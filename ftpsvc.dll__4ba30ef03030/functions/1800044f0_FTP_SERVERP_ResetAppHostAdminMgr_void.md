# FTP_SERVERP::ResetAppHostAdminMgr(void)

- ea: `0x1800044f0`
- end: `0x1800045fb`
- name: `?ResetAppHostAdminMgr@FTP_SERVERP@@UEAAJXZ`
- size: `267`
- prototype: `__int64 __fastcall(FTP_SERVERP *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180001210`
- `0x180001250`
- `0x1800044f0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180004564`
- `KERNEL32!CreateThread` at `0x180004564`
- `KERNEL32!GetLastError` at `0x180004593`
- `KERNEL32!GetLastError` at `0x180004593`
- `KERNEL32!CloseHandle` at `0x18000457e`
- `KERNEL32!CloseHandle` at `0x18000457e`
- `iisutil!PuDbgPrint` at `0x1800045dc`
- `iisutil!PuDbgPrint` at `0x1800045dc`

## string_xrefs

- `0x1800045b8`: `CreateThread() failed to reset config system.  hr = %x\n`

## pseudocode

```c

```
