# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800ebbac`
- end: `0x1800ebc42`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800eb46c`
- `0x1800eb5d0`
- `0x1800ecf00`
- `0x1800ed390`
- `0x1800f1170`

## callees

- `0x1800e4770`
- `0x1800ebbac`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ebbf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ebbf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ebbc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ebbc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ebbd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ebbd1`

## string_xrefs

- `0x1800ebbee`: `ntdll.dll`

## pseudocode

```c

```
