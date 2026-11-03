# termenbox bundle signing keys

These are the keys that sign the hosted termenbox client bundle and its installer. A bundle or installer is genuine only
if it is signed by one of the keys below. This file lives in an organisation that is separate from `termenbox/termenbox`,
so a break-in to the main organisation, GitHub Pages or Cloudflare cannot change it.

Last reviewed: 2026-11-03

## Stable channel

| Key id | Fingerprint | Held by |
|--------|-------------|---------|
| `bk1` | `SHA256:EcN+IBMm8lQWCl2JxgNA4ebTftzlxK2u3bp6P3PYO9g` | The owner, on a private machine, outside GitHub and Cloudflare |
| `bk2` | `SHA256:lfmv+huP625NbSM4qgP3na8YgOr+2dfK6cSxei0Gak4` | This repository's `signer` environment, signed only after the owner approves a run |

Beta and nightly bundles are not signed with these keys.

## How to check a key

Compare the fingerprint with the one the project ships. In a checkout of `termenbox/termenbox`:

```sh
```

The output must list exactly the two fingerprints above. Anything else, or a different number of keys, is wrong.
Do not install. Report it privately at https://github.com/termenbox/termenbox/security/advisories/new.

## How to install with a pinned key

Give the installer the fingerprint from this file, not from the main repository:

```sh
TERMENBOX_BUNDLE_FP=SHA256:lfmv+huP625NbSM4qgP3na8YgOr+2dfK6cSxei0Gak4 sh install.sh
```

The installer then accepts only a bundle signed by the key with that fingerprint.

## Changes to this file

A key is added, replaced or removed only in a pull request that says why. A fingerprint changed anywhere else is a
warning sign. The history of this file is the record of every key the project has trusted.
