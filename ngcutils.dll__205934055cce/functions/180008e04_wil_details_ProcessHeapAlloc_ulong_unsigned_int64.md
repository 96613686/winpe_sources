# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008e04`
- end: `0x180008ea2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006ce8`
- `0x1800070c4`
- `0x180007e10`
- `0x18000a6a4`
- `0x18000bf4c`

## callees

- `0x180008e04`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008e4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008e4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008e62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008e62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e18`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e29`

## string_xrefs

- `0x180008e46`: `ntdll.dll`

## pseudocode

```c

```
