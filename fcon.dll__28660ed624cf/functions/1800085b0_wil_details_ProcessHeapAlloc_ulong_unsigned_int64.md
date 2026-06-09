# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800085b0`
- end: `0x180008646`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000724c`
- `0x180007fd0`
- `0x180008134`
- `0x180009540`
- `0x1800099d0`
- `0x18000acbc`

## callees

- `0x180005064`
- `0x1800085b0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800085f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800085f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800085d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800085d5`

## string_xrefs

- `0x1800085f2`: `ntdll.dll`

## pseudocode

```c

```
