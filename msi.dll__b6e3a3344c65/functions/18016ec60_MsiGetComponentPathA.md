# MsiGetComponentPathA

- ea: `0x18016ec60`
- end: `0x18016f0a6`
- name: `MsiGetComponentPathA`
- size: `1094`
- prototype: `INSTALLSTATE __stdcall(LPCSTR szProduct, LPCSTR szComponent, LPSTR lpPathBuf, LPDWORD pcchBuf)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x18016eb30`

## callees

- `0x18001cab0`
- `0x18001d960`
- `0x1800250d4`
- `0x180051d20`
- `0x180051e50`
- `0x1800520f4`
- `0x180054124`
- `0x18008f3e8`
- `0x18016ec60`
- `0x18019a2d0`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18016ecd3`
- `KERNEL32!lstrlenA` at `0x18016ecfd`
- `KERNEL32!lstrlenA` at `0x18016ecd3`
- `KERNEL32!lstrlenA` at `0x18016ecfd`
- `KERNEL32!GlobalFree` at `0x18016eda0`
- `KERNEL32!GlobalFree` at `0x18016edbc`
- `KERNEL32!GlobalFree` at `0x18016eec5`
- `KERNEL32!GlobalFree` at `0x18016eeda`
- `KERNEL32!GlobalFree` at `0x18016ef3d`
- `KERNEL32!GlobalFree` at `0x18016ef66`
- `KERNEL32!GlobalFree` at `0x18016ef8a`
- `KERNEL32!GlobalFree` at `0x18016efa6`
- `KERNEL32!GlobalFree` at `0x18016efdb`
- `KERNEL32!GlobalFree` at `0x18016f003`
- `KERNEL32!GlobalFree` at `0x18016f01f`
- `KERNEL32!GlobalFree` at `0x18016f049`
- `KERNEL32!GlobalFree` at `0x18016f065`
- `KERNEL32!GlobalFree` at `0x18016eda0`
- `KERNEL32!GlobalFree` at `0x18016edbc`
- `KERNEL32!GlobalFree` at `0x18016eec5`
- `KERNEL32!GlobalFree` at `0x18016eeda`
- `KERNEL32!GlobalFree` at `0x18016ef3d`
- `KERNEL32!GlobalFree` at `0x18016ef66`
- `KERNEL32!GlobalFree` at `0x18016ef8a`
- `KERNEL32!GlobalFree` at `0x18016efa6`
- `KERNEL32!GlobalFree` at `0x18016efdb`
- `KERNEL32!GlobalFree` at `0x18016f003`
- `KERNEL32!GlobalFree` at `0x18016f01f`
- `KERNEL32!GlobalFree` at `0x18016f049`
- `KERNEL32!GlobalFree` at `0x18016f065`

## pseudocode

```c

```
