# Repolex Knowledge Graph of samuelcolvin/awesome-mcp-servers

RDF knowledge graph data for [samuelcolvin/awesome-mcp-servers](https://github.com/samuelcolvin/awesome-mcp-servers), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/awesome-mcp-servers
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── beb8dc051b807c9568c6e043b317271b59a36779
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── beb8dc051b807c9568c6e043b317271b59a36779
│           └── chunk-001.nq.gz
├── blob
│   ├── 1e543669d96fd00ac76313d82422d7746e54929b.nq.gz
│   ├── 618f243bcd9cd04268ac9bd4bfab322b36d847d9.nq.gz
│   ├── 7d063f1a332dba7df714f3f6b2244cc552fd0759.nq.gz
│   ├── 7f5a6e30ea24860b1528cfb7a54cf777650fd46a.nq.gz
│   └── a94556e6e3b51c472d56e68cea6394ce44024952.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── beb8dc051b807c9568c6e043b317271b59a36779.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 11 files
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

[samuelcolvin/awesome-mcp-servers](https://github.com/samuelcolvin/awesome-mcp-servers)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
