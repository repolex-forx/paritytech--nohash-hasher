# Repolex Knowledge Graph of paritytech/nohash-hasher

RDF knowledge graph data for [paritytech/nohash-hasher](https://github.com/paritytech/nohash-hasher), parsed by [repolex](https://repolex.ai).

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
lexq download paritytech/nohash-hasher
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 99b021664e9d7fd3e1f7ffb8633a137e21e12149
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 99b021664e9d7fd3e1f7ffb8633a137e21e12149.nq.gz
│   └── repolex
│       └── 99b021664e9d7fd3e1f7ffb8633a137e21e12149
│           └── chunk-001.nq.gz
├── blob
│   ├── 50e024ef7de0596ccc0147902ab8a43b3ceed2b1.nq.gz
│   ├── 5c9ac80a8fafb051d7f4cfc8568bc0c25175c101.nq.gz
│   ├── 693699042b1a8ccf697636d3cd34b200f3a8278b.nq.gz
│   ├── 940c8e733f007b3e6f6dc2e83d9eb9ae42108080.nq.gz
│   ├── b2560d6525ae4bba546fce6104d14e182a30da33.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   └── d8322d9f2a586b7a69ff72bda3c424b53630861f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 99b021664e9d7fd3e1f7ffb8633a137e21e12149.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 16 files
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

[paritytech/nohash-hasher](https://github.com/paritytech/nohash-hasher)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
