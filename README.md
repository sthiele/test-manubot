# Output directory containing the formatted manuscript

The [`gh-pages`](https://github.com/cnapy-org/CNApy-guide/tree/gh-pages) branch hosts the contents of this directory at <https://cnapy-org.github.io/CNApy-guide/>.
The permalink for this webpage version is <https://cnapy-org.github.io/CNApy-guide/v/323a3c8e7e23e3aa5649edfa7b5a5b2e1037c113/>.
To redirect to the permalink for the latest manuscript version at anytime, use the link <https://cnapy-org.github.io/CNApy-guide/v/freeze/>.

## Files

This directory contains the following files, which are mostly ignored on the `main` branch:

+ [`index.html`](index.html) is an HTML manuscript.
+ [`manuscript.pdf`](manuscript.pdf) is a PDF manuscript.

The `v` directory contains directories for each manuscript version.
In general, a version is identified by the commit hash of the source content that created it.

### Timestamps

The `*.ots` files in version directories are OpenTimestamps which can be used to verify manuscript existence at or before a given time.
[OpenTimestamps](https://opentimestamps.org/) uses the Bitcoin blockchain to attest to file hash existence.
The `deploy.sh` script run during continuous deployment creates the `.ots` files through its `manubot webpage` call.
There is a delay before timestamps get confirmed by a Bitcoin block.
Therefore, `.ots` files are initially incomplete and should be upgraded at a later time, so that they no longer rely on the availability of a calendar server to verify.
The `manubot webpage` call during continuous deployment identifies files matched by `webpage/v/**/*.ots` and attempts to upgrade them.
You can also manually upgrade timestamps, by running the following in the `gh-pages` branch:

```shell
ots upgrade v/*/*.ots
rm v/*/*.ots.bak
git add v/*/*.ots
```

Verifying timestamps with the `ots verify` command requires running a local bitcoin node with JSON-RPC configured, at this time.

## Source

The manuscripts in this directory were built from
[`323a3c8e7e23e3aa5649edfa7b5a5b2e1037c113`](https://github.com/cnapy-org/CNApy-guide/commit/323a3c8e7e23e3aa5649edfa7b5a5b2e1037c113).
