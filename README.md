# Repolex Knowledge Graph of scrapinghub/price-parser

RDF knowledge graph data for [scrapinghub/price-parser](https://github.com/scrapinghub/price-parser), parsed by [repolex](https://repolex.ai).

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
rlex download scrapinghub/price-parser
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6718bfe8447f2de17ecc152d3ad2a4c51520c755
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6718bfe8447f2de17ecc152d3ad2a4c51520c755
│           └── chunk-001.nq.gz
├── blob
│   ├── 14a8d7d16575242422d84255751ae998935722e8.nq.gz
│   ├── 3abd521a848af08953dd575c7cf41ca8aa4eac3a.nq.gz
│   ├── 40ea37abf1ae187ff59cad39cb1ed43c3275ce27.nq.gz
│   ├── 4a397ef98a68a1405c4499f29c6296b51998bdf8.nq.gz
│   ├── 4bf3abf7f02de6688e90fa9b79f973f9bd68d618.nq.gz
│   ├── 519abf603c20111d7e6b01d7d92ef67eae502968.nq.gz
│   ├── 5b6ce8c828cffd4ae0ca25baab94b7a7eae1e6d3.nq.gz
│   ├── 6470a1c69746cdb7235f5d315d95134231dd9f94.nq.gz
│   ├── 7e11a718d094c7c41ea02214059b44f69b7ae6d9.nq.gz
│   ├── 905335f0d79599e596746a67083a28aabe117c71.nq.gz
│   ├── 95a0d1d53ae7b0e880acf4a0a41979f3b6b201ba.nq.gz
│   ├── a1181bced49bff112d5c34cf0668f11e4cd961e1.nq.gz
│   ├── a76cba3fefd2db2e866b122c610fe69915e6e61e.nq.gz
│   ├── a7b0552e879037618004f1ed6cb41deb4c55c917.nq.gz
│   ├── b99db9fbe1de1e04479df4b33e6c89790ed467d1.nq.gz
│   ├── d8aa6b984fa2c4c4891f114100d205ad99801b34.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e6d3cf17ee1779e5b5b8b61496f2df66c9c55cc4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6718bfe8447f2de17ecc152d3ad2a4c51520c755.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

[scrapinghub/price-parser](https://github.com/scrapinghub/price-parser)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
