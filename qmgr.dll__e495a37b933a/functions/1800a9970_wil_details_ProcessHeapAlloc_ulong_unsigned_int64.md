# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800a9970`
- end: `0x1800a9a0e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18009b40c`
- `0x1800a94ac`
- `0x1800a95d0`
- `0x1800aa6e4`
- `0x1800aa918`

## callees

- `0x1800a9970`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a99ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a99ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a99b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a99b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9995`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9995`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a9984`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a9984`

## string_xrefs

- `0x1800a99b2`: `ntdll.dll`

## pseudocode

```c

```
