# DoAdvertiseScript(char const *,ulong,HKEY__ * *,int)

- ea: `0x1801961b8`
- end: `0x180196a03`
- name: `?DoAdvertiseScript@@YAIPEBDKPEAPEAUHKEY__@@H@Z`
- size: `2123`
- prototype: `unsigned int __fastcall(const char *, unsigned int, HKEY *, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18019b520`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x180006970`
- `0x180008d68`
- `0x18000c4bc`
- `0x180013fe4`
- `0x180014528`
- `0x180027634`
- `0x18002e870`
- `0x1800433c0`
- `0x180067fec`
- `0x180077470`
- `0x18007adb4`
- `0x18007b9e8`
- `0x180081de0`
- `0x180097608`
- `0x1800a6864`
- `0x1800ae46c`
- `0x1800c08f8`
- `0x1800c8268`
- `0x18012b2c0`
- `0x18012e4e8`
- `0x180148a30`
- `0x1801961b8`
- `0x1801d1938`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18019635e`
- `KERNEL32!GetLastError` at `0x18019635e`
- `KERNEL32!GlobalAlloc` at `0x180196432`
- `KERNEL32!GlobalAlloc` at `0x180196432`
- `KERNEL32!GlobalFree` at `0x18019634d`
- `KERNEL32!GlobalFree` at `0x18019651c`
- `KERNEL32!GlobalFree` at `0x1801968bc`
- `KERNEL32!GlobalFree` at `0x18019634d`
- `KERNEL32!GlobalFree` at `0x18019651c`
- `KERNEL32!GlobalFree` at `0x1801968bc`

## string_xrefs

- `0x180196255`: `Attempt to execute advertise script when not running as local system`
- `0x1801962af`: `Attempt to do an unimpersonated user assignment`
- `0x1801963f2`: `MsiAdvertiseScript: OLE initialized to MTA already, therefore cannot call IShellLink`
- `0x1801969cc`: `MsiAdvertiseScript failed to initialize COM with error 0x%X`

## pseudocode

```c

```
