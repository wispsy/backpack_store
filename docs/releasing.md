# Publishing Backpack Store

The 0.2.0 release contains the qualified SQLite application profile. PostgreSQL
work remains deferred; it is not a requirement for the Pretty Notebook framework
migration. The base runtime remains dependency-free on Python 3.11+.

1. Merge release preparation after passing cross-platform base, relational,
   process and Python 3.14 Enforce Type 0.2.0 checks.
2. Build wheel and source with `uv build`. Verify MIT metadata, version agreement,
   passive base imports, SQLite snapshots and isolated installed tests.
3. Create immutable annotated `v0.2.0` on the verified main revision. Publish its
   GitHub release to trigger `release.yaml`; the workflow reruns checks and passes
   its exact verified artifacts to the PyPI environment with OIDC.
4. Confirm publisher owner `wispsy`, repository `backpack_store`, workflow `release.yaml`
   and environment `pypi`. Verify registry file hashes and an uncached installation
   of `backpack-store[enforce-type]==0.2.0` on Python 3.14.
5. Attach those same workflow artifacts to the GitHub release and record receipts
   in REL-02 and the Backpack Project. Never replace a released tag or artifact.

Publication is separate from application deployment.

The repository was renamed from `backpack` to `backpack_store` after 0.2.0.
Before the next publication, update/verify the PyPI Trusted Publisher against
the new repository slug; GitHub URL redirects do not change that OIDC identity.
The published 0.2.0 artifacts and historical source pins remain immutable.
