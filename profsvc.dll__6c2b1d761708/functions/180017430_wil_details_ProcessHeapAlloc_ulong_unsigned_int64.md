# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180017430`
- end: `0x1800174ea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `186`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014c90`
- `0x180016ea0`
- `0x1800177c0`
- `0x1800229f4`
- `0x1800232b8`
- `0x1800233b0`
- `0x180023598`
- `0x18003edf8`
- `0x18003f3a4`
- `0x18003f758`
- `0x18004129c`

## callees

- `0x180017430`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800174c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800174c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800174a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800174a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001745b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001745b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017444`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017444`

## string_xrefs

- `0x18001749e`: `ntdll.dll`

## pseudocode

```c

```
