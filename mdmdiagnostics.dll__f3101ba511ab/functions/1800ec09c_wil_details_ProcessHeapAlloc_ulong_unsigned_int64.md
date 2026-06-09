# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800ec09c`
- end: `0x1800ec145`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800eb924`
- `0x1800eba88`
- `0x1800ed524`
- `0x1800ed9d0`
- `0x1800f1ac0`

## callees

- `0x1800e489c`
- `0x1800ec09c`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ec0f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ec0f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ec0b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ec0b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ec0c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ec0c7`

## string_xrefs

- `0x1800ec0ea`: `ntdll.dll`

## pseudocode

```c

```
