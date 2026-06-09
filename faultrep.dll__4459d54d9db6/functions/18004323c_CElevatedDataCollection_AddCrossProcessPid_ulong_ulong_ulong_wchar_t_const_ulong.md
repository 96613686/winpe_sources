# CElevatedDataCollection::AddCrossProcessPid(ulong,ulong,ulong,wchar_t const *,ulong)

- ea: `0x18004323c`
- end: `0x1800434a3`
- name: `?AddCrossProcessPid@CElevatedDataCollection@@QEAAJKKKPEB_WK@Z`
- size: `615`
- prototype: `__int64 __fastcall(CElevatedDataCollection *this, DWORD dwProcessId, int, int, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180044b44`
- `0x180045774`

## callees

- `0x180003617`
- `0x180004c92`
- `0x180004ee1`
- `0x180009ed8`
- `0x180009f00`
- `0x180038c0c`
- `0x18004323c`
- `0x180045dd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043471`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043471`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043484`

## string_xrefs

- `0x18004326f`: `Attempting to cross-proc reporting process!`
- `0x18004339d`: `Open process failed unexpectedly: 0X%X`

## pseudocode

```c

```
