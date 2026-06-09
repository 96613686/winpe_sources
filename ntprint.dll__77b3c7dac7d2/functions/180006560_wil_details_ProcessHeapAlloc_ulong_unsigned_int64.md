# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006560`
- end: `0x1800065f6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006000`
- `0x180006164`
- `0x180007524`
- `0x180007758`
- `0x1800087fc`

## callees

- `0x180003578`
- `0x180006560`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800065a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800065a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006585`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006585`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006574`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006574`

## string_xrefs

- `0x1800065a2`: `ntdll.dll`

## pseudocode

```c

```
