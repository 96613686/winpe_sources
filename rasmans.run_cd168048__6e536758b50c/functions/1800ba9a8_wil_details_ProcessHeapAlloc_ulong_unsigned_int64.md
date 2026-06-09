# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800ba9a8`
- end: `0x1800baa5f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800b4ea0`
- `0x1800b524c`
- `0x1800bcad8`
- `0x1800bdd68`

## callees

- `0x1800ba9a8`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ba9d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ba9d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ba9bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ba9bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ba9fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ba9fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800baa18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800baa18`

## string_xrefs

- `0x1800ba9f6`: `ntdll.dll`

## pseudocode

```c

```
