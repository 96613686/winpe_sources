# CDeviceCollection::AddDevicesBySetupClass(_GUID *,ulong,ulong,int,ulong *,ulong *)

- ea: `0x18056d950`
- end: `0x18056dd2a`
- name: `?AddDevicesBySetupClass@CDeviceCollection@@UEAAJPEAU_GUID@@KKHPEAK1@Z`
- size: `986`
- prototype: `__int64 __usercall@<rax>(CDeviceCollection *__hidden this@<rcx>, struct _GUID *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, int, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x180094bc8`
- `0x180094d34`
- `0x1800e9b1c`
- `0x18056d1a0`
- `0x18056d950`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18056d9e6`
- `KERNEL32!GetLastError` at `0x18056da85`
- `KERNEL32!GetLastError` at `0x18056dc5c`
- `KERNEL32!GetLastError` at `0x18056dcbd`
- `KERNEL32!GetLastError` at `0x18056dcca`
- `KERNEL32!GetLastError` at `0x18056d9e6`
- `KERNEL32!GetLastError` at `0x18056da85`
- `KERNEL32!GetLastError` at `0x18056dc5c`
- `KERNEL32!GetLastError` at `0x18056dcbd`
- `KERNEL32!GetLastError` at `0x18056dcca`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18056db48`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18056db48`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18056dbc8`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18056dbc8`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18056db0f`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18056db0f`
- `DEVOBJ!DevObjGetClassDevs` at `0x18056da7b`
- `DEVOBJ!DevObjGetClassDevs` at `0x18056da7b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056dcf1`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056dcf1`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056d9d7`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056d9d7`

## string_xrefs

- `0x18056da34`: `DevObjCreateDeviceInfoList FAILED`

## pseudocode

```c

```
