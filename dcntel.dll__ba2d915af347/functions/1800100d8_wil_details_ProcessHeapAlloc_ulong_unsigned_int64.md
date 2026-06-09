# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800100d8`
- end: `0x180010176`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d7a8`
- `0x18000db78`
- `0x18000ecb0`
- `0x18000f3d0`
- `0x180011dd4`
- `0x18001398c`

## callees

- `0x1800100d8`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010136`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010136`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010121`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010121`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800100fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800100fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800100ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800100ec`

## string_xrefs

- `0x18001011a`: `ntdll.dll`

## pseudocode

```c

```
