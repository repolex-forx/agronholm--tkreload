# Repolex Knowledge Graph of agronholm/tkreload

RDF knowledge graph data for [agronholm/tkreload](https://github.com/agronholm/tkreload), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/tkreload
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2c7126b0946be2f903d9c80a169d0bf3061b1de6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2c7126b0946be2f903d9c80a169d0bf3061b1de6
│           └── chunk-001.nq.gz
├── blob
│   ├── 031771ed5e36f1d08db75c43422ed4bc397ccb20.nq.gz
│   ├── 0952af1f0ce17d9cf08a912946d747a37cdc60b1.nq.gz
│   ├── 1e8caf299261d6fc9a8a27193130736fb776bf6e.nq.gz
│   ├── 2b7bacbb2cf03dab89fc837f57e7e9e14a9f2c6f.nq.gz
│   ├── 2d757879c862567b001572a7839a77f62307179c.nq.gz
│   ├── 4434a355d7a51cba8dc9eb86267ed2543226c4ec.nq.gz
│   ├── 4800d63e90501eaebc4b16612fe201641c293af7.nq.gz
│   ├── 48d5f81fa422964dd1eea360efdecfc5dc9a6c87.nq.gz
│   ├── 55b6962b65f77364a8968f7eae4fc95a2da533b9.nq.gz
│   ├── 5d3171a1b31a7c386c61a7719830e07953f8211a.nq.gz
│   ├── 630ab8b547666120d70eefdfb13878ffa4e2744e.nq.gz
│   ├── 680b761a8e70bf9ba96e27186b788cd4a1bb29e8.nq.gz
│   ├── 795c2e6ee0c200bb18cf57d5a0b43ae971c8a03c.nq.gz
│   ├── 83d6c547359de2b367d35aba9ed8c8328e1a0b72.nq.gz
│   ├── 8a8139f3cb6772790029c2ff1c2d791eb41b1deb.nq.gz
│   ├── 8dbd15d8c227dbdef686e3f7f794085c3b022cd3.nq.gz
│   ├── 92d030a7b28fca9f98bc27319eb2040aad54ab3c.nq.gz
│   ├── 93d4900012d82f304a2b63fc44dad05c57ca887b.nq.gz
│   ├── a1fe46da0ef844640945b053328e421eff4d9b4d.nq.gz
│   ├── a488c36dccd71c7d4c29130f8662c1196e7df6c3.nq.gz
│   ├── c4a11621a59f80b65e11ec21682c773114301a3d.nq.gz
│   ├── da7d4a3ee1eb34e850468239a36a9a472b77aee5.nq.gz
│   ├── de0db4ddf6c09eb7cebb1679b9cb65731baf6ed4.nq.gz
│   ├── e0c0168b23e551900ecd3aedeff668461b6f93c1.nq.gz
│   ├── e2bdc56d690d3fb2e17ccb9217710b3a51a8ff98.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e6b8ead6c48a4eeefb0d25ecea1168d838869027.nq.gz
│   └── fca690f7a6b66a6de0b57fef79434683c1ceab53.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2c7126b0946be2f903d9c80a169d0bf3061b1de6.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 34 files
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

[agronholm/tkreload](https://github.com/agronholm/tkreload)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
