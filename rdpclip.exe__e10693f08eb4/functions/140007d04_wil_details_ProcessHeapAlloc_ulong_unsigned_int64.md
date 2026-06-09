# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140007d04`
- end: `0x140007da2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007ba0`
- `0x140008200`
- `0x140008378`

## callees

- `0x140007d04`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007d62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007d62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007d4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007d4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007d29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007d29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007d18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007d18`

## string_xrefs

- `0x140007d46`: `ntdll.dll`

## pseudocode

```c

```
