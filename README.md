# Repolex Knowledge Graph of mne-tools/mne-dash

RDF knowledge graph data for [mne-tools/mne-dash](https://github.com/mne-tools/mne-dash), parsed by [repolex](https://repolex.ai).

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
rlex download mne-tools/mne-dash
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 087cb76a5b29d56e84d71f8f7025f6e940ffdecf
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 087cb76a5b29d56e84d71f8f7025f6e940ffdecf
│           └── chunk-001.nq.gz
├── blob
│   ├── 0eac6792003177357a8f9b4f73c589e49441ebed.nq.gz
│   ├── 37e03533af6284ebbabaad49e95bb69dcf2802d5.nq.gz
│   ├── 38651df9da5d9468f516665dd05cd50312138427.nq.gz
│   ├── 671640e82a19cc0376709d415e35af5e64292454.nq.gz
│   ├── 75c9945169d82d4da076875cccdb41d699e217a9.nq.gz
│   ├── 892a1d5de4096937c5eb19d922b7b53422d03059.nq.gz
│   ├── 91b48831decdb92858873a75b6351cb3afcda7a6.nq.gz
│   ├── a2c8b998c919d6af6b9fc153f7b76e078c899687.nq.gz
│   ├── bcde72044149474bc130e0b64ef6146a5a3d5f40.nq.gz
│   ├── e080d0876c129d1a444ffa29c4cb816a4fdf5b94.nq.gz
│   ├── e44ff28a5c630737c069ee1fd9b8da849d6eaac2.nq.gz
│   ├── eb700fc717bc9294bc97d337766f3fb8eb9d17e3.nq.gz
│   └── fa720bfc81417270b4b6125be545831e371e04d1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 087cb76a5b29d56e84d71f8f7025f6e940ffdecf.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[mne-tools/mne-dash](https://github.com/mne-tools/mne-dash)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
