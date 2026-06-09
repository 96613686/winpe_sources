# GetComponentPathInternal(ushort const *,ushort const *,ushort const *,CMsiCustomActionManager *,ushort *,ulong *,bool,bool,CRFSCachedSourceInfo &,int,ushort const *,ulong,ushort *,ulong *,ulong *,int *,iaaAppAssignment)

- ea: `0x18006fcf4`
- end: `0x1800700d9`
- name: `?GetComponentPathInternal@@YA?AW4tagINSTALLSTATE@@PEBG00PEAVCMsiCustomActionManager@@PEAGPEAK_N4AEAVCRFSCachedSourceInfo@@H0K233PEAHW4iaaAppAssignment@@@Z`
- size: `997`
- prototype: `enum tagINSTALLSTATE __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CMsiCustomActionManager *, unsigned __int16 *, unsigned int *, bool, bool, struct CRFSCachedSourceInfo *, int, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *, int *, enum iaaAppAssignment)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1800138e4`
- `0x18001c420`
- `0x18004b75c`
- `0x18006ee70`

## callees

- `0x180015950`
- `0x180020940`
- `0x180022120`
- `0x18006fcf4`
- `0x1800700e0`
- `0x1800a9f70`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18006ff4a`
- `ADVAPI32!RegQueryValueExW` at `0x18006ff4a`
- `KERNEL32!InitializeCriticalSection` at `0x18006fdb1`
- `KERNEL32!InitializeCriticalSection` at `0x18006fdb1`
- `KERNEL32!GlobalFree` at `0x18006fe48`
- `KERNEL32!GlobalFree` at `0x18006ff02`
- `KERNEL32!GlobalFree` at `0x18006fff3`
- `KERNEL32!GlobalFree` at `0x180070013`
- `KERNEL32!GlobalFree` at `0x180070051`
- `KERNEL32!GlobalFree` at `0x18007008f`
- `KERNEL32!GlobalFree` at `0x1800700b0`
- `KERNEL32!GlobalFree` at `0x18006fe48`
- `KERNEL32!GlobalFree` at `0x18006ff02`
- `KERNEL32!GlobalFree` at `0x18006fff3`
- `KERNEL32!GlobalFree` at `0x180070013`
- `KERNEL32!GlobalFree` at `0x180070051`
- `KERNEL32!GlobalFree` at `0x18007008f`
- `KERNEL32!GlobalFree` at `0x1800700b0`

## string_xrefs

- `0x18006fe84`: `Components`

## pseudocode

```c

```
