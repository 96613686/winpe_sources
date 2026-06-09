# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007cf8`
- end: `0x180007d96`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005cc8`
- `0x18000609c`
- `0x180006d90`
- `0x180009564`
- `0x18000ae9c`

## callees

- `0x180007cf8`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007d41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007d41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007d56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007d56`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d0c`

## string_xrefs

- `0x180007d3a`: `ntdll.dll`

## pseudocode

```c

```
