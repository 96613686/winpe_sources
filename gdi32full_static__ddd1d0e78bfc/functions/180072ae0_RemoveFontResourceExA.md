# RemoveFontResourceExA

- ea: `0x180072ae0`
- end: `0x180072c3f`
- name: `RemoveFontResourceExA`
- size: `351`
- prototype: `BOOL __stdcall(LPCSTR name, DWORD fl, PVOID pdv)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180083240`

## callees

- `0x180044900`
- `0x180072ae0`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180072b34`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180072b8f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180072b34`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180072b8f`
- `GDI32!GdiSetLastError` at `0x180072b21`
- `GDI32!GdiSetLastError` at `0x180072b21`
- `ntdll!RtlFreeHeap` at `0x180072c08`
- `ntdll!RtlFreeHeap` at `0x180072c08`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180072bb3`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180072bb3`
- `ntdll!RtlAllocateHeap` at `0x180072b70`
- `ntdll!RtlAllocateHeap` at `0x180072b70`

## pseudocode

```c

```
