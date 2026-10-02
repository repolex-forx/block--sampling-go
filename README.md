# Repolex Knowledge Graph of block/sampling-go

RDF knowledge graph data for [block/sampling-go](https://github.com/block/sampling-go), parsed by [repolex](https://repolex.ai).

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
rlex download block/sampling-go
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2fd0710ed40518f2a8344176b7be3f9d1b6405d5
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 2fd0710ed40518f2a8344176b7be3f9d1b6405d5.nq.gz
│   └── repolex
│       └── 2fd0710ed40518f2a8344176b7be3f9d1b6405d5
│           └── chunk-001.nq.gz
├── blob
│   ├── 1bc469e68eb776aa52185c6cbfc5cdcaee837ce3.nq.gz
│   ├── 3f146feffacb49dc5285a0887e435e9efbdf9048.nq.gz
│   ├── 4a002801612b19d3ab38733bebcfdbd70300bc02.nq.gz
│   ├── 5d5a4abe04f6338fa7d1f3501b836f94e8bdde73.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 6db80a0e9d5f8e1ef511de58abb31ac286ef0298.nq.gz
│   ├── 7937c689ada3d05e230da4559ceb5d207154d952.nq.gz
│   ├── 835e41205067b6c947f03d33f436fa65c240259b.nq.gz
│   ├── 8ef778f0d4ac9384563efff92b275859a2e5674b.nq.gz
│   ├── 919a8546c43e2be4fe535d6228d33ed1663b7ca9.nq.gz
│   ├── 96bbbb3648282fc267f532310d27543f4d7cbc2e.nq.gz
│   ├── 9920966a78851cdbc9920fba45d69a9f12aaf0e3.nq.gz
│   ├── b7f8df57d0c676dc87b9ac8fd1621b6f1553f7e9.nq.gz
│   ├── c4c1710c475c1aaf6b41e75cf7003b167ddb3739.nq.gz
│   ├── c4f18419741c3dc16957a8080793e6bf3cb64c3f.nq.gz
│   ├── ca2417c8e3dfb04a2a4a320075442b430bda8872.nq.gz
│   ├── cec9cd2c957acc823bf6356a7ed99ef9d066d669.nq.gz
│   ├── d7c3aaa2523f5be3fc0899486bc07282d0668179.nq.gz
│   ├── e2e115e557056d9b04e12493a88305d7653214ca.nq.gz
│   └── eda70e9ee58d41d7b1faef1936212fa5df0a1dd3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 2fd0710ed40518f2a8344176b7be3f9d1b6405d5.nq.gz
├── filetree
│   └── 2fd0710ed40518f2a8344176b7be3f9d1b6405d5.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 29 files
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

[block/sampling-go](https://github.com/block/sampling-go)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
