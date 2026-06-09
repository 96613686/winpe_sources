# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180082db8`
- end: `0x180082e4e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `10`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180082c94`
- `0x1800830bc`
- `0x180083234`
- `0x180089670`
- `0x1800c28f0`
- `0x1800c2f40`
- `0x1800c37c0`
- `0x1800c3c90`
- `0x1801289f0`
- `0x18012e540`

## callees

- `0x1800811d0`
- `0x180082db8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180082e01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180082e01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082ddd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082ddd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082dcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082dcc`

## string_xrefs

- `0x180082dfa`: `ntdll.dll`

## pseudocode

```c

```
