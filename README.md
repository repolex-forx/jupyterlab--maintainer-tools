# Repolex Knowledge Graph of jupyterlab/maintainer-tools

RDF knowledge graph data for [jupyterlab/maintainer-tools](https://github.com/jupyterlab/maintainer-tools), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterlab/maintainer-tools
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9ef9d99e773be92f2d68ec6fe0f7bd47c14671a2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9ef9d99e773be92f2d68ec6fe0f7bd47c14671a2
│           └── chunk-001.nq.gz
├── blob
│   ├── 0977426d297ed9287fdd5b411f3b61f916610393.nq.gz
│   ├── 0cf675c4f0d6a11fc1379df8a728fe14b699487d.nq.gz
│   ├── 0fb3407be572582fb933bc9e8b7cf1f462cbe82e.nq.gz
│   ├── 178ffe7b5dc50453f227625bf8723ef99bc6d2fa.nq.gz
│   ├── 19368ba93294e25f41efd15fb2da381770963817.nq.gz
│   ├── 206699a64e6c5840afab5757fb108cfc9839c87b.nq.gz
│   ├── 21e368c6d58f33e82f9c651437d751163eb07276.nq.gz
│   ├── 236fdbdc1718e7df421b317e348011b03825252a.nq.gz
│   ├── 24406bdd02a62259f9bbe751d8d84eaf91048d0e.nq.gz
│   ├── 24418188f10c497c86debbe9487a46fa972aa304.nq.gz
│   ├── 26f5f7a11180658f5a0c15612b22448e7ac12e4f.nq.gz
│   ├── 284a6836871536cd977f6c0cfdcb93110b261cc2.nq.gz
│   ├── 2f3f947593887e1bf0cb2ff6b45d874335427cf7.nq.gz
│   ├── 440669357e61aac2f1cab224ab393619de2d476b.nq.gz
│   ├── 579192fcd226eeeceb08a7bd4c7d91c9b8987fbd.nq.gz
│   ├── 62d9dcff006bafcbe0665a470a6ba184c9de45eb.nq.gz
│   ├── 6946ae38ea75e93633fe52ed777514b77b1f85d7.nq.gz
│   ├── 6b07064805bff0593aed2af25cbfa65e6c310037.nq.gz
│   ├── 6fdef0e0fbb395e975aa2110f4d798f739debc3e.nq.gz
│   ├── 719d1481c2ff33a9f75a278ec5c670f77d2d7025.nq.gz
│   ├── 767c18f11d6e9734e23c1986045b26ef7d61f958.nq.gz
│   ├── 7f9c00b8f6fc4bb0e1e2ffe5958aa3c006697621.nq.gz
│   ├── 7fe156972fa6c4c79d0ba3186df360f64f9dfbad.nq.gz
│   ├── 82f8b847498d23c6b57ad2d3a034ab5e8a11a565.nq.gz
│   ├── 8acc3a6bc6b2fd2b42794d81c7a648b2e5d57074.nq.gz
│   ├── 9117380a396a69a7f8f53ddc48857e992963fc34.nq.gz
│   ├── 96ad971f2c60429885ad375355259c7ae7584252.nq.gz
│   ├── a49b7f5615c5f4c6fe9cfe9bc0450869e7cc2790.nq.gz
│   ├── c1bec448b1c3891d9ba5ccbdd5d48e29cdf6cb9f.nq.gz
│   ├── c2eaf46fb21af7df7477df3f0e52464486b81eb8.nq.gz
│   ├── cf9de5cd61471e9dfbab02a7d1ef910e09bf5e64.nq.gz
│   ├── d0cd8b7614178f46872f4752327270227bcbd642.nq.gz
│   ├── daeac30eaa610e1639ec4fdc7e73d2bbe3043d0b.nq.gz
│   ├── ddb5ab72a2b3b165214dfa17585d79858d512444.nq.gz
│   ├── e8e30235b2c60ca040dbfa04adafab8b53d0dba3.nq.gz
│   ├── f226ae7f865a7196f91bb1726aa12e278857a5f4.nq.gz
│   ├── f6a7d408400323e08ef36456fb454d5880d42fc9.nq.gz
│   └── ff6865f5f0dc0fb1bde03aac5977866ed6a4c7be.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9ef9d99e773be92f2d68ec6fe0f7bd47c14671a2.nq.gz
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

[jupyterlab/maintainer-tools](https://github.com/jupyterlab/maintainer-tools)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
