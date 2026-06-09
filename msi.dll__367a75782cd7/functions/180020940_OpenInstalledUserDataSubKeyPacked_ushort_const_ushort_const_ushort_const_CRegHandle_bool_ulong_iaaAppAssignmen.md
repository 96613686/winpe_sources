# OpenInstalledUserDataSubKeyPacked(ushort const *,ushort const *,ushort const *,CRegHandle &,bool,ulong,iaaAppAssignment,iaaAppAssignment *)

- ea: `0x180020940`
- end: `0x180020d3a`
- name: `?OpenInstalledUserDataSubKeyPacked@@YAKPEBG00AEAVCRegHandle@@_NKW4iaaAppAssignment@@PEAW42@@Z`
- size: `1018`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `11`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800159d4`
- `0x180015ac0`
- `0x180026c34`
- `0x18004d38c`
- `0x18006fcf4`
- `0x180073d9c`
- `0x1800f2d54`
- `0x1801928bc`
- `0x1801d3bac`
- `0x180212fdc`
- `0x180233698`

## callees

- `0x180013fe4`
- `0x180020940`
- `0x180022120`
- `0x1800250d4`
- `0x1800561c0`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180020a3f`
- `ADVAPI32!RegCloseKey` at `0x180020afe`
- `ADVAPI32!RegCloseKey` at `0x180020a3f`
- `ADVAPI32!RegCloseKey` at `0x180020afe`
- `KERNEL32!LeaveCriticalSection` at `0x180020a54`
- `KERNEL32!LeaveCriticalSection` at `0x180020b13`
- `KERNEL32!LeaveCriticalSection` at `0x180020a54`
- `KERNEL32!LeaveCriticalSection` at `0x180020b13`
- `KERNEL32!EnterCriticalSection` at `0x180020a31`
- `KERNEL32!EnterCriticalSection` at `0x180020af0`
- `KERNEL32!EnterCriticalSection` at `0x180020a31`
- `KERNEL32!EnterCriticalSection` at `0x180020af0`
- `KERNEL32!GlobalFree` at `0x180020c0f`
- `KERNEL32!GlobalFree` at `0x180020c2b`
- `KERNEL32!GlobalFree` at `0x180020cc4`
- `KERNEL32!GlobalFree` at `0x180020d14`
- `KERNEL32!GlobalFree` at `0x180020d20`
- `KERNEL32!GlobalFree` at `0x180020d2f`
- `KERNEL32!GlobalFree` at `0x180020c0f`
- `KERNEL32!GlobalFree` at `0x180020c2b`
- `KERNEL32!GlobalFree` at `0x180020cc4`
- `KERNEL32!GlobalFree` at `0x180020d14`
- `KERNEL32!GlobalFree` at `0x180020d20`
- `KERNEL32!GlobalFree` at `0x180020d2f`

## string_xrefs

- `0x180020999`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x180020be1`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
