# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180032690`
- end: `0x18003272e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f50c`
- `0x180032408`
- `0x180032ab0`
- `0x180032e48`
- `0x1800386ac`

## callees

- `0x180032690`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800326ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800326ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800326d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800326d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800326b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800326b5`

## string_xrefs

- `0x1800326d2`: `ntdll.dll`

## pseudocode

```c

```
