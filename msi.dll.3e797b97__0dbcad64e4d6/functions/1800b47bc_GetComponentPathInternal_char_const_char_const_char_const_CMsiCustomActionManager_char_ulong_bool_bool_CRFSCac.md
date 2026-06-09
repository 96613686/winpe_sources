# GetComponentPathInternal(char const *,char const *,char const *,CMsiCustomActionManager *,char *,ulong *,bool,bool,CRFSCachedSourceInfo &,int,char const *,ulong,char *,ulong *,ulong *,int *,iaaAppAssignment)

- ea: `0x1800b47bc`
- end: `0x1800b4aa3`
- name: `?GetComponentPathInternal@@YA?AW4tagINSTALLSTATE@@PEBD00PEAVCMsiCustomActionManager@@PEADPEAK_N4AEAVCRFSCachedSourceInfo@@H0K233PEAHW4iaaAppAssignment@@@Z`
- size: `743`
- prototype: `enum tagINSTALLSTATE __high(const char *, const char *, const char *, struct CMsiCustomActionManager *, char *, unsigned int *, bool, bool, struct CRFSCachedSourceInfo *, int, const char *, unsigned int, char *, unsigned int *, unsigned int *, int *, enum iaaAppAssignment)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1800b369c`
- `0x1800b7d84`
- `0x180174d90`

## callees

- `0x18003c030`
- `0x1800b47bc`
- `0x1800b4aac`
- `0x1800b5dc8`
- `0x18011cdf0`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x1800b48af`
- `ADVAPI32!RegQueryValueExA` at `0x1800b48af`
- `KERNEL32!InitializeCriticalSection` at `0x1800b484e`
- `KERNEL32!InitializeCriticalSection` at `0x1800b484e`
- `KERNEL32!GlobalFree` at `0x1800b49c9`
- `KERNEL32!GlobalFree` at `0x1800b49f4`
- `KERNEL32!GlobalFree` at `0x1800b4a18`
- `KERNEL32!GlobalFree` at `0x1800b4a41`
- `KERNEL32!GlobalFree` at `0x1800b4a67`
- `KERNEL32!GlobalFree` at `0x1800b49c9`
- `KERNEL32!GlobalFree` at `0x1800b49f4`
- `KERNEL32!GlobalFree` at `0x1800b4a18`
- `KERNEL32!GlobalFree` at `0x1800b4a41`
- `KERNEL32!GlobalFree` at `0x1800b4a67`

## pseudocode

```c

```
