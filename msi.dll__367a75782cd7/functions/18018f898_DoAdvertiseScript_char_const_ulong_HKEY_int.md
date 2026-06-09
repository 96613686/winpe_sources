# DoAdvertiseScript(char const *,ulong,HKEY__ * *,int)

- ea: `0x18018f898`
- end: `0x1801900c1`
- name: `?DoAdvertiseScript@@YAIPEBDKPEAPEAUHKEY__@@H@Z`
- size: `2089`
- prototype: `DWORD __fastcall(const char *, unsigned int, HKEY *, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801948c0`

## callees

- `0x18000a150`
- `0x18001ba40`
- `0x180024f9c`
- `0x180025904`
- `0x180025a18`
- `0x180035a8c`
- `0x180066074`
- `0x180068680`
- `0x180071494`
- `0x180076e28`
- `0x180079dd0`
- `0x18007ccec`
- `0x18007d8cc`
- `0x18008af8c`
- `0x180098b50`
- `0x18009ae30`
- `0x18009e5d8`
- `0x1800a5fc4`
- `0x1800b8034`
- `0x1800cc4dc`
- `0x180126db8`
- `0x180129200`
- `0x180143d60`
- `0x18018f898`
- `0x1801c90d8`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18018fa37`
- `KERNEL32!GetLastError` at `0x18018fa37`
- `KERNEL32!GlobalAlloc` at `0x18018fb02`
- `KERNEL32!GlobalAlloc` at `0x18018fb02`
- `KERNEL32!GlobalFree` at `0x18018fa2c`
- `KERNEL32!GlobalFree` at `0x18018fbe6`
- `KERNEL32!GlobalFree` at `0x18018ff80`
- `KERNEL32!GlobalFree` at `0x18018fa2c`
- `KERNEL32!GlobalFree` at `0x18018fbe6`
- `KERNEL32!GlobalFree` at `0x18018ff80`

## string_xrefs

- `0x18018f935`: `Attempt to execute advertise script when not running as local system`
- `0x18018f98f`: `Attempt to do an unimpersonated user assignment`
- `0x18018fac2`: `MsiAdvertiseScript: OLE initialized to MTA already, therefore cannot call IShellLink`
- `0x18019008a`: `MsiAdvertiseScript failed to initialize COM with error 0x%X`

## pseudocode

```c

```
