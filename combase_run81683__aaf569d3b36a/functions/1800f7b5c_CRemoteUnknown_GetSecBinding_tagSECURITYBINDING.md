# CRemoteUnknown::GetSecBinding(tagSECURITYBINDING * *)

- ea: `0x1800f7b5c`
- end: `0x1800f7f33`
- name: `?GetSecBinding@CRemoteUnknown@@AEAAJPEAPEAUtagSECURITYBINDING@@@Z`
- size: `983`
- prototype: `HRESULT __fastcall(CRemoteUnknown *this, tagSECURITYBINDING **pSecBind)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031554`
- `0x1801749c8`

## callees

- `0x1800188a0`
- `0x18004768c`
- `0x18008db2c`
- `0x1800f7b5c`
- `0x180153648`
- `0x180179024`
- `0x1801999b0`
- `0x1802135dd`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7d88`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f7ea7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f7ea7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f7d51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f7d51`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800f7cf8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800f7cf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7c56`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7c56`

## string_xrefs

- `0x1800f7cae`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800f7f21`: `onecore\com\combase\dcomrem\remoteu.cxx`
- `0x1800f7c4f`: `comsvcs.dll`
- `0x1800f7cef`: `comsvcs.dll`
- `0x1800f7e47`: `\\\Thread to thread`

## pseudocode

```c

```
