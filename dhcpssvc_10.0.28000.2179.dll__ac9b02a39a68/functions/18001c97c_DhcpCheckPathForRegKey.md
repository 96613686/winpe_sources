# DhcpCheckPathForRegKey

- ea: `0x18001c97c`
- end: `0x18001cb89`
- name: `DhcpCheckPathForRegKey`
- size: `525`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001cb90`

## callees

- `0x1800058bc`
- `0x18001c97c`
- `0x18001dde0`
- `0x1800cdac0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001ca24`
- `KERNEL32!HeapAlloc` at `0x18001ca24`
- `KERNEL32!GetFileAttributesExW` at `0x18001ca98`
- `KERNEL32!GetFileAttributesExW` at `0x18001ca98`
- `KERNEL32!GetLastError` at `0x18001cb2c`
- `KERNEL32!GetLastError` at `0x18001cb2c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001ca59`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001ca59`
- `KERNEL32!LocalFree` at `0x18001cb57`
- `KERNEL32!LocalFree` at `0x18001cb57`
- `KERNEL32!HeapFree` at `0x18001cb46`
- `KERNEL32!HeapFree` at `0x18001cb46`

## pseudocode

```c

```
