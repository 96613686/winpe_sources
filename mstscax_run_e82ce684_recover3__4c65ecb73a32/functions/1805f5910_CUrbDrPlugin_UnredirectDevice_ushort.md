# CUrbDrPlugin::UnredirectDevice(ushort *)

- ea: `0x1805f5910`
- end: `0x1805f5d42`
- name: `?UnredirectDevice@CUrbDrPlugin@@AEAAJPEAG@Z`
- size: `1074`
- prototype: `__int64 __fastcall(CUrbDrPlugin *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1805f5370`

## callees

- `0x18001cdc0`
- `0x1800204e8`
- `0x18002a334`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x1805f5910`
- `0x1805f7d7c`
- `0x1805fa2f8`
- `0x1805fa344`
- `0x1805fa3e4`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1805f598c`
- `KERNEL32!GetLastError` at `0x1805f5a33`
- `KERNEL32!GetLastError` at `0x1805f5ac7`
- `KERNEL32!GetLastError` at `0x1805f598c`
- `KERNEL32!GetLastError` at `0x1805f5a33`
- `KERNEL32!GetLastError` at `0x1805f5ac7`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1805f5b3c`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1805f5b3c`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1805f5abd`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1805f5abd`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805f5a29`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805f5a29`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f5d04`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f5d04`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805f5977`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805f5977`
- `ADVAPI32!RegQueryValueExW` at `0x1805f5b72`
- `ADVAPI32!RegQueryValueExW` at `0x1805f5b72`
- `ADVAPI32!RegCloseKey` at `0x1805f5d13`
- `ADVAPI32!RegCloseKey` at `0x1805f5d13`

## string_xrefs

- `0x1805f59d2`: `DevObjCreateDeviceInfoList FAILED`

## pseudocode

```c

```
