# DhcpCheckPathForRegKey

- ea: `0x18001d3d8`
- end: `0x18001d5e5`
- name: `DhcpCheckPathForRegKey`
- size: `525`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001d5ec`

## callees

- `0x1800058cc`
- `0x18001d3d8`
- `0x18001e828`
- `0x1800cc9e0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001d480`
- `KERNEL32!HeapAlloc` at `0x18001d480`
- `KERNEL32!GetFileAttributesExW` at `0x18001d4f4`
- `KERNEL32!GetFileAttributesExW` at `0x18001d4f4`
- `KERNEL32!GetLastError` at `0x18001d588`
- `KERNEL32!GetLastError` at `0x18001d588`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001d4b5`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001d4b5`
- `KERNEL32!LocalFree` at `0x18001d5b3`
- `KERNEL32!LocalFree` at `0x18001d5b3`
- `KERNEL32!HeapFree` at `0x18001d5a2`
- `KERNEL32!HeapFree` at `0x18001d5a2`

## pseudocode

```c

```
