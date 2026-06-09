# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180109b28`
- end: `0x180109bdf`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180105190`
- `0x180109628`
- `0x18010974c`
- `0x18010a558`
- `0x18010a7c8`

## callees

- `0x180109b28`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180109b7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180109b7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180109b98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180109b98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180109b53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180109b53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180109b3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180109b3c`

## string_xrefs

- `0x180109b76`: `ntdll.dll`

## pseudocode

```c

```
