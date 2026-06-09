# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180048f08`
- end: `0x180048f9e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180048d08`
- `0x180049214`
- `0x180049350`
- `0x180052040`
- `0x1800536b0`

## callees

- `0x180046ef4`
- `0x180048f08`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048f1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048f1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180048f51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180048f51`

## string_xrefs

- `0x180048f4a`: `ntdll.dll`

## pseudocode

```c

```
