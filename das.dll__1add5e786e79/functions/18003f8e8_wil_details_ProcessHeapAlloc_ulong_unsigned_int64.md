# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003f8e8`
- end: `0x18003f986`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002de80`
- `0x18003f27c`
- `0x18003f3ac`
- `0x18004043c`
- `0x1800408c0`

## callees

- `0x18003f8e8`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003f946`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003f946`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003f931`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003f931`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f8fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f8fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f90d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f90d`

## string_xrefs

- `0x18003f92a`: `ntdll.dll`

## pseudocode

```c

```
