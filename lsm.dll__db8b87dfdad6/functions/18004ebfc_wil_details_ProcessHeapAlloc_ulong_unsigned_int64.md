# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004ebfc`
- end: `0x18004ec9a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180046154`
- `0x18004e6d4`
- `0x18004ea58`
- `0x18004f0e0`
- `0x18004f478`

## callees

- `0x18004ebfc`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004ec5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004ec5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004ec45`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004ec45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ec21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ec21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ec10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ec10`

## string_xrefs

- `0x18004ec3e`: `ntdll.dll`

## pseudocode

```c

```
