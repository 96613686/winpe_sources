# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180019e54`
- end: `0x180019ef2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001b278`
- `0x18001b6e0`
- `0x18001b8f0`
- `0x18001c928`

## callees

- `0x180019e54`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019eb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019eb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019e9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019e9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019e79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019e79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e68`

## string_xrefs

- `0x180019e96`: `ntdll.dll`

## pseudocode

```c

```
