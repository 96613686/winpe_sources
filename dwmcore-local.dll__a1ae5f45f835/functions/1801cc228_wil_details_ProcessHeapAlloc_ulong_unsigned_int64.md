# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1801cc228`
- end: `0x1801cc2c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1801cbf20`
- `0x1801cc180`
- `0x18022b1b4`
- `0x18022b8ec`
- `0x18022ba64`

## callees

- `0x1801cc228`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801cc271`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801cc271`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801cc2b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801cc2b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801cc23c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801cc23c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801cc24d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801cc24d`

## string_xrefs

- `0x1801cc26a`: `ntdll.dll`

## pseudocode

```c

```
