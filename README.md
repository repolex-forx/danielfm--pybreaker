# Repolex Knowledge Graph of danielfm/pybreaker

RDF knowledge graph data for [danielfm/pybreaker](https://github.com/danielfm/pybreaker), parsed by [repolex](https://repolex.ai).

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
rlex download danielfm/pybreaker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2b0b965fcfc7705ca9a776c614ea6cb3ec3fe783
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2b0b965fcfc7705ca9a776c614ea6cb3ec3fe783
│           └── chunk-001.nq.gz
├── blob
│   ├── 1c226d512cc67013e4e8b4592625de7ba8aecf38.nq.gz
│   ├── 2f40c5bbf0095595f8b92b1b55649c3469281206.nq.gz
│   ├── 3611919d06e9cf261e5ed5929a54af62a048b133.nq.gz
│   ├── 37f8c7aed545c43c0f277c4ef86a3ea9950f949d.nq.gz
│   ├── 48bffd64d2733af45201884ca46144ab8d2e6cb5.nq.gz
│   ├── 4d75c3847c1f5277499b2e236fe4f400b63f7910.nq.gz
│   ├── 56f2dbf65da3163129e1144fe62761c22bf67b04.nq.gz
│   ├── 59dabb5905c1b5842d9de6cd0725b8931b07a3a5.nq.gz
│   ├── 5a81b0841db9b2bc42bf10f56c9ee054604121b5.nq.gz
│   ├── 5f8e818b2848f014e4957922244982fe32aa5a30.nq.gz
│   ├── 7fcc08864c65dcd2a69efec1442331d0d54a273f.nq.gz
│   ├── 8175553cf0235e5f995093bf77577eb349995a6e.nq.gz
│   ├── 85416b75f0a05ea3c861110c1113bb309b35fd73.nq.gz
│   ├── 9c1caac2c91ba5201266950ed5f0d29ba2bd1625.nq.gz
│   ├── a007f5859b31c77ddab9a8924b16f377931b1767.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2b0b965fcfc7705ca9a776c614ea6cb3ec3fe783.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[danielfm/pybreaker](https://github.com/danielfm/pybreaker)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
