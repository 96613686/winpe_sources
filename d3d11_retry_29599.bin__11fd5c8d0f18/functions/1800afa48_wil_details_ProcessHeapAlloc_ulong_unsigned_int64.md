# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800afa48`
- end: `0x1800afade`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800a7828`
- `0x1800a797c`
- `0x1800b0b48`
- `0x1800b48d0`
- `0x1800b49bc`

## callees

- `0x1800acb80`
- `0x1800afa48`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800afa5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800afa5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800afa6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800afa6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800afa91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800afa91`

## string_xrefs

- `0x1800afa8a`: `ntdll.dll`

## pseudocode

```c

```
