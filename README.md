# Repolex Knowledge Graph of Teemu/pytest-sugar

RDF knowledge graph data for [Teemu/pytest-sugar](https://github.com/Teemu/pytest-sugar), parsed by [repolex](https://repolex.ai).

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
rlex download Teemu/pytest-sugar
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 54ec9991e1e6e57a6fa4d70e5094797f6dc72f11
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 54ec9991e1e6e57a6fa4d70e5094797f6dc72f11
│           └── chunk-001.nq.gz
├── blob
│   ├── 095661302b2649b44f53a38f88c5529a49286c86.nq.gz
│   ├── 0e77752af777b30304003a5897893a029f88eef9.nq.gz
│   ├── 12df5d7282cda13fdca7a4cc2c87b4c8ddbc949b.nq.gz
│   ├── 1ab1569797fc7a4f36ccccca341076331d940109.nq.gz
│   ├── 227185986a6eb48282a66c00023c1a0eefb8b4ee.nq.gz
│   ├── 26c21ceace045bdfccf163e1c87574e324190b9b.nq.gz
│   ├── 2a24f4d455f2177ef232a85048df0054d5283dfe.nq.gz
│   ├── 2f61ac4a890b8011243a3b45d412ba452ad00d6f.nq.gz
│   ├── 3415dd4bbb315df42730e1abf8bec5c5dfdb9061.nq.gz
│   ├── 36132432410ec9809074f5545fc9f7e667e0e3d7.nq.gz
│   ├── 38538042c1b022833311b7a56d08a5c037bf6b09.nq.gz
│   ├── 3969bc1850771e51c784b1452cfba19059696f4a.nq.gz
│   ├── 3e6a89eff8c6e247a209fb867fb891f7ce33bc57.nq.gz
│   ├── 553b8f822db75d0c4caad7361a338532c04bbbce.nq.gz
│   ├── 57af4cdb4b2cbe90fc8095cd47be05db13f5ca81.nq.gz
│   ├── 5b4d2fb52b572150ab76d89b3f669156d6df71eb.nq.gz
│   ├── 5da0b10ddcc822faac109f4d524356ba0c0a214b.nq.gz
│   ├── 5e70986d5bb33c715ded1a837dae617ba2650074.nq.gz
│   ├── 64950822633bb4162e5ab7420d564638a71ac3e5.nq.gz
│   ├── 65a0c2e879b1f507869d56523ccacab4a9100b89.nq.gz
│   ├── 75c737c327c87e177d5609576306f1d68c19d916.nq.gz
│   ├── 795cdb7dbcdab310211ea4ce526a6423c9809f71.nq.gz
│   ├── 8150015ca5d2c88517e759790b7c2fc442b5ace6.nq.gz
│   ├── 835cfc02af99abae27990f77fe8382c52d7ceae8.nq.gz
│   ├── 84edea7ad103daf1a6d49f027e01bf3d86c485c9.nq.gz
│   ├── 8dd399ab55bce8a4a1ddfd0c98170f771f6e5c35.nq.gz
│   ├── 935a7dcfd1451cf2403719a1b2c5293d01374ada.nq.gz
│   ├── b125c0888b5555ed03ad5d9f9a89f3c4b23dfcc4.nq.gz
│   ├── c2fd88d15c39b29d29edeaea051e0da1c08cea15.nq.gz
│   ├── c684fae51a9fb3870800c4d39f134720821a1254.nq.gz
│   ├── cdc1f8cfe3fe01fbc8d780d14d1630212f040948.nq.gz
│   ├── db5bd8cfc468c44cef50f167a0a8f43fe2723e3b.nq.gz
│   ├── e78dd2089e996b4c0d7c2d7db4ea6e158f929172.nq.gz
│   ├── ebf3610cf9b124b8fbbcd9516455b1479fff44eb.nq.gz
│   ├── f2fc75b71141676ec0e32b19fcdd15912b1df1a8.nq.gz
│   ├── f4422b61865cdfb10ef0e638c8568f8a45fba77e.nq.gz
│   └── f8199f9813c4e387fbdff0313a36ee73c786bc6f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 54ec9991e1e6e57a6fa4d70e5094797f6dc72f11.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[Teemu/pytest-sugar](https://github.com/Teemu/pytest-sugar)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
