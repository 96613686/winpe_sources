# OpenSharedFileMapping(ushort const *,ulong,void * *,ulong)

- ea: `0x18000a9e0`
- end: `0x18000aaa7`
- name: `?OpenSharedFileMapping@@YAPEAXPEBGKPEAPEAXK@Z`
- size: `199`
- prototype: `void *__fastcall(const wchar_t *ppv, unsigned int pszName, void **ulMapSize, unsigned int ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a398`

## callees

- `0x18000a9e0`
- `0x180046f80`
- `0x1800742f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa62`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000aa21`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000aa21`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000a9ff`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000a9ff`

## string_xrefs

- `0x18000aa46`: `onecore\internal\com\inc\combase\smcreate.hxx`
- `0x18000aa87`: `onecore\internal\com\inc\combase\smcreate.hxx`

## pseudocode

```c

```
