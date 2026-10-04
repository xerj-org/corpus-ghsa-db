# corpus-ghsa-db

GitHub-reviewed security advisories, mirrored as a reference corpus for
retrieval evaluation. Unofficial mirror — not affiliated with GitHub. The
authoritative source is [github/advisory-database](https://github.com/github/advisory-database).

## Scope — exactly what this contains

The **`advisories/github-reviewed/` subtree only** of
github/advisory-database @ `4b4ac300e0f6718d5e56e9a410069894c3a22cb7`
(2026-10-03). 36,263 advisory JSON files, byte-verbatim, in the upstream
layout `github-reviewed/<year>/<month>/<GHSA-id>.json`.

Deliberately excluded: `advisories/unreviewed/` (343,910 auto-generated,
unreviewed entries at the same pin). The corpus domain — per the XERJ hub
registry — is *GitHub-reviewed advisories with CVSS and patched ranges*;
the unreviewed half is machine-generated from ecosystem diffs, has no
GitHub review, and diluted nothing but the index build time (measured:
the unscoped walk projected ~36 h). Anyone wanting it can clone upstream.

## Why a mirror instead of the upstream pin

`xerj corpus index` walks every file under the corpus root; the manifest
format cannot carry a subpath scope, so reproducing this corpus from the
upstream sha alone would index all 380 k files. This mirror makes
`xerj corpus add --from hub/ghsa-db.json` reproduce exactly this scope.

## Licence

The advisory data is licensed by its authors under **CC-BY-4.0** (upstream
`LICENSE.md`: "The advisories in this database are made available under
the Creative Commons Attribution 4.0 license"). Attribution: the GitHub
Advisory Database and the original advisory authors named in each record.
This mirror adds no rights and claims none.

## Refresh

Upstream updates continuously; re-pin by copying `advisories/github-reviewed`
from a fresh clone and committing (upstream rewrites advisory files in
place — a refresh rewrites history-free additive months plus edits).
