# Repolex Knowledge Graph of python-trio/trio-talks

RDF knowledge graph data for [python-trio/trio-talks](https://github.com/python-trio/trio-talks), parsed by [repolex](https://repolex.ai).

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
rlex download python-trio/trio-talks
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 184aeb818b0395028941f43e769c120e94be0d5a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 184aeb818b0395028941f43e769c120e94be0d5a
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e259d42c996742e9e3cba14c677129b2c1b6311.nq.gz
│   ├── 0e93534a258c35aab939c924296f879e9226586b.nq.gz
│   ├── 104c402ebf17ef55f9cdca2114f0a4449f6dd039.nq.gz
│   ├── 1b1e801c846f76d561f689ba33b14f35748c78a3.nq.gz
│   ├── 2b49eb7a6e3ab68d3421c9f82031a3b4b3e2c13c.nq.gz
│   ├── 31a676727a13ca3fc3bc9ff3b49d1ab0105eda6f.nq.gz
│   ├── 358f92e7e56a5169bb0b6b91eff1231ef212c43f.nq.gz
│   ├── 89123cfc54fd18ef90df8a405e9885065f184e28.nq.gz
│   ├── 8a3980ed6f0cc33c55e44bdfddae94a221d25c5b.nq.gz
│   ├── aad40037c646916c39b142e4648d34d89f0c14cb.nq.gz
│   ├── b51731fc53666ea5820abc04eb93b42738ba990b.nq.gz
│   ├── dfe316d24865c7af76d3667e2461200df1f60e8c.nq.gz
│   ├── f38c5167733eb2fd1cb677450f876788a4aa603e.nq.gz
│   ├── f8f6d9f21e84a4e108558d50d47913b8dec934a4.nq.gz
│   └── fa3ab942cb80033f935ca1978eb996d5e3037ca0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 184aeb818b0395028941f43e769c120e94be0d5a.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 22 files
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

[python-trio/trio-talks](https://github.com/python-trio/trio-talks)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
