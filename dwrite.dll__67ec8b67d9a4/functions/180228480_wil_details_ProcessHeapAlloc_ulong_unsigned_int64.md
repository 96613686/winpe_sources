# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180228480`
- end: `0x180228516`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180211930`
- `0x180227570`
- `0x180227fa4`
- `0x1802280d4`
- `0x180228f50`
- `0x1802293d4`

## callees

- `0x180225a4c`
- `0x180228480`
- `0x180330010`

## import_xrefs

- `kernel32!HeapAlloc` at `0x1802284a5`
- `kernel32!HeapAlloc` at `0x1802284a5`
- `kernel32!GetProcessHeap` at `0x180228494`
- `kernel32!GetProcessHeap` at `0x180228494`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1802284c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1802284c9`

## string_xrefs

- `0x1802284c2`: `ntdll.dll`

## pseudocode

```c

```
