# Repolex Knowledge Graph of astral-sh/uv-pre-commit

RDF knowledge graph data for [astral-sh/uv-pre-commit](https://github.com/astral-sh/uv-pre-commit), parsed by [repolex](https://repolex.ai).

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
rlex download astral-sh/uv-pre-commit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2e145a365871c9fef3715d38b9b7393ce4174c85
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2e145a365871c9fef3715d38b9b7393ce4174c85
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d4a882a3a2380f1d3f841561a9b6179c047439b.nq.gz
│   ├── 12c2a2235fd9337fb0d605ebde485b95ea103db4.nq.gz
│   ├── 23b2203df3cf8a2c5206343b40511b5e182cd8b2.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2b71fb75e6863577b20476649bc4b3e867ab0fcf.nq.gz
│   ├── 309de5763b135a2f879391d9c899e95ca488798b.nq.gz
│   ├── 317dd6361b6e1d55cd213070237a4fb61aec68ab.nq.gz
│   ├── 9e103803ce62fd0f46e5a7b526c93ec6d49ee2ab.nq.gz
│   ├── c16d8bb1db2621505a8bdd37d260d6f312b049ad.nq.gz
│   └── d5a3bf457046eddec7ee968883427f75533cf66d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2e145a365871c9fef3715d38b9b7393ce4174c85.nq.gz
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

[astral-sh/uv-pre-commit](https://github.com/astral-sh/uv-pre-commit)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
