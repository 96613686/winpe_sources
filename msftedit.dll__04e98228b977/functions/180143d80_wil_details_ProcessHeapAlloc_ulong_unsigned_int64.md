# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180143d80`
- end: `0x180143e37`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1801438d0`
- `0x180143a30`
- `0x180144d08`
- `0x180144f44`
- `0x180145f2c`

## callees

- `0x180143d80`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180143df0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180143df0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180143dd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180143dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180143d94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180143d94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180143dab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180143dab`

## string_xrefs

- `0x180143dce`: `ntdll.dll`

## pseudocode

```c

```
