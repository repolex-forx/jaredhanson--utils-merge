# Repolex Knowledge Graph of jaredhanson/utils-merge

RDF knowledge graph data for [jaredhanson/utils-merge](https://github.com/jaredhanson/utils-merge), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download jaredhanson/utils-merge
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 80f8533cde3039ff68efead269c41fb5f1a0e59b
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 80f8533cde3039ff68efead269c41fb5f1a0e59b.nq.gz
│   └── repolex
│       └── 80f8533cde3039ff68efead269c41fb5f1a0e59b
│           └── chunk-001.nq.gz
├── blob
│   ├── 2b8b14ce0958af216c006f4795f1d209d8d1dbc6.nq.gz
│   ├── 2bdd88563935d25a84895ccfda1b8de503d04518.nq.gz
│   ├── 2f94e9bd2ea5756e98e8927f9bbca8717c8d5472.nq.gz
│   ├── 4265c694fec6f4eb174612ee434c3ab7da8e40fa.nq.gz
│   ├── a02940d41fd1e6e005dc6f981cd6a1cdc4dea0ba.nq.gz
│   ├── af92b021bee9937fd8c64d36258d1671873cc472.nq.gz
│   ├── ba9e473bc282400379c17b839ba23a9f0f7dc2c6.nq.gz
│   ├── c99b18e56a351ccf170847462b48d4f70e846add.nq.gz
│   ├── d95c77f652067936c76dd23b579e601479627795.nq.gz
│   └── e33bd10bb4a3570f3c118561559a210c07ce6fa7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 80f8533cde3039ff68efead269c41fb5f1a0e59b.nq.gz
├── filetree
│   └── 80f8533cde3039ff68efead269c41fb5f1a0e59b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 20 files
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

## Source repository

[jaredhanson/utils-merge](https://github.com/jaredhanson/utils-merge)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
