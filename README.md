# Repolex Knowledge Graph of florimondmanca/arel

RDF knowledge graph data for [florimondmanca/arel](https://github.com/florimondmanca/arel), parsed by [repolex](https://repolex.ai).

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
rlex download florimondmanca/arel
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ec8768016be115d5ff4dbad6981c916423debe97
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ec8768016be115d5ff4dbad6981c916423debe97
│           └── chunk-001.nq.gz
├── blob
│   ├── 013495dd5e90a5fdb920522263c78034f0ae0f67.nq.gz
│   ├── 149ca1171cc321f6d5c75f39de2b019708ce90b6.nq.gz
│   ├── 15608b6742ca4cbc1eb9ada0b24d2d16d865bfdf.nq.gz
│   ├── 182f3565c8747c775274f334f8b6ad8512c95793.nq.gz
│   ├── 1b81003d7c7de023630d5c0e8dce68ba22307f8c.nq.gz
│   ├── 2942f2be21fdc39c87eb462c1b668c7161e86f39.nq.gz
│   ├── 2dcca2f982e1321037ad7b53c90cc30d3258c5c6.nq.gz
│   ├── 34f275ed3c9d7894766f1b188d9d5e13327f24bb.nq.gz
│   ├── 375573aac2852fdc36f223d9fac7790c476fca47.nq.gz
│   ├── 38310de52044b6273ef872f477a12f331e71332c.nq.gz
│   ├── 405f33e98e0e5cfd13d7acd8a88dd467687779a5.nq.gz
│   ├── 49139e012b8905b8b421e488415d4e509f1838bc.nq.gz
│   ├── 4fbda3818cd913ea760a8187a85fe052d28fb887.nq.gz
│   ├── 5580482f3fefe5620609489b3e1682dddde5cdbc.nq.gz
│   ├── 5d884beda9206813d3a8e94c7626a75e1936ab9e.nq.gz
│   ├── 6d763ff3ea4c139a5faef3df4cf2f41897c0c443.nq.gz
│   ├── 70e3c3700f2a6cc868ebd05ff01cace1915d1bfb.nq.gz
│   ├── 71f7867f3e813abd43cd2b5669eff0eabd071fd6.nq.gz
│   ├── 7ae72c93caa6320393f8ac3bbad45004656b968f.nq.gz
│   ├── 831f76d623f067700dc860cbe24dae93ec4dab67.nq.gz
│   ├── 85b728cf19642d1810816ba518171d0ed4ac30b1.nq.gz
│   ├── 89b57cfdea087bedec52527408934f8b84b6368d.nq.gz
│   ├── 8af718fbc7df18ee0d79a9c92407289092d84bff.nq.gz
│   ├── 92f9e1ac32636ee6fed365f01b861cf0e8855ada.nq.gz
│   ├── 97e4f1eaf40acd928d8fb52cdca0f6db3a3d165d.nq.gz
│   ├── 9d856d9f88720a6492d1821bb8f29c4f509a7d02.nq.gz
│   ├── ae9988e95712486db2471f069d07fb12a3be520f.nq.gz
│   ├── b39114897eca5711e4058695fc5e172a93a31b61.nq.gz
│   ├── be53afa5d35be8c7e612e8c147e1cf881f05fc5d.nq.gz
│   ├── c811e9c92c9af1be3ea5af1d1b73c911e73a5a95.nq.gz
│   ├── c9792ba29d7ea560244aed86bd4f1e6c76fcd37d.nq.gz
│   ├── ce1b01a5b115e9a2ce6dc2f8bf6b0574d271ba98.nq.gz
│   ├── d41a94043c43d58b1c21d58399d4cc5eaf2a2606.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e8d119b19f40d0afad2c41f3314ce093be7985df.nq.gz
│   ├── fd64c29d99e731a4a9aa14f86d5fa71b80fa1677.nq.gz
│   ├── ffa15c695624fb67a4d51a56281db759a4715973.nq.gz
│   └── fffdcbbe2f144e6cfe762f1037473d5ef84e3805.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ec8768016be115d5ff4dbad6981c916423debe97.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[florimondmanca/arel](https://github.com/florimondmanca/arel)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
