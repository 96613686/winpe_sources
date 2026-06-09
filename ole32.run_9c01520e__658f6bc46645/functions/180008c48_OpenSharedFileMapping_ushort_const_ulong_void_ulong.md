# OpenSharedFileMapping(ushort const *,ulong,void * *,ulong)

- ea: `0x180008c48`
- end: `0x180008d4e`
- name: `?OpenSharedFileMapping@@YAPEAXPEBGKPEAPEAXK@Z`
- size: `262`
- prototype: `void *__fastcall(const wchar_t *ppv, unsigned int pszName, void **ulMapSize, unsigned int ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800087b4`

## callees

- `0x180008c48`
- `0x180045320`
- `0x18006c04c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008cfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cec`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180008c75`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180008c75`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180008c9f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180008c9f`

## string_xrefs

- `0x180008cd0`: `onecore\internal\com\inc\combase\smcreate.hxx`
- `0x180008d16`: `onecore\internal\com\inc\combase\smcreate.hxx`

## pseudocode

```c

```
