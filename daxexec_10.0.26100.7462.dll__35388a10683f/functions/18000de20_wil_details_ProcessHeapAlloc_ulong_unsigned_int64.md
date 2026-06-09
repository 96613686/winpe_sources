# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000de20`
- end: `0x18000ded7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c93c`
- `0x18000d564`
- `0x18000e360`
- `0x18000eaa4`
- `0x18001628c`
- `0x180021378`

## callees

- `0x18000de20`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000de90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000de90`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000de75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000de75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000de4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000de4b`

## string_xrefs

- `0x18000de6e`: `ntdll.dll`

## pseudocode

```c

```
