# Repolex Knowledge Graph of sphinx-contrib/aafig

RDF knowledge graph data for [sphinx-contrib/aafig](https://github.com/sphinx-contrib/aafig), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/aafig
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4b192aa8d69def23a279e87b5e60beee40886ae0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4b192aa8d69def23a279e87b5e60beee40886ae0
│           └── chunk-001.nq.gz
├── blob
│   ├── 047b876fe8b1ca6ce026032fd11cfaf0e09421c9.nq.gz
│   ├── 1164038cbe9bafc8c4f4286db8b60b03237bcffd.nq.gz
│   ├── 1724367514219c4d859bf27393c5e998f14a9b49.nq.gz
│   ├── 2c0c46a91c90f0557a599908fb0c92f61cc8a921.nq.gz
│   ├── 37467bdc4752a31da7763d7cf24051ab5a8a4307.nq.gz
│   ├── 4392bc2e6cc50efff9e4fed160254e46f96cc396.nq.gz
│   ├── 458aadd6352f3defb4e402e5948c3c7c8c86b676.nq.gz
│   ├── 5ff9a2af66ba65862cc41772fbfb815850aa4907.nq.gz
│   ├── 8e9e7de2939a82ff939c32a00a640d78f211a660.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── c11cf4d28056a6ead35a1749e481b2f3894985a9.nq.gz
│   ├── c1523749ff61aef4fbb79ec793512213e35f3db7.nq.gz
│   ├── eab12bde50dd24cbf8f0033dbd5dabfac1064df1.nq.gz
│   ├── f71e577883b1adf451fa6442745082cae4c481ed.nq.gz
│   └── fdfc620ed25b60c5293d0a03a1fb1048dc599979.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4b192aa8d69def23a279e87b5e60beee40886ae0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[sphinx-contrib/aafig](https://github.com/sphinx-contrib/aafig)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
