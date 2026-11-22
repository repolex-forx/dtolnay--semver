# Repolex Knowledge Graph of dtolnay/semver

RDF knowledge graph data for [dtolnay/semver](https://github.com/dtolnay/semver), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/semver
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7625c7aa3f0e8ba21e099d1765bcebcb72aa8816
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 7625c7aa3f0e8ba21e099d1765bcebcb72aa8816.nq.gz
│   └── repolex
│       └── 7625c7aa3f0e8ba21e099d1765bcebcb72aa8816
│           └── chunk-001.nq.gz
├── blob
│   ├── 077ff323c560e8ec0327d29129adba5cfd6b3c95.nq.gz
│   ├── 12e8840044480d37e1969ff1283c0def3863d0b3.nq.gz
│   ├── 18612c27d7a9a92919e42d9f72ec9fc292ca0701.nq.gz
│   ├── 19784a9582a2143de58561234ab30bf782aecd67.nq.gz
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 1fcb0fb5ee78ffc0c86c8b88494c824e10f7bbaa.nq.gz
│   ├── 1fcc7d87f624088da616387da4cc17f791dd79d4.nq.gz
│   ├── 2d6be7c2d380276aaa76053f449e05399360010f.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 3be85894020a9eba94f5f478b84576bcf448c739.nq.gz
│   ├── 40d859654880bc3befd590b9506edeffe5a6f948.nq.gz
│   ├── 44c3b587177f69113bfc5e0f84ee7777d1f96abd.nq.gz
│   ├── 5d16689129499500828ff51438da08aadf36d451.nq.gz
│   ├── 5e49e8065c0f9ace6ccc72f5c3c78c556091e362.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 7c677075701517115492009339ae5964ba02b3c7.nq.gz
│   ├── 82685e4fddd330402b91b0a3e2393556b7786772.nq.gz
│   ├── 9bc1cd760a4e251bd0c6e6165c756728f5c90259.nq.gz
│   ├── a12d7b9ac01043fd15cc1cbcaa81ba5a7e7acc4e.nq.gz
│   ├── a138c80e56dce8afe0df0eab82fd88217d38eaa0.nq.gz
│   ├── a3cedd8ff752d0ccb2522d802679c727df2b06e0.nq.gz
│   ├── adc32581017479e6776f6b0b30fe1f19f5f54efb.nq.gz
│   ├── bffe1254994d1e78bddcbcc788498538ccc0e638.nq.gz
│   ├── caf7ebeb3f60f1c6b324c0cd1b7df0d00c413fe8.nq.gz
│   ├── d7446e5b57040490ec674c73d0621d57af84d5db.nq.gz
│   ├── e5fff35f71a9acc347cda47dcea673d86c992ee5.nq.gz
│   ├── e9c897bf2135e404e01a42398f5a764f7e849e61.nq.gz
│   └── f5726c7903a4b505977da35d7628b9144ddcd2ec.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 7625c7aa3f0e8ba21e099d1765bcebcb72aa8816.nq.gz
├── filetree
│   └── 7625c7aa3f0e8ba21e099d1765bcebcb72aa8816.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 38 files
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

[dtolnay/semver](https://github.com/dtolnay/semver)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
