# FAQ

## Is BikoDB production-ready?

Not as a general-purpose packaged database product yet.

The repo is strongest today as an embedded Rust graph runtime with additional document and vector capabilities. Several broader areas are still better described as experimental.

## What is the recommended way to try it today?

Use the Rust workspace directly:

```bash
cargo test --workspace
cargo build --workspace
```

Then start with the embedded `Database` API shown in the [quickstart](/guide/quickstart).

## Does BikoDB support full SQL, full Cypher, or full Gremlin?

No.

It supports documented subsets of each language. The goal of these docs is to make that boundary explicit instead of implying full compatibility.

## Are SQL and Cypher writes supported through the public query endpoint?

Not as a documented end-to-end public surface today.

The parsers contain mutation-related work, but the primary `Database` query dispatch path is currently read-oriented.

## Is there a standalone server binary?

Not as the main documented entry point today.

The repo includes an HTTP router library, but not a polished packaged server distribution with first-class deployment docs.

## Are graph transactions the same as cross-model transactions?

No.

A graph transaction implementation exists in `bikodb-graph`, but that should not be read as a full public transactional contract across graph, document, and vector subsystems.

## Are the benchmark comparisons fully audited?

Not yet.

BikoDB measurements are reproducible from the repo, but the current cross-database comparison still includes reference/approximate competitor values and should be treated accordingly.
