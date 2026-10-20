# Repolex Knowledge Graph of klen/muffin-peewee-aio

RDF knowledge graph data for [klen/muffin-peewee-aio](https://github.com/klen/muffin-peewee-aio), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download klen/muffin-peewee-aio
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ffc6e9ef401e154fdbc6e26635602e160fabb73c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ffc6e9ef401e154fdbc6e26635602e160fabb73c
│           └── chunk-001.nq.gz
├── blob
│   ├── 031e64eeb03af7678cf46c119683d6c2ea3bcd67.nq.gz
│   ├── 0799f242a62fc36582b6d4eebed01b40a7dae46d.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 0f8a68adf224384d33a7f5da6a660a628d8b7a12.nq.gz
│   ├── 1389293253adb215a02017eb8bac70f2d5000e5c.nq.gz
│   ├── 1d0105f996733670aca16e08071d0738aac0a4d4.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 2e7c3833651750c35bcbdbd17a286e4ce3191423.nq.gz
│   ├── 43d30664440a4d71df537fdae42452e1f924466b.nq.gz
│   ├── 4a060cc8ce501e4a5b9157c2f5ed52285582dd60.nq.gz
│   ├── 4dfbc5c5982e7302c42ada8ec6c441ea8e59ba7a.nq.gz
│   ├── 50147aa389e7e2fcf059c4ffa7f9a90360a32308.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 6e01047c068eda4b69abe103ae8da636731f8ab9.nq.gz
│   ├── 6e37bd281919d0dba16c6a8093c10e95f685d5ac.nq.gz
│   ├── 728922dec2c5f083d53bb28b9dd4e659c8de3847.nq.gz
│   ├── 73df01ca0c7b5d4338b5709db1a35b5d77c422b5.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 84ba55c37f6fc6eed0ff2c0be081da68d8e9dc50.nq.gz
│   ├── 8dde55c4529cd6a4037e6dc61702c58f093b5094.nq.gz
│   ├── 9a183e685a17e16a1704929d2b6c5be1daebf538.nq.gz
│   ├── 9c7740fd1eec6c0c4dc758bac35b14ea4330de19.nq.gz
│   ├── 9e2bf4020eb925cae80b0e2fac7e611e6bf279c4.nq.gz
│   ├── 9ea3eabaadfa74931dd241ac49ef1424c7c07d0e.nq.gz
│   ├── ace0e6397dcf5dbe3512f2308ee718a1ac03470b.nq.gz
│   ├── c686f6c7b1ca9bfee066eb09b44a828ea9e978e0.nq.gz
│   ├── c6c54710197d498c1c2dc47fe473deff1e0c4c2e.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── cea28cce1f4df3c2a3aa0cdbcf891cc41aad6707.nq.gz
│   ├── e06da19e7b2fbd9e5a0730a1afe62fdcd1e182f3.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   ├── f58972a836fc04d58f30626ec982146391b774ef.nq.gz
│   └── fc47a503e3385c172f66288cae72c0f559f0e158.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ffc6e9ef401e154fdbc6e26635602e160fabb73c.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 43 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[klen/muffin-peewee-aio](https://github.com/klen/muffin-peewee-aio)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
