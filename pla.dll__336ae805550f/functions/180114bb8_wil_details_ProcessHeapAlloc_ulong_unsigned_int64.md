# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180114bb8`
- end: `0x180114c56`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180113888`
- `0x1801139b0`
- `0x180115fd4`
- `0x180116200`
- `0x180119dcc`

## callees

- `0x180114bb8`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180114c01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180114c01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180114c16`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180114c16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180114bdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180114bdd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180114bcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180114bcc`

## string_xrefs

- `0x180114bfa`: `ntdll.dll`

## pseudocode

```c

```
