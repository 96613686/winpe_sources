# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006064`
- end: `0x180006102`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005ecc`
- `0x1800066d0`
- `0x180006a68`

## callees

- `0x180006064`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800060c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800060c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800060ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800060ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006078`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006078`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006089`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006089`

## string_xrefs

- `0x1800060a6`: `ntdll.dll`

## pseudocode

```c

```
