# Repolex Knowledge Graph of simonw/datasette-explain

RDF knowledge graph data for [simonw/datasette-explain](https://github.com/simonw/datasette-explain), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-explain
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d39ba0ff187efad61d7e2995113bbcedd2d16dec
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d39ba0ff187efad61d7e2995113bbcedd2d16dec
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 54bec923ed288505ffa1e09423f0b3de7446fcaa.nq.gz
│   ├── 59039dd7bf4b974c0f3b73ae92995cc71d43f840.nq.gz
│   ├── 657a42fcaff8e56d3170426737885b54ef091d65.nq.gz
│   ├── 6934c7f3f8dc4cf6638c8fdee08965862e23d6d0.nq.gz
│   ├── 6c975043a66954e5c7786cdc16fabce14512c599.nq.gz
│   ├── 960ddce3457617d26da8d34f478f43494c414e34.nq.gz
│   ├── c1c3c472afc26c81053785e900a8d8279db7fae8.nq.gz
│   ├── d0d5ce3ee8fa6494d61b4f902ee7d8de943e1b36.nq.gz
│   └── f692e6cdede0eba47c63bd43289fc6f584126fd1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d39ba0ff187efad61d7e2995113bbcedd2d16dec.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[simonw/datasette-explain](https://github.com/simonw/datasette-explain)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
