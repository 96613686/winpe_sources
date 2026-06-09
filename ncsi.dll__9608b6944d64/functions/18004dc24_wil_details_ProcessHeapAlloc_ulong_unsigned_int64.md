# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004dc24`
- end: `0x18004dcba`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180044c34`
- `0x18004d9fc`
- `0x18005b79c`
- `0x18005b95c`
- `0x18005ba98`

## callees

- `0x18004b6a4`
- `0x18004dc24`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004dc6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004dc6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004dc49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004dc49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004dc38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004dc38`

## string_xrefs

- `0x18004dc66`: `ntdll.dll`

## pseudocode

```c

```
