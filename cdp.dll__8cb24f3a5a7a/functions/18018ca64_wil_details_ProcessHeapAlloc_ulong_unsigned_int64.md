# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18018ca64`
- end: `0x18018cb02`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180097350`
- `0x1800d2bb0`
- `0x1800d4264`
- `0x1800de17c`
- `0x18021f844`
- `0x18021f994`
- `0x180220310`
- `0x18022044c`

## callees

- `0x18018ca64`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18018caad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18018caad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018cac2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018cac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18018ca78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18018ca78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18018ca89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18018ca89`

## string_xrefs

- `0x18018caa6`: `ntdll.dll`

## pseudocode

```c

```
