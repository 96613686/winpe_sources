# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006e70`
- end: `0x180006f06`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(unsigned int flags, unsigned __int64 size)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006bc8`
- `0x1800072a0`
- `0x180007638`
- `0x18005b7f0`
- `0x18005e518`

## callees

- `0x180004be0`
- `0x180006e70`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006eb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006eb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006e95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006e95`

## string_xrefs

- `0x180006eb2`: `ntdll.dll`

## pseudocode

```c

```
