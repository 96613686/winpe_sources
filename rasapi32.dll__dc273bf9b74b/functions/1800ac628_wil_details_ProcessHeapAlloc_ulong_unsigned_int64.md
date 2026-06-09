# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800ac628`
- end: `0x1800ac6c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800ac148`
- `0x1800ac270`
- `0x1800ad914`
- `0x1800adb40`
- `0x1800aea90`

## callees

- `0x1800ac628`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ac671`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ac671`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac686`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ac63c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ac63c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ac64d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ac64d`

## string_xrefs

- `0x1800ac66a`: `ntdll.dll`

## pseudocode

```c

```
