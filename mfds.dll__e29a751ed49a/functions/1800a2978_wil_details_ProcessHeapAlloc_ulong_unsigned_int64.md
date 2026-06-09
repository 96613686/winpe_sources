# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800a2978`
- end: `0x1800a2a21`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18006d0f0`
- `0x1800a2fc4`
- `0x1800a3148`

## callees

- `0x18009b388`
- `0x1800a2978`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a29a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a29a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a298c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a298c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a29cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a29cd`

## string_xrefs

- `0x1800a29c6`: `ntdll.dll`

## pseudocode

```c

```
