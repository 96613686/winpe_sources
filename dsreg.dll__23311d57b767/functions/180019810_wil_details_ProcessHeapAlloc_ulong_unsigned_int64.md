# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180019810`
- end: `0x1800198ae`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001832c`
- `0x180019768`
- `0x18004e430`
- `0x18004e560`
- `0x18004fe34`
- `0x1800501f8`

## callees

- `0x180019810`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001986e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001986e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019859`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019859`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019824`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019824`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019835`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019835`

## string_xrefs

- `0x180019852`: `ntdll.dll`

## pseudocode

```c

```
