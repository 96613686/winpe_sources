# CDeviceCollection::AddDevicesByDevInterface(_GUID *,ulong,ulong,ulong *,ulong *)

- ea: `0x18056d5a0`
- end: `0x18056d942`
- name: `?AddDevicesByDevInterface@CDeviceCollection@@UEAAJPEAU_GUID@@KKPEAK1@Z`
- size: `930`
- prototype: `__int64 __usercall@<rax>(CDeviceCollection *__hidden this@<rcx>, struct _GUID *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x18056d1a0`
- `0x18056d5a0`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18056d639`
- `KERNEL32!GetLastError` at `0x18056d6d9`
- `KERNEL32!GetLastError` at `0x18056d86c`
- `KERNEL32!GetLastError` at `0x18056d8cd`
- `KERNEL32!GetLastError` at `0x18056d8de`
- `KERNEL32!GetLastError` at `0x18056d639`
- `KERNEL32!GetLastError` at `0x18056d6d9`
- `KERNEL32!GetLastError` at `0x18056d86c`
- `KERNEL32!GetLastError` at `0x18056d8cd`
- `KERNEL32!GetLastError` at `0x18056d8de`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18056d7d9`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18056d7d9`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18056d7b8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18056d7b8`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18056d767`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18056d767`
- `DEVOBJ!DevObjGetClassDevs` at `0x18056d6cf`
- `DEVOBJ!DevObjGetClassDevs` at `0x18056d6cf`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056d909`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056d909`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056d62a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056d62a`

## string_xrefs

- `0x18056d687`: `DevObjCreateDeviceInfoList FAILED`

## pseudocode

```c

```
