# Repolex Knowledge Graph of sphinx-contrib/prefecttask

RDF knowledge graph data for [sphinx-contrib/prefecttask](https://github.com/sphinx-contrib/prefecttask), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/prefecttask
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 44112bca2d6bd66b00c40faf52a41b1dda6809c9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 44112bca2d6bd66b00c40faf52a41b1dda6809c9
│           └── chunk-001.nq.gz
├── blob
│   ├── 38195daabcf3f2cfd2b19701f643cd8aaf6a4232.nq.gz
│   ├── 3a604e3aabd2d0c81414f2045df2ee20336f7fab.nq.gz
│   ├── 3e672f76f0bdc834eccb080b56017fbf6fee2ae1.nq.gz
│   ├── 74c66f5d851577725991910cebabf911f3e9720f.nq.gz
│   ├── 9217608f4ee646390eb23357a4f1f6f9ec7e6575.nq.gz
│   ├── ac7d049af032e3844752d27d07bb59fa97ab4907.nq.gz
│   ├── d0422d014688dcc1488a3a907f9c1f345f10d4e3.nq.gz
│   ├── e1095ce6e088a91932b1fab6e53a0f1801a767e1.nq.gz
│   ├── f1baac53e70622fb5419b9d7e88678f8aed3e7be.nq.gz
│   ├── f288702d2fa16d3cdf0035b15a9fcbc552cd88e7.nq.gz
│   └── fd2209536371b289482bbc1aac0bd826903010ef.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 44112bca2d6bd66b00c40faf52a41b1dda6809c9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[sphinx-contrib/prefecttask](https://github.com/sphinx-contrib/prefecttask)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
