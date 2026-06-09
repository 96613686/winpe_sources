# OpenAdvertisedProductKey(ushort const *,CRegHandle &,bool,iaaAppAssignment *)

- ea: `0x18001354c`
- end: `0x18001386f`
- name: `?OpenAdvertisedProductKey@@YAKPEBGAEAVCRegHandle@@_NPEAW4iaaAppAssignment@@@Z`
- size: `803`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct CRegHandle *, bool, enum iaaAppAssignment *)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001db00`
- `0x1800ea890`
- `0x180139da8`
- `0x180193a84`
- `0x180224714`

## callees

- `0x1800134d8`
- `0x18001354c`
- `0x180013878`
- `0x180013ecc`
- `0x1800227d0`
- `0x180025a18`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800136b0`
- `KERNEL32!LeaveCriticalSection` at `0x1800136b0`
- `KERNEL32!EnterCriticalSection` at `0x1800137e7`
- `KERNEL32!EnterCriticalSection` at `0x1800137e7`
- `KERNEL32!lstrlenW` at `0x180013592`
- `KERNEL32!lstrlenW` at `0x180013628`
- `KERNEL32!lstrlenW` at `0x180013592`
- `KERNEL32!lstrlenW` at `0x180013628`
- `KERNEL32!GlobalFree` at `0x1800135b9`
- `KERNEL32!GlobalFree` at `0x1800136f0`
- `KERNEL32!GlobalFree` at `0x1800135b9`
- `KERNEL32!GlobalFree` at `0x1800136f0`

## string_xrefs

- `0x1800135e7`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x180013829`: `Using cached product context: %s for product: %s`

## pseudocode

```c

```
