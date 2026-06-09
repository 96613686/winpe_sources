# ActivityFeedClient::Database::dal_exec(sqlite3 *,char const *,int (*)(void *,int,char * *,char * *),void *,char * *)

- ea: `0x1800ceb88`
- end: `0x1800ced76`
- name: `?dal_exec@Database@ActivityFeedClient@@CAXPEAUsqlite3@@PEBDP6AHPEAXHPEAPEAD3@Z23@Z`
- size: `494`
- prototype: `void __fastcall(struct sqlite3 *, const char *, int (*)(void *, int, char **, char **), void *, char **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800cea20`

## callees

- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800ceb88`
- `0x1800ced7c`
- `0x1801135bc`
- `0x180143248`
- `0x1801fcb36`
- `0x1803079b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ced00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ced00`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800cebc0`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800cec82`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800ceca2`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800cebc0`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800cec82`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800ceca2`
- `winsqlite3!sqlite3_exec` at `0x1800cebf4`
- `winsqlite3!sqlite3_exec` at `0x1800cebf4`
- `winsqlite3!sqlite3_free` at `0x1800cec7a`
- `winsqlite3!sqlite3_free` at `0x1800ced6b`
- `winsqlite3!sqlite3_free` at `0x1800cec7a`
- `winsqlite3!sqlite3_free` at `0x1800ced6b`

## string_xrefs

- `0x1800ced26`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c

```
