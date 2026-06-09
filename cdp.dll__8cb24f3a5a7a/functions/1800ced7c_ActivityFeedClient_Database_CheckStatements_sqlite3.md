# ActivityFeedClient::Database::CheckStatements(sqlite3 *)

- ea: `0x1800ced7c`
- end: `0x1800cee6b`
- name: `?CheckStatements@Database@ActivityFeedClient@@CAXPEAUsqlite3@@@Z`
- size: `239`
- prototype: `void __fastcall(struct sqlite3 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ce878`
- `0x1800ceb88`

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800ced7c`
- `0x180143248`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cee03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cee03`
- `winsqlite3!sqlite3_next_stmt` at `0x1800ced9d`
- `winsqlite3!sqlite3_next_stmt` at `0x1800cedc4`
- `winsqlite3!sqlite3_next_stmt` at `0x1800ced9d`
- `winsqlite3!sqlite3_next_stmt` at `0x1800cedc4`
- `winsqlite3!sqlite3_stmt_busy` at `0x1800cedae`
- `winsqlite3!sqlite3_stmt_busy` at `0x1800cedae`

## string_xrefs

- `0x1800cee29`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c

```
