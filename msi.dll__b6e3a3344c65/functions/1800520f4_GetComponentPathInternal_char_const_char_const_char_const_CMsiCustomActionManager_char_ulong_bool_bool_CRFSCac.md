# GetComponentPathInternal(char const *,char const *,char const *,CMsiCustomActionManager *,char *,ulong *,bool,bool,CRFSCachedSourceInfo &,int,char const *,ulong,char *,ulong *,ulong *,int *,iaaAppAssignment)

- ea: `0x1800520f4`
- end: `0x1800523b0`
- name: `?GetComponentPathInternal@@YA?AW4tagINSTALLSTATE@@PEBD00PEAVCMsiCustomActionManager@@PEADPEAK_N4AEAVCRFSCachedSourceInfo@@H0K233PEAHW4iaaAppAssignment@@@Z`
- size: `700`
- prototype: `enum tagINSTALLSTATE __high(const char *, const char *, const char *, struct CMsiCustomActionManager *, char *, unsigned int *, bool, bool, struct CRFSCachedSourceInfo *, int, const char *, unsigned int, char *, unsigned int *, unsigned int *, int *, enum iaaAppAssignment)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180055030`
- `0x1801357b4`
- `0x18016ec60`

## callees

- `0x180015950`
- `0x1800520f4`
- `0x1800523b8`
- `0x180053570`
- `0x180116644`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x1800521e1`
- `ADVAPI32!RegQueryValueExA` at `0x1800521e1`
- `KERNEL32!InitializeCriticalSection` at `0x180052186`
- `KERNEL32!InitializeCriticalSection` at `0x180052186`
- `KERNEL32!GlobalFree` at `0x1800522f5`
- `KERNEL32!GlobalFree` at `0x18005231a`
- `KERNEL32!GlobalFree` at `0x180052338`
- `KERNEL32!GlobalFree` at `0x18005235b`
- `KERNEL32!GlobalFree` at `0x18005237b`
- `KERNEL32!GlobalFree` at `0x1800522f5`
- `KERNEL32!GlobalFree` at `0x18005231a`
- `KERNEL32!GlobalFree` at `0x180052338`
- `KERNEL32!GlobalFree` at `0x18005235b`
- `KERNEL32!GlobalFree` at `0x18005237b`

## pseudocode

```c

```
