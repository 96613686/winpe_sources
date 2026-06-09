# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000db5c`
- end: `0x18000dc13`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009fdc`
- `0x18000b3f8`
- `0x18000eac8`
- `0x180016708`
- `0x180019e24`

## callees

- `0x18000db5c`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dbb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dbb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dbcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dbcc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db70`

## string_xrefs

- `0x18000dbaa`: `ntdll.dll`

## pseudocode

```c

```
