# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800081c8`
- end: `0x18000825e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000756c`
- `0x180007f3c`
- `0x1800085f0`
- `0x180008988`
- `0x1800204cc`
- `0x1800234cc`

## callees

- `0x180005f78`
- `0x1800081c8`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008211`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008211`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800081ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800081ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081dc`

## string_xrefs

- `0x18000820a`: `ntdll.dll`

## pseudocode

```c

```
