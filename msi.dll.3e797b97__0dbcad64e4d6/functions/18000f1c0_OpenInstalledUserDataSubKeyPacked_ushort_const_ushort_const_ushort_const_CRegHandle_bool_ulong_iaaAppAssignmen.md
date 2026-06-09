# OpenInstalledUserDataSubKeyPacked(ushort const *,ushort const *,ushort const *,CRegHandle &,bool,ulong,iaaAppAssignment,iaaAppAssignment *)

- ea: `0x18000f1c0`
- end: `0x18000f5f2`
- name: `?OpenInstalledUserDataSubKeyPacked@@YAKPEBG00AEAVCRegHandle@@_NKW4iaaAppAssignment@@PEAW42@@Z`
- size: `1074`
- prototype: `unsigned int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CRegHandle *, bool, unsigned int, enum iaaAppAssignment, enum iaaAppAssignment *)`
- caller_count: `11`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800398bc`
- `0x18003c0d4`
- `0x18003c1d0`
- `0x180048294`
- `0x18004c7e4`
- `0x180095d40`
- `0x1800b2820`
- `0x1801993cc`
- `0x1801dc920`
- `0x18021c94c`
- `0x18023d720`

## callees

- `0x18000f1c0`
- `0x180010ac0`
- `0x180013b7c`
- `0x18003a560`
- `0x1800b8f60`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000f2c5`
- `ADVAPI32!RegCloseKey` at `0x18000f397`
- `ADVAPI32!RegCloseKey` at `0x18000f2c5`
- `ADVAPI32!RegCloseKey` at `0x18000f397`
- `KERNEL32!LeaveCriticalSection` at `0x18000f2e0`
- `KERNEL32!LeaveCriticalSection` at `0x18000f3b2`
- `KERNEL32!LeaveCriticalSection` at `0x18000f2e0`
- `KERNEL32!LeaveCriticalSection` at `0x18000f3b2`
- `KERNEL32!EnterCriticalSection` at `0x18000f2b1`
- `KERNEL32!EnterCriticalSection` at `0x18000f383`
- `KERNEL32!EnterCriticalSection` at `0x18000f2b1`
- `KERNEL32!EnterCriticalSection` at `0x18000f383`
- `KERNEL32!GlobalFree` at `0x18000f4b4`
- `KERNEL32!GlobalFree` at `0x18000f4d6`
- `KERNEL32!GlobalFree` at `0x18000f5ba`
- `KERNEL32!GlobalFree` at `0x18000f5cc`
- `KERNEL32!GlobalFree` at `0x18000f5e1`
- `KERNEL32!GlobalFree` at `0x18000f4b4`
- `KERNEL32!GlobalFree` at `0x18000f4d6`
- `KERNEL32!GlobalFree` at `0x18000f5ba`
- `KERNEL32!GlobalFree` at `0x18000f5cc`
- `KERNEL32!GlobalFree` at `0x18000f5e1`

## string_xrefs

- `0x18000f219`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18000f486`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
