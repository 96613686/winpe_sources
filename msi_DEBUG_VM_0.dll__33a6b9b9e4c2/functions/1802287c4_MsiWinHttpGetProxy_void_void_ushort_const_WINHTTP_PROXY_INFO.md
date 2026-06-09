# MsiWinHttpGetProxy(void *,void *,ushort const *,_WINHTTP_PROXY_INFO * *)

- ea: `0x1802287c4`
- end: `0x180228b11`
- name: `?MsiWinHttpGetProxy@@YAHPEAX0PEBGPEAPEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `845`
- prototype: `int(void *, void *, const unsigned __int16 *, struct _WINHTTP_PROXY_INFO **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180228c08`

## callees

- `0x180025a18`
- `0x180064b4c`
- `0x180064f18`
- `0x1802287c4`
- `0x18025ab12`
- `0x18025c010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180228ae6`
- `KERNEL32!SetLastError` at `0x180228ae6`
- `KERNEL32!GlobalAlloc` at `0x180228a29`
- `KERNEL32!GlobalAlloc` at `0x180228a29`
- `KERNEL32!lstrlenW` at `0x1802289fd`
- `KERNEL32!lstrlenW` at `0x180228a10`
- `KERNEL32!lstrlenW` at `0x1802289fd`
- `KERNEL32!lstrlenW` at `0x180228a10`
- `KERNEL32!GlobalFree` at `0x180228a94`
- `KERNEL32!GlobalFree` at `0x180228aa6`
- `KERNEL32!GlobalFree` at `0x180228ab9`
- `KERNEL32!GlobalFree` at `0x180228acb`
- `KERNEL32!GlobalFree` at `0x180228ada`
- `KERNEL32!GlobalFree` at `0x180228a94`
- `KERNEL32!GlobalFree` at `0x180228aa6`
- `KERNEL32!GlobalFree` at `0x180228ab9`
- `KERNEL32!GlobalFree` at `0x180228acb`
- `KERNEL32!GlobalFree` at `0x180228ada`

## string_xrefs

- `0x1802289de`: `MSI WinHttp: Proxy Settings Proxy: %s | Bypass: %s | AccessType: %d`
- `0x1802288bb`: `Msi WinHttp: Performing auto proxy detection`

## pseudocode

```c

```
