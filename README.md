# Repolex Knowledge Graph of NousResearch/hermes-plugin-backsearch

RDF knowledge graph data for [NousResearch/hermes-plugin-backsearch](https://github.com/NousResearch/hermes-plugin-backsearch), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-backsearch
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 477d81446c856a39021c069a88a047e9c89fbba3
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 477d81446c856a39021c069a88a047e9c89fbba3.nq.gz
│   └── repolex
│       └── 477d81446c856a39021c069a88a047e9c89fbba3
│           └── chunk-001.nq.gz
├── blob
│   ├── 1034e3a8a5378792887d615b3c56d6bc67e1fe47.nq.gz
│   ├── 5700b997827973cb0eb6d84a2782bb08a5872434.nq.gz
│   ├── 692f12e5eadf6faf839a7be9f8f47d3cfa1169f6.nq.gz
│   ├── 6a73286fc441e803a1735dc1de2661739e23aa69.nq.gz
│   ├── 706d7f91a06fc67fc5ade5e17429376f1cf12b1a.nq.gz
│   ├── beff8086e41be5069dea64642cd85b4c9c7d5d64.nq.gz
│   ├── c2316dacfd79dadba8956877b2aaa246b8ad6d89.nq.gz
│   └── de34220232ef73fc140adc0fd46acaec8608b569.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 477d81446c856a39021c069a88a047e9c89fbba3.nq.gz
├── filetree
│   └── 477d81446c856a39021c069a88a047e9c89fbba3.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 17 files
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

[NousResearch/hermes-plugin-backsearch](https://github.com/NousResearch/hermes-plugin-backsearch)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
