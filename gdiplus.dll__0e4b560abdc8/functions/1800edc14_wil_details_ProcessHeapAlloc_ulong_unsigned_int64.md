# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800edc14`
- end: `0x1800edccb`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800ed690`
- `0x1800ed7e0`
- `0x1800ee9f0`
- `0x1800eec9c`
- `0x1800efe58`

## callees

- `0x1800edc14`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800edc84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800edc84`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800edc69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800edc69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800edc3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800edc3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800edc28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800edc28`

## string_xrefs

- `0x1800edc62`: `ntdll.dll`

## pseudocode

```c

```
