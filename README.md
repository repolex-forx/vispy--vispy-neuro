# Repolex Knowledge Graph of vispy/vispy-neuro

RDF knowledge graph data for [vispy/vispy-neuro](https://github.com/vispy/vispy-neuro), parsed by [repolex](https://repolex.ai).

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
rlex download vispy/vispy-neuro
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b4d5a456f992f2c7eff8d7baf5931297a8767937
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b4d5a456f992f2c7eff8d7baf5931297a8767937
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d9a03a58bcff91cbb4c9a08d271881a84708aa3.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 26cf0e0220c728e31188885d956cc44f24b1b506.nq.gz
│   ├── 3b55aad0ea4edea762c6ca34b4d86a1d70daec8a.nq.gz
│   ├── 4e3d2824471e97b7088f152e479a8747206adc9e.nq.gz
│   ├── 621d076841aef83dd3fd83b31d192528c10ba6e6.nq.gz
│   ├── 65d7a6ec89f8d2273a434935c0a412d7181e4b93.nq.gz
│   ├── 6c341533ea8e33d51fdf2be8385b69d2e6c1b27c.nq.gz
│   ├── 759fa024dcd5ae5741b220fb3db3535e0c97ef64.nq.gz
│   ├── 83972fadc2724842e111d0d3e2829a59ae3d3f45.nq.gz
│   ├── 8b137891791fe96927ad78e64b0aad7bded08bdc.nq.gz
│   ├── 91dfce67e9cd91e0164342f7b066a49431a1bd28.nq.gz
│   ├── 99eb10241221d68b85c1cd26cce222c0e86a6ffb.nq.gz
│   ├── c23ed34f082eb1600b223d5551a8f7c84148db99.nq.gz
│   ├── c506c897ef78a47e4726059b0269278f5974971d.nq.gz
│   ├── c68b2af64767269abc992015ac1f72187027bb7d.nq.gz
│   ├── c8329484948dff9f2ba15d221bb1822e70f5382d.nq.gz
│   ├── ce2f7b6098f44a0468467fe14716a3af4c4b6eb5.nq.gz
│   ├── dc8f82cccf5a926b2f26e8dbcd17022a56ba9f4c.nq.gz
│   ├── ed5fb57b585050c98b8b8b6a94021f8ad501e271.nq.gz
│   ├── fcfef4d57421d3f75b5614f083382bb66801a170.nq.gz
│   └── fdbde616ad7a37f77fa8bfa30dd6c8be09431929.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b4d5a456f992f2c7eff8d7baf5931297a8767937.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 28 files
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

[vispy/vispy-neuro](https://github.com/vispy/vispy-neuro)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
