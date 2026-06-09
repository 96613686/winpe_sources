# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180075e68`
- end: `0x180075f06`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003bfa8`
- `0x180075960`
- `0x180075a8c`
- `0x180076894`
- `0x180076af8`

## callees

- `0x180075e68`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075e7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075e7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180075e8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180075e8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075ec6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075ec6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180075eb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180075eb1`

## string_xrefs

- `0x180075eaa`: `ntdll.dll`

## pseudocode

```c

```
