# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b718`
- end: `0x18000b7b6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008ea8`
- `0x180009278`
- `0x18000a390`
- `0x18000d274`
- `0x18000ed3c`

## callees

- `0x18000b718`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b761`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b761`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b776`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b776`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b73d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b73d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b72c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b72c`

## string_xrefs

- `0x18000b75a`: `ntdll.dll`

## pseudocode

```c

```
