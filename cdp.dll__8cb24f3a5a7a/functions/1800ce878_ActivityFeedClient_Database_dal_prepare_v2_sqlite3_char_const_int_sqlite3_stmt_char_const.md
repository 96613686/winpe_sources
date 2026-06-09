# ActivityFeedClient::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)

- ea: `0x1800ce878`
- end: `0x1800cea15`
- name: `?dal_prepare_v2@Database@ActivityFeedClient@@CAXPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z`
- size: `413`
- prototype: `void __fastcall(struct sqlite3 *, const char *, int, struct sqlite3_stmt **, const char **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800ce730`

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800ce878`
- `0x1800ced7c`
- `0x1801135bc`
- `0x180143248`
- `0x1801fcb36`
- `0x1803078fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce9ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce9ad`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800ce8b1`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800ce942`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800ce94f`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800ce8b1`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800ce942`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800ce94f`
- `winsqlite3!sqlite3_prepare_v2` at `0x1800ce8d9`
- `winsqlite3!sqlite3_prepare_v2` at `0x1800ce8d9`

## string_xrefs

- `0x1800ce9d3`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c

```
