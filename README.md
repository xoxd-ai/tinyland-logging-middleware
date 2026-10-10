# @tummycrypt/tinyland-logging-middleware (retired)

This repository is retired and archived (2026-10-10, estate uplift rulings
RU2, RU6, RU7, RU8).

Its code now lives in
[xoxd-ai/tinyland-logging](https://github.com/xoxd-ai/tinyland-logging) as
the `./middleware` subpath export of `@tummycrypt/tinyland-logging`, starting
with tinyland-logging 1.3.0. The API is unchanged: `configure`, `getConfig`,
`resetConfig`, `getNoopLogger`, `loggingMiddleware`, `createLogger`,
`createScopedLogger` and the `LogLevel`, `LogContext`, `Logger` and
`LoggingMiddlewareConfig` types.

## Migrating

1. In `MODULE.bazel`, replace
   `bazel_dep(name = "tummycrypt_tinyland_logging_middleware", ...)` with
   `bazel_dep(name = "tummycrypt_tinyland_logging", version = "1.3.0")`
   from [xoxd-ai/bazel-registry](https://github.com/xoxd-ai/bazel-registry),
   and link `@tummycrypt_tinyland_logging//:pkg` with `npm_link_package`.
2. Change imports (and `vi.mock` targets) from
   `@tummycrypt/tinyland-logging-middleware` to
   `@tummycrypt/tinyland-logging/middleware`. Use the subpath: the root
   entry of `@tummycrypt/tinyland-logging` exports different `LogLevel`,
   `LogContext`, `getNoopLogger` and `createScopedLogger`.

The registry module `tummycrypt_tinyland_logging_middleware` is marked
deprecated. Its 0.2.2 and 0.2.3 entries stay resolvable and nothing is
yanked, so existing pins keep building until they move. The package is no
longer published to npm or GitHub Packages; the publish workflow is removed.
