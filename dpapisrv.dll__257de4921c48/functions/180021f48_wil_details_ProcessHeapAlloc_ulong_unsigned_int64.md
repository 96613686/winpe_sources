# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180021f48`
- end: `0x180021fff`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c490`
- `0x18001c5f4`
- `0x180022b44`
- `0x180022fe4`
- `0x180023edc`

## callees

- `0x180021f48`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021fb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021fb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021f9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021f9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021f5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021f73`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021f73`

## string_xrefs

- `0x180021f96`: `ntdll.dll`

## pseudocode

```c

```
