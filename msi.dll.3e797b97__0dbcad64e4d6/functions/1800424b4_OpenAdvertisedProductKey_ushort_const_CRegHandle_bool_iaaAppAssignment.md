# OpenAdvertisedProductKey(ushort const *,CRegHandle &,bool,iaaAppAssignment *)

- ea: `0x1800424b4`
- end: `0x1800427fc`
- name: `?OpenAdvertisedProductKey@@YAKPEBGAEAVCRegHandle@@_NPEAW4iaaAppAssignment@@@Z`
- size: `840`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct CRegHandle *, bool, enum iaaAppAssignment *)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x180042810`
- `0x1800f2fa0`
- `0x18013ef88`
- `0x18019a634`
- `0x18022e3f0`

## callees

- `0x18000c4bc`
- `0x180011280`
- `0x18003a444`
- `0x180041cc0`
- `0x180042394`
- `0x1800424b4`
- `0x180265240`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18004262a`
- `KERNEL32!LeaveCriticalSection` at `0x18004262a`
- `KERNEL32!EnterCriticalSection` at `0x18004276e`
- `KERNEL32!EnterCriticalSection` at `0x18004276e`
- `KERNEL32!lstrlenW` at `0x1800424fa`
- `KERNEL32!lstrlenW` at `0x18004259c`
- `KERNEL32!lstrlenW` at `0x1800424fa`
- `KERNEL32!lstrlenW` at `0x18004259c`
- `KERNEL32!GlobalFree` at `0x180042527`
- `KERNEL32!GlobalFree` at `0x180042671`
- `KERNEL32!GlobalFree` at `0x180042527`
- `KERNEL32!GlobalFree` at `0x180042671`

## string_xrefs

- `0x1800427b6`: `Using cached product context: %s for product: %s`

## pseudocode

```c

```
