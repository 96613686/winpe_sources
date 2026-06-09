# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006f9c`
- end: `0x180007032`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006c28`
- `0x180007848`
- `0x180007be0`
- `0x18001b634`
- `0x18001d040`

## callees

- `0x1800044f8`
- `0x180006f9c`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fe5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006fb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006fb0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006fc1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006fc1`

## string_xrefs

- `0x180006fde`: `ntdll.dll`

## pseudocode

```c

```
