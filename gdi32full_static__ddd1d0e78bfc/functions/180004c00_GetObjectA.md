# GetObjectA

- ea: `0x180004c00`
- end: `0x180004f2e`
- name: `GetObjectA`
- size: `814`
- prototype: `int __stdcall(HANDLE h, int c, LPVOID pv)`
- caller_count: `14`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180001f18`
- `0x180002ac8`
- `0x1800032a8`
- `0x180003a9c`
- `0x1800177f0`
- `0x180024c40`
- `0x1800270d8`
- `0x180028260`
- `0x180029730`
- `0x1800741cc`
- `0x1800836f0`
- `0x18008406c`
- `0x18008eb38`
- `0x18009d9e4`

## callees

- `0x180004c00`
- `0x1800050b0`
- `0x18004c6c0`
- `0x18007f800`
- `0x180080604`
- `0x18008deb0`
- `0x1800a68d4`

## import_xrefs

- `GDI32!GdiSetLastError` at `0x180004df4`
- `GDI32!GdiSetLastError` at `0x180004f1b`
- `GDI32!GdiSetLastError` at `0x180004df4`
- `GDI32!GdiSetLastError` at `0x180004f1b`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180004db1`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180004db1`
- `win32u!NtGdiExtGetObjectW` at `0x180004ca7`
- `win32u!NtGdiExtGetObjectW` at `0x180004cf9`
- `win32u!NtGdiExtGetObjectW` at `0x180004ca7`
- `win32u!NtGdiExtGetObjectW` at `0x180004cf9`

## pseudocode

```c

```
