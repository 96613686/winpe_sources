# GetComponentPathInternal(ushort const *,ushort const *,ushort const *,CMsiCustomActionManager *,ushort *,ulong *,bool,bool,CRFSCachedSourceInfo &,int,ushort const *,ulong,ushort *,ulong *,ulong *,int *,iaaAppAssignment)

- ea: `0x180095d40`
- end: `0x18009615c`
- name: `?GetComponentPathInternal@@YA?AW4tagINSTALLSTATE@@PEBG00PEAVCMsiCustomActionManager@@PEAGPEAK_N4AEAVCRFSCachedSourceInfo@@H0K233PEAHW4iaaAppAssignment@@@Z`
- size: `1052`
- prototype: `enum tagINSTALLSTATE __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CMsiCustomActionManager *, unsigned __int16 *, unsigned int *, bool, bool, struct CRFSCachedSourceInfo *, int, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *, int *, enum iaaAppAssignment)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180039e50`
- `0x180043e60`
- `0x18004a530`
- `0x180094df0`

## callees

- `0x18000f1c0`
- `0x180010ac0`
- `0x18003c030`
- `0x180095d40`
- `0x180096164`
- `0x18009fdf0`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180095fa9`
- `ADVAPI32!RegQueryValueExW` at `0x180095fa9`
- `KERNEL32!InitializeCriticalSection` at `0x180095dfd`
- `KERNEL32!InitializeCriticalSection` at `0x180095dfd`
- `KERNEL32!GlobalFree` at `0x180095e9a`
- `KERNEL32!GlobalFree` at `0x180095f5b`
- `KERNEL32!GlobalFree` at `0x180096058`
- `KERNEL32!GlobalFree` at `0x18009607e`
- `KERNEL32!GlobalFree` at `0x1800960c2`
- `KERNEL32!GlobalFree` at `0x180096106`
- `KERNEL32!GlobalFree` at `0x18009612d`
- `KERNEL32!GlobalFree` at `0x180095e9a`
- `KERNEL32!GlobalFree` at `0x180095f5b`
- `KERNEL32!GlobalFree` at `0x180096058`
- `KERNEL32!GlobalFree` at `0x18009607e`
- `KERNEL32!GlobalFree` at `0x1800960c2`
- `KERNEL32!GlobalFree` at `0x180096106`
- `KERNEL32!GlobalFree` at `0x18009612d`

## string_xrefs

- `0x180095edd`: `Components`

## pseudocode

```c

```
