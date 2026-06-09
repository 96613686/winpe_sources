# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001e4ac`
- end: `0x18001e54d`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `161`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011e80`
- `0x18001e3c0`
- `0x18001fdc4`
- `0x180020694`
- `0x18002078c`
- `0x180020968`
- `0x18003d7dc`
- `0x18003dd70`
- `0x18003e108`
- `0x18003fab8`

## callees

- `0x18001e4ac`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e529`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e529`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e514`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e514`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e4d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e4d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e4c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e4c0`

## string_xrefs

- `0x18001e50d`: `ntdll.dll`

## pseudocode

```c

```
