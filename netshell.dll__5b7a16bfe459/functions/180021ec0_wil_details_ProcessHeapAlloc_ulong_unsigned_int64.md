# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180021ec0`
- end: `0x180021f5e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019e44`
- `0x180021440`
- `0x180021c30`
- `0x180022340`
- `0x1800226d8`
- `0x180053df4`

## callees

- `0x180021ec0`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021f1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021f1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021f09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021f09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021ee5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021ee5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ed4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ed4`

## string_xrefs

- `0x180021f02`: `ntdll.dll`

## pseudocode

```c

```
