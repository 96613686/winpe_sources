# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800b4ff4`
- end: `0x1800b5092`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800aed6c`
- `0x1800af110`
- `0x1800b706c`
- `0x1800b829c`

## callees

- `0x1800b4ff4`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5008`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5019`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b5052`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b5052`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b503d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b503d`

## string_xrefs

- `0x1800b5036`: `ntdll.dll`

## pseudocode

```c

```
