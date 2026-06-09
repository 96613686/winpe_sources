# MsiWinHttpGetProxy(void *,void *,ushort const *,_WINHTTP_PROXY_INFO * *)

- ea: `0x18023265c`
- end: `0x1802329e0`
- name: `?MsiWinHttpGetProxy@@YAHPEAX0PEBGPEAPEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `900`
- prototype: `int(void *, void *, const unsigned __int16 *, struct _WINHTTP_PROXY_INFO **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180232ae8`

## callees

- `0x18000c4bc`
- `0x180013d64`
- `0x180014f18`
- `0x18023265c`
- `0x1802651d2`
- `0x180266010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1802329ae`
- `KERNEL32!SetLastError` at `0x1802329ae`
- `KERNEL32!GlobalAlloc` at `0x1802328cd`
- `KERNEL32!GlobalAlloc` at `0x1802328cd`
- `KERNEL32!lstrlenW` at `0x180232895`
- `KERNEL32!lstrlenW` at `0x1802328ae`
- `KERNEL32!lstrlenW` at `0x180232895`
- `KERNEL32!lstrlenW` at `0x1802328ae`
- `KERNEL32!GlobalFree` at `0x18023293e`
- `KERNEL32!GlobalFree` at `0x180232956`
- `KERNEL32!GlobalFree` at `0x18023296f`
- `KERNEL32!GlobalFree` at `0x180232987`
- `KERNEL32!GlobalFree` at `0x18023299c`
- `KERNEL32!GlobalFree` at `0x18023293e`
- `KERNEL32!GlobalFree` at `0x180232956`
- `KERNEL32!GlobalFree` at `0x18023296f`
- `KERNEL32!GlobalFree` at `0x180232987`
- `KERNEL32!GlobalFree` at `0x18023299c`

## string_xrefs

- `0x180232876`: `MSI WinHttp: Proxy Settings Proxy: %s | Bypass: %s | AccessType: %d`
- `0x180232753`: `Msi WinHttp: Performing auto proxy detection`

## pseudocode

```c

```
