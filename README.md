# Repolex Knowledge Graph of click-contrib/click-log

RDF knowledge graph data for [click-contrib/click-log](https://github.com/click-contrib/click-log), parsed by [repolex](https://repolex.ai).

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
rlex download click-contrib/click-log
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6e9ef983593124adb2d3f73cb6f0631afcfdfd9a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6e9ef983593124adb2d3f73cb6f0631afcfdfd9a
│           └── chunk-001.nq.gz
├── blob
│   ├── 058a229ab9780e00c003f4a8c737ca2c00038229.nq.gz
│   ├── 134e5db45c3fce847b9c8e60cac65b680d4de2b6.nq.gz
│   ├── 281506513b618a69c037394fa20613682a9e496f.nq.gz
│   ├── 31becd8da90f37b7e81df4bce023b1462f0b58d5.nq.gz
│   ├── 59901dab441feab91e0e607041df9d58c7108015.nq.gz
│   ├── 928371fef36714e7cbec9e52ebcbecd6f654f586.nq.gz
│   ├── 97901fc3e35fabf8eece4a37e14c8cb5e0d01ea3.nq.gz
│   ├── ab35c0ef3ff9217b886f06eee762a8b06530019f.nq.gz
│   ├── b09058521bb118adda080c1a0ec1c83fa764a30d.nq.gz
│   ├── b50ea519fa626eeaf37e533c31f413534e1116f6.nq.gz
│   ├── b8085bc724f05c193d6b4c60d282b606f8df7402.nq.gz
│   ├── bde55a6d112754f17e148beed93a4b7fb381b723.nq.gz
│   ├── d257e7b6731b86267b31c2b30987f6d937806fc2.nq.gz
│   ├── e9ae94fa76db1feafe30bca47d2c18bf909a010d.nq.gz
│   ├── ec5102e2489e153bd7afd806f6988d917887c3d1.nq.gz
│   ├── f8d036f543734e3db36a0e1d54eed570bc547502.nq.gz
│   └── ffe30d199fa42a60c960a2e755497df19681bf7f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6e9ef983593124adb2d3f73cb6f0631afcfdfd9a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[click-contrib/click-log](https://github.com/click-contrib/click-log)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
