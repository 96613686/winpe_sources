# RemoveFontResourceExA

- ea: `0x18006ddd0`
- end: `0x18006df0a`
- name: `RemoveFontResourceExA`
- size: `314`
- prototype: `BOOL __stdcall(LPCSTR name, DWORD fl, PVOID pdv)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007e550`

## callees

- `0x180038ef0`
- `0x18006ddd0`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18006de1e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18006de6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18006de1e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18006de6d`
- `GDI32!GdiSetLastError` at `0x18006de11`
- `GDI32!GdiSetLastError` at `0x18006de11`
- `ntdll!RtlFreeHeap` at `0x18006deda`
- `ntdll!RtlFreeHeap` at `0x18006deda`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18006de8b`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18006de8b`
- `ntdll!RtlAllocateHeap` at `0x18006de54`
- `ntdll!RtlAllocateHeap` at `0x18006de54`

## pseudocode

```c

```
