# Repolex Knowledge Graph of pydantic/pytest-examples

RDF knowledge graph data for [pydantic/pytest-examples](https://github.com/pydantic/pytest-examples), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/pytest-examples
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── df945f7043cb8c456359b01700f3d664d30fbe44
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── df945f7043cb8c456359b01700f3d664d30fbe44
│           └── chunk-001.nq.gz
├── blob
│   ├── 04a26fda00ab384d5ee49c3559984c8daba594d5.nq.gz
│   ├── 1cf7b2fd3ffd7bf441a56b3cd392b9449a60de45.nq.gz
│   ├── 310e9b05b7f4260549b6e4809cf589da10b845a6.nq.gz
│   ├── 32783a599bd280317fdb1ce5d9ea3399f8840b63.nq.gz
│   ├── 34bf14a8e0a4bc07bc72483ad9691d82d604a021.nq.gz
│   ├── 37f8a9fec2dd230850eece0f260ab8c7a2483436.nq.gz
│   ├── 4c3a5bce748421f1987b00f9237c2c1f8e69ebf8.nq.gz
│   ├── 4e99a4e333088c274bcacca8d947f53c88e99e69.nq.gz
│   ├── 529141124e4890c97be50295e9bf0884caa1e2f3.nq.gz
│   ├── 55390a4c488b74b82fed4429053acc26bdf46dad.nq.gz
│   ├── 5751df38ed25870f2794655968e0462f0a9a423f.nq.gz
│   ├── 5bd55d3f3945c1c274e5b19fcff3590824c22bda.nq.gz
│   ├── 6550b665ca3f7f1411f34b65cb2f2e99e729c4bf.nq.gz
│   ├── 6c1c13702acaa92c9a1fa1d70ced435140f97506.nq.gz
│   ├── 6f08de4d721826308f38fdfa17b886dee1e94a48.nq.gz
│   ├── 76a16c134961cb00a726a8d7d31cc5c856eec22d.nq.gz
│   ├── 78fc17b716d84639b174370d86601b77ed701dfc.nq.gz
│   ├── 7df4a07be0b4aff32743b9ee55202d2f0ec9061b.nq.gz
│   ├── 7e2ab69757c04153bb1b926141af9f27d25b8779.nq.gz
│   ├── 873d9a18171f344272e4ab994a40fbecba9c6ec7.nq.gz
│   ├── 89ea18b9d993f23db7ac077a0d013ab54f6b94f9.nq.gz
│   ├── 8e913ad2e7eb1a90d8e3b9b82eca007ad244ffc1.nq.gz
│   ├── 90462b528928346aedbd774bddd6f241139b86aa.nq.gz
│   ├── 9861cfd377a5c8b396763f12edb40ffaecefdc4d.nq.gz
│   ├── a60b5be87f97cef216ce91314a29ab1e0378b810.nq.gz
│   ├── b42cb01c97f739da5d67a66119664f9d2ae223df.nq.gz
│   ├── b735bb17d4777f563505f20c07d04258f9496820.nq.gz
│   ├── cffb277bdb639982deb147f108715a0a32f5ddfe.nq.gz
│   ├── d4b4dbcb8c81a52e6a7866d97377f3205076c9f7.nq.gz
│   ├── da66b2c5333fe1a0e25b5afd53ac410ff3517ef0.nq.gz
│   ├── e2abbac8ff64e22c5be66280d6b8ea7bdab9bbc8.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e86e01d1d491a6586586bd0bfefa18af84b52f80.nq.gz
│   ├── e88cfa115d4c56898fefa1e47337f5940b24067d.nq.gz
│   └── f0865696f89d3a8ce3920d810acb4d4ac6d917a8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── df945f7043cb8c456359b01700f3d664d30fbe44.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 43 files
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

[pydantic/pytest-examples](https://github.com/pydantic/pytest-examples)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
