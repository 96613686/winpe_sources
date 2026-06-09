# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005fe48`
- end: `0x18005fee7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005f910`
- `0x18005fa40`
- `0x180061ef0`
- `0x18006239c`
- `0x180064014`

## callees

- `0x18005fe48`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005fe91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005fe91`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fea6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fea6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fe5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fe5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fe6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fe6d`

## string_xrefs

- `0x18005fe8a`: `ntdll.dll`

## pseudocode

```c

```
