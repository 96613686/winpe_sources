# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800f1554`
- end: `0x1800f15f4`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `160`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800f1404`
- `0x1800f18f4`
- `0x1800f1c8c`

## callees

- `0x1800ef730`
- `0x1800f1554`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f15a7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f15a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f1572`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f1572`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f1583`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f1583`

## string_xrefs

- `0x1800f15a0`: `ntdll.dll`

## pseudocode

```c

```
