# Repolex Knowledge Graph of holoviz/.github

RDF knowledge graph data for [holoviz/.github](https://github.com/holoviz/.github), parsed by [repolex](https://repolex.ai).

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
rlex download holoviz/.github
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 978014ce9ed9fccdea47c3a085039d98192b37a1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 978014ce9ed9fccdea47c3a085039d98192b37a1
│           └── chunk-001.nq.gz
├── blob
│   ├── 209dbfd7b32aa993ca30ae252a698185dd36c65e.nq.gz
│   ├── 584bedcad1c11563bbdb7ed2124fb9afa591747c.nq.gz
│   ├── 8b8182c2028e3fdda0a821295394599d18e28c74.nq.gz
│   ├── 9e9661a9aaaf644e1f69089bd6e86be4227de585.nq.gz
│   └── fd62ef9da98673d9be27a19b3a71bf7dee3c9d76.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 978014ce9ed9fccdea47c3a085039d98192b37a1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 13 files
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

[holoviz/.github](https://github.com/holoviz/.github)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
