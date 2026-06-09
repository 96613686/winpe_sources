# GetComponentClientState(ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &,ulong &,iaaAppAssignment *)

- ea: `0x18003a820`
- end: `0x18003ae4b`
- name: `?GetComponentClientState@@YA?AW4tagINSTALLSTATE@@PEBG00AEAV?$CAPITempBufferRef@G@@AEAKPEAW4iaaAppAssignment@@@Z`
- size: `1579`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180039e50`
- `0x18003ae54`
- `0x180043e60`
- `0x18021c1ac`

## callees

- `0x180010ac0`
- `0x180013b7c`
- `0x18003a820`
- `0x18003c030`
- `0x18003c0d4`
- `0x18006cb7c`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18003aa80`
- `ADVAPI32!RegQueryValueExW` at `0x18003aca0`
- `ADVAPI32!RegQueryValueExW` at `0x18003aa80`
- `ADVAPI32!RegQueryValueExW` at `0x18003aca0`
- `ADVAPI32!RegCloseKey` at `0x18003a9b1`
- `ADVAPI32!RegCloseKey` at `0x18003ab4a`
- `ADVAPI32!RegCloseKey` at `0x18003a9b1`
- `ADVAPI32!RegCloseKey` at `0x18003ab4a`
- `KERNEL32!InitializeCriticalSection` at `0x18003a88e`
- `KERNEL32!InitializeCriticalSection` at `0x18003a88e`
- `KERNEL32!DeleteCriticalSection` at `0x18003ab7a`
- `KERNEL32!DeleteCriticalSection` at `0x18003ab7a`
- `KERNEL32!LeaveCriticalSection` at `0x18003a9d0`
- `KERNEL32!LeaveCriticalSection` at `0x18003ab69`
- `KERNEL32!LeaveCriticalSection` at `0x18003a9d0`
- `KERNEL32!LeaveCriticalSection` at `0x18003ab69`
- `KERNEL32!EnterCriticalSection` at `0x18003a99b`
- `KERNEL32!EnterCriticalSection` at `0x18003ab34`
- `KERNEL32!EnterCriticalSection` at `0x18003a99b`
- `KERNEL32!EnterCriticalSection` at `0x18003ab34`
- `KERNEL32!GlobalAlloc` at `0x18003acba`
- `KERNEL32!GlobalAlloc` at `0x18003acba`
- `KERNEL32!GlobalFree` at `0x18003a93b`
- `KERNEL32!GlobalFree` at `0x18003ab92`
- `KERNEL32!GlobalFree` at `0x18003ad13`
- `KERNEL32!GlobalFree` at `0x18003ade0`
- `KERNEL32!GlobalFree` at `0x18003adf8`
- `KERNEL32!GlobalFree` at `0x18003ae0d`
- `KERNEL32!GlobalFree` at `0x18003ae25`
- `KERNEL32!GlobalFree` at `0x18003ae3a`
- `KERNEL32!GlobalFree` at `0x18003a93b`
- `KERNEL32!GlobalFree` at `0x18003ab92`
- `KERNEL32!GlobalFree` at `0x18003ad13`
- `KERNEL32!GlobalFree` at `0x18003ade0`
- `KERNEL32!GlobalFree` at `0x18003adf8`
- `KERNEL32!GlobalFree` at `0x18003ae0d`
- `KERNEL32!GlobalFree` at `0x18003ae25`
- `KERNEL32!GlobalFree` at `0x18003ae3a`

## string_xrefs

- `0x18003a913`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18003a956`: `Components`

## pseudocode

```c

```
