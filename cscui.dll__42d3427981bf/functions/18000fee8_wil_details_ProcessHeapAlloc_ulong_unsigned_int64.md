# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000fee8`
- end: `0x18000ff7e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a40c`
- `0x18000a560`
- `0x180010184`
- `0x1800102c0`
- `0x18002cc28`

## callees

- `0x18000e4f8`
- `0x18000fee8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ff31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ff31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fefc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fefc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ff0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ff0d`

## string_xrefs

- `0x18000ff2a`: `ntdll.dll`

## pseudocode

```c

```
