# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004c86c`
- end: `0x18004c90a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004ab0c`
- `0x18004b41c`
- `0x18004b600`
- `0x18004c6b4`
- `0x18004c7ac`
- `0x18009fa70`
- `0x18009fd74`
- `0x18009fec4`
- `0x1800a06d4`
- `0x1800a0810`

## callees

- `0x18004c86c`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c8ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c8ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004c8b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004c8b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c891`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c891`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c880`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c880`

## string_xrefs

- `0x18004c8ae`: `ntdll.dll`

## pseudocode

```c

```
