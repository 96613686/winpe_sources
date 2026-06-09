# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000f150`
- end: `0x18000f1ee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002d90`
- `0x180007ab0`
- `0x180008180`
- `0x18002e024`
- `0x18002e640`
- `0x18002e9d8`
- `0x180030f60`

## callees

- `0x18000f150`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f1df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f1df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f199`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f199`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f175`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f175`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f164`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f164`

## string_xrefs

- `0x18000f192`: `ntdll.dll`

## pseudocode

```c

```
