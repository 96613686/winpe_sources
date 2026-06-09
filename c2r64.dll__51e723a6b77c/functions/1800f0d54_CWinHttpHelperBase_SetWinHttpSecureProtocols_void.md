# CWinHttpHelperBase::SetWinHttpSecureProtocols(void)

- ea: `0x1800f0d54`
- end: `0x1800f1045`
- name: `?SetWinHttpSecureProtocols@CWinHttpHelperBase@@AEAAXXZ`
- size: `753`
- prototype: `void __fastcall(CWinHttpHelperBase *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800f04d4`

## callees

- `0x18000adf0`
- `0x180010730`
- `0x1800258b4`
- `0x18003e690`
- `0x18005ac1c`
- `0x18005ace0`
- `0x18009afa0`
- `0x18009c0e0`
- `0x1800d0d00`
- `0x1800f00ac`
- `0x1800f0d54`
- `0x1800f3d10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800f0e1c`
- `KERNEL32!GetLastError` at `0x1800f0ed8`
- `KERNEL32!GetLastError` at `0x1800f0e1c`
- `KERNEL32!GetLastError` at `0x1800f0ed8`
- `WINHTTP!WinHttpSetOption` at `0x1800f0e02`
- `WINHTTP!WinHttpSetOption` at `0x1800f0ec7`
- `WINHTTP!WinHttpSetOption` at `0x1800f0e02`
- `WINHTTP!WinHttpSetOption` at `0x1800f0ec7`

## string_xrefs

- `0x1800f0fad`: `SetWinHttpSecureProtocols()`
- `0x1800f0f6d`: `SecureProtocol`
- `0x1800f0e50`: `Failed to set secure protocols option`

## pseudocode

```c

```
