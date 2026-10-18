# Repolex Knowledge Graph of thombashi/subprocrunner

RDF knowledge graph data for [thombashi/subprocrunner](https://github.com/thombashi/subprocrunner), parsed by [repolex](https://repolex.ai).

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
rlex download thombashi/subprocrunner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6fb306496ea897b34bccd66c4e801843ebc00862
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6fb306496ea897b34bccd66c4e801843ebc00862
│           └── chunk-001.nq.gz
├── blob
│   ├── 082e9ca3a8cefb5a2f9b02a47240855bc9f8e01e.nq.gz
│   ├── 1696e4a545290add4fb4301aff97ab32165d8bc7.nq.gz
│   ├── 1862de44521a83ca1462578766d0700b12ffe2b1.nq.gz
│   ├── 1a92e678e3f4d0aa3f9b09914502dd3007142577.nq.gz
│   ├── 1de427a45ad4986de92d71eea6a657aceb095766.nq.gz
│   ├── 2933c6ff9c2ab17f2077a92da70850c546ce2baa.nq.gz
│   ├── 341913f9567177d71ca25520438c3e21a91dd2e0.nq.gz
│   ├── 35e3314155d1c6d96f93346ae54841398d02f46a.nq.gz
│   ├── 3ad25db9f1bab161e184dc518e5121a18212f465.nq.gz
│   ├── 442528e8401c73c8a3e49ae02f71ee6dabc44679.nq.gz
│   ├── 4467558327c91316511670864f52877a832e19c6.nq.gz
│   ├── 44f8af048c30de57146215e7f46eabecfab26d75.nq.gz
│   ├── 571855b9170e42125dd0aaa7ca1b1b20d12b3720.nq.gz
│   ├── 576b3986d1de2bace78018df7bde7ba103a0b6b5.nq.gz
│   ├── 5bb42c48f497f39d7d9e835d844d841e73605786.nq.gz
│   ├── 659942530b53573d75e75d1a84d63e906ef0b3a7.nq.gz
│   ├── 6fa61e67fe6d684f7e0d8aa205e4cc581d18ab24.nq.gz
│   ├── 721045d09d3a97c042a0feb5c3de204a18334428.nq.gz
│   ├── 74f886af17fef7de0bc3c5ceb096e7ded9c6c5c3.nq.gz
│   ├── 7d1c33a7121001f8e265e819bba8a079960452c6.nq.gz
│   ├── 860063f423a138465fdd91d03b383f2ce939093e.nq.gz
│   ├── 8b5b9036b147d85c9ebb54a87aea38b730ed2d3d.nq.gz
│   ├── 8c139c7bec29cd1fd808ae643e5b9181813f32b8.nq.gz
│   ├── 94a0a0912e6df5a499eb4d107a478a4cd5c0d833.nq.gz
│   ├── a7904c826e9d7b3d475211006e2f190f0778edf7.nq.gz
│   ├── bd1518d4ac49e94300f95dd2ec48e501a800bc94.nq.gz
│   ├── c0f551f4b23cd1c4786f1e3a1f8badac33682598.nq.gz
│   ├── cdac498384abcc9e6e972702ee6b114af04fc462.nq.gz
│   ├── db3d8a8bd2e0d6e2dfdf7346df406b6e1e49da0c.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6fb306496ea897b34bccd66c4e801843ebc00862.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 38 files
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

[thombashi/subprocrunner](https://github.com/thombashi/subprocrunner)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
