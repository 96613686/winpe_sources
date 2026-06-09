# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800520e8`
- end: `0x18005219f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800490b4`
- `0x180051b9c`
- `0x180051f40`
- `0x180052614`
- `0x1800529c8`

## callees

- `0x1800520e8`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052158`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052158`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005213d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005213d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052113`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052113`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800520fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800520fc`

## string_xrefs

- `0x180052136`: `ntdll.dll`

## pseudocode

```c

```
