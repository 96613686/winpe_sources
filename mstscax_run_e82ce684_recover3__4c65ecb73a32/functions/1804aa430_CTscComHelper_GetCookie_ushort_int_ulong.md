# CTscComHelper::GetCookie(ushort *,int,ulong *)

- ea: `0x1804aa430`
- end: `0x1804aa8ed`
- name: `?GetCookie@CTscComHelper@@CAJPEAGHPEAK@Z`
- size: `1213`
- prototype: `__int64 __fastcall(LPWSTR lpsz, int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1804a9e54`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1804a9c00`
- `0x1804a9d3c`
- `0x1804aa430`
- `0x1804aa8f4`
- `0x1804aad5c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804aa535`
- `KERNEL32!GetLastError` at `0x1804aa542`
- `KERNEL32!GetLastError` at `0x1804aa63f`
- `KERNEL32!GetLastError` at `0x1804aa6f1`
- `KERNEL32!GetLastError` at `0x1804aa535`
- `KERNEL32!GetLastError` at `0x1804aa542`
- `KERNEL32!GetLastError` at `0x1804aa63f`
- `KERNEL32!GetLastError` at `0x1804aa6f1`
- `KERNEL32!LocalAlloc` at `0x1804aa74b`
- `KERNEL32!LocalAlloc` at `0x1804aa74b`
- `KERNEL32!LocalFree` at `0x1804aa8b7`
- `KERNEL32!LocalFree` at `0x1804aa8c5`
- `KERNEL32!LocalFree` at `0x1804aa8b7`
- `KERNEL32!LocalFree` at `0x1804aa8c5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1804aa5ba`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1804aa5ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1804aa867`
- `OLEAUT32!__imp_SysFreeString` at `0x1804aa88e`
- `OLEAUT32!__imp_SysFreeString` at `0x1804aa867`
- `OLEAUT32!__imp_SysFreeString` at `0x1804aa88e`
- `CRYPT32!CryptProtectData` at `0x1804aa6e7`
- `CRYPT32!CryptProtectData` at `0x1804aa6e7`
- `WININET!InternetGetCookieW` at `0x1804aa527`
- `WININET!InternetGetCookieW` at `0x1804aa635`
- `WININET!InternetGetCookieW` at `0x1804aa527`
- `WININET!InternetGetCookieW` at `0x1804aa635`

## pseudocode

```c

```
