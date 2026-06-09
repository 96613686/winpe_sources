# CDeviceCollection::AddRedirectableDevices(ushort *,ulong,ulong,ulong *,ulong *)

- ea: `0x1800947b0`
- end: `0x180094bbf`
- name: `?AddRedirectableDevices@CDeviceCollection@@UEAAJPEAGKKPEAK1@Z`
- size: `1039`
- prototype: `__int64 __usercall@<rax>(CDeviceCollection *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800947b0`
- `0x180094c10`
- `0x180094d34`
- `0x1800e9b1c`
- `0x18012966c`
- `0x18056d1a0`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180094835`
- `KERNEL32!GetLastError` at `0x1800948d4`
- `KERNEL32!GetLastError` at `0x180094ae3`
- `KERNEL32!GetLastError` at `0x180094b4e`
- `KERNEL32!GetLastError` at `0x180094b5f`
- `KERNEL32!GetLastError` at `0x180094835`
- `KERNEL32!GetLastError` at `0x1800948d4`
- `KERNEL32!GetLastError` at `0x180094ae3`
- `KERNEL32!GetLastError` at `0x180094b4e`
- `KERNEL32!GetLastError` at `0x180094b5f`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180094986`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180094986`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180094a18`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180094a18`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180094959`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180094959`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800948ca`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800948ca`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180094b86`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180094b86`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180094826`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180094826`
- `ADVAPI32!RegCloseKey` at `0x180094ac5`
- `ADVAPI32!RegCloseKey` at `0x180094ac5`

## string_xrefs

- `0x180094883`: `DevObjCreateDeviceInfoList FAILED`

## pseudocode

```c

```
