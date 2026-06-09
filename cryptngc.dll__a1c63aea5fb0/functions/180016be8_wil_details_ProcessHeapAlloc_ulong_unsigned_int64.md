# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180016be8`
- end: `0x180016c86`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180030570`
- `0x1800306a0`
- `0x180030dd0`
- `0x180031168`

## callees

- `0x180016be8`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c46`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016c31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016c31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016bfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016bfc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016c0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016c0d`

## string_xrefs

- `0x180016c2a`: `ntdll.dll`

## pseudocode

```c

```
