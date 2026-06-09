# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010fe8`
- end: `0x18001107e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010b1c`
- `0x180010c70`
- `0x180011cf0`
- `0x180012174`
- `0x1800130c8`

## callees

- `0x18000df58`
- `0x180010fe8`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011031`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011031`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001100d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001100d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010ffc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010ffc`

## string_xrefs

- `0x18001102a`: `ntdll.dll`

## pseudocode

```c

```
