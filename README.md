# std Aware Cargo

This repo is a place to focus discussion and work on "`std` Aware Cargo". This
is a feature to allow users of [Cargo](https://github.com/rust-lang/cargo/) to
build the Rust standard library locally, instead of using the pre-built
artifacts shipped with Rust.

We plan to work on multiple RFCs, targeted to specific changes. Work on an
experimental implementation will also begin immediately to help work through
issues.

## Use Cases

It is possible that we will not address all of these use cases, but these are
some of the things we are thinking about.

1. Build the standard library with your project with custom profile settings.

   This allows you to use the standard library with different optimization
   levels, debug settings, etc. [See more.](https://github.com/rust-lang/wg-cargo-std-aware/issues/2)

2. Build the standard library (particularly libcore) for an unsupported
   target.

   [See more.](https://github.com/rust-lang/wg-cargo-std-aware/issues/3)

3. Build the standard library with different `cfg` settings.

   This may be used to disable parts of the standard library, or to select
   different behaviors. [See more.](https://github.com/rust-lang/wg-cargo-std-aware/issues/4)

4. Specify explicit dependencies on sysroot crates in `Cargo.toml`.

   Primarily this is to remove the need for `extern crate`. [See
   more.](https://github.com/rust-lang/wg-cargo-std-aware/issues/5)

## MVP Implementation

An initial version is available on the latest Rust nightly releases. This
version is very minimal, with a simple `-Z` flag to enable. There are a large
number of known issues with this implementation, and it is not intended to
work for all targets and should not be used for anything other than
experimentation and testing.

Documentation may be found at: https://doc.rust-lang.org/nightly/cargo/reference/unstable.html#build-std

## RFCs

It is yet to be determined exactly which RFCs will be written to cover the
enhancements we want to make. As a rough outline, the following are
possibilities:

- Syntax for specifying standard library dependencies in Cargo. [#5](https://github.com/rust-lang/wg-cargo-std-aware/issues/5)
- Standard library portability. [#8](https://github.com/rust-lang/wg-cargo-std-aware/issues/8)
- Target specification. [#6](https://github.com/rust-lang/wg-cargo-std-aware/issues/6)

## Getting involved

Everyone is encouraged to jump in to [the issue tracker
here](https://github.com/rust-lang/wg-cargo-std-aware/issues/) to discuss
specific points. If it looks like something is missing, feel free to open a
new issue or leave a comment.

At some point in the future, we will likely start working on the RFCs. If you
are interested in helping with that, follow and comment on [one of the
issues](https://github.com/rust-lang/wg-cargo-std-aware/issues?q=is%3Aopen+is%3Aissue+label%3ARFC).

Once implementations are available on nightly, helping to test it out is very
valuable.

The Cargo team can also be reached on [#t-cargo on
Zulip](https://rust-lang.zulipchat.com/#narrow/stream/246057-t-cargo).

## History

There have been various requests and efforts over the years to define `std`
Aware Cargo and to support building the standard library:

- [RFC 1133 proposal](https://github.com/rust-lang/rfcs/pull/1133)
- [RFC 2663 proposal](https://github.com/rust-lang/rfcs/pull/2663)
    - [Pre-RFC discussion](https://github.com/jamesmunns/rfcs/pull/1)
- [#4959](https://github.com/rust-lang/cargo/issues/4959) — RFE to add Xargo to Cargo
- [#5002](https://github.com/rust-lang/cargo/issues/5002) — Explicit standard
  library dependencies
- [#5003](https://github.com/rust-lang/cargo/issues/5003) — Implicit standard
  library dependencies
- [Xargo](https://github.com/japaric/xargo)
- [cargo-xbuild](https://github.com/rust-osdev/cargo-xbuild)
