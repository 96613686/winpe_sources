# APP_POOL_ISOLATION::GetTemplateFileBuffer(MULTISZ *,ushort const *,AUTO_GROWING_BUFFER * *)

- ea: `0x18000d084`
- end: `0x18000d297`
- name: `?GetTemplateFileBuffer@APP_POOL_ISOLATION@@CAJPEAVMULTISZ@@PEBGPEAPEAVAUTO_GROWING_BUFFER@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(struct MULTISZ *, LPCWSTR lpFileName, struct AUTO_GROWING_BUFFER **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000d8a4`

## callees

- `0x180001234`
- `0x180008048`
- `0x18000832c`
- `0x180008cb4`
- `0x180009104`
- `0x18000d084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d10f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d231`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d26c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d231`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d26c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d0f3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d0f3`

## pseudocode

```c

```
