# Repolex Knowledge Graph of apple/ccs-pykerberos

RDF knowledge graph data for [apple/ccs-pykerberos](https://github.com/apple/ccs-pykerberos), parsed by [repolex](https://repolex.ai).

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
rlex download apple/ccs-pykerberos
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 32ff1211fc1866ab33bbfbcf27d5e522bf0bb593
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 32ff1211fc1866ab33bbfbcf27d5e522bf0bb593
│           └── chunk-001.nq.gz
├── blob
│   ├── 08703e1561eb8b4b25513eaa32afed2bdf41daae.nq.gz
│   ├── 1e889dfd537d4344f08f19e553a18caa15d1c06d.nq.gz
│   ├── 21c59122155a44737c64ad604014285fd84b1ec6.nq.gz
│   ├── 250f2d5346c2e03122ff76d0750c8e2868215ede.nq.gz
│   ├── 2ccbc0ebf4e7fedf4c524bfb5a11ae511fcbbd65.nq.gz
│   ├── 362040d98746b535a629b571ffa33683be6c7c88.nq.gz
│   ├── 372ccf7a4099bb1067bf68f9fb2285f56b41c351.nq.gz
│   ├── 39d92ed762ebbf0b200c7eac1cc7e58efee4368c.nq.gz
│   ├── 4496f92e24f2542b599124ca6d007ccda3c244fb.nq.gz
│   ├── 46487bb6e93d17f43a18d7df36756500af0e4676.nq.gz
│   ├── 4b51fd89f8d548f9b6700e6db97988fa37417a2b.nq.gz
│   ├── 4ddff3e3339977f4e1f8d00aa311099376baea9a.nq.gz
│   ├── 5dc73ac762775e9e2dc816d4ce8de62e9003068a.nq.gz
│   ├── 6004e37499b46a1730374b69b1d98e557fe1a0be.nq.gz
│   ├── 62a6249f19bc204d1d2fd607ea867b797c9fdae9.nq.gz
│   ├── 7dec520273bbbb60d650ae6973e058465b95ad87.nq.gz
│   ├── 81c2180a00eefc112cffce3cba2e516cce7593b9.nq.gz
│   ├── 83c1b721f1dee6e6e33680e0a544510e683c2dbb.nq.gz
│   ├── 8bc0c4f6a0552ff1635874127120327722547b2b.nq.gz
│   ├── 935bfec190e71706b704aeefd227d0e4bf2e50fe.nq.gz
│   ├── 9a0dfa7f78a4f17d04e3d1bfe54a02e6c2ff48b0.nq.gz
│   ├── 9fbd9224cc1af081d56b52e840ec6ea82d396a3a.nq.gz
│   ├── a37e16adb445fd4a26d3ce86b749de386b3d32f1.nq.gz
│   ├── a46d695ce9b2887dece4742665adc0f83c701de6.nq.gz
│   ├── c558234e43cea6768d2b56599509640aecce1fd6.nq.gz
│   ├── c82a5e4390166dcc2bd903b69d2f17fed0a9b974.nq.gz
│   ├── d4f53a6bcfe05e611929e885704509e9deec3431.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e6abc0d8ad8ea71a48c2ffa13488d4412938a49b.nq.gz
│   └── f6546fc3c71147ab9e7715254654e20520425fbc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 32ff1211fc1866ab33bbfbcf27d5e522bf0bb593.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[apple/ccs-pykerberos](https://github.com/apple/ccs-pykerberos)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
