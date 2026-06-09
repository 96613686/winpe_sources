# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180022850`
- end: `0x1800228ee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021234`
- `0x180021604`
- `0x180022160`
- `0x180023af8`
- `0x1800247fc`

## callees

- `0x180022850`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022899`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022899`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800228ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800228ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022864`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022864`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022875`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022875`

## string_xrefs

- `0x180022892`: `ntdll.dll`

## pseudocode

```c

```
