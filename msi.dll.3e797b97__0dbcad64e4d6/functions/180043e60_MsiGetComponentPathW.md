# MsiGetComponentPathW

- ea: `0x180043e60`
- end: `0x18004454e`
- name: `MsiGetComponentPathW`
- size: `1774`
- prototype: `INSTALLSTATE __stdcall(LPCWSTR szProduct, LPCWSTR szComponent, LPWSTR lpPathBuf, LPDWORD pcchBuf)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1800b7080`
- `0x180171ac0`

## callees

- `0x180013b7c`
- `0x18003a820`
- `0x18003c030`
- `0x18003c0d4`
- `0x180042810`
- `0x180043e60`
- `0x180044960`
- `0x1800459c0`
- `0x180086264`
- `0x180095d40`
- `0x180096164`
- `0x18009fdf0`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800440eb`
- `ADVAPI32!RegQueryValueExW` at `0x1800440eb`
- `KERNEL32!InitializeCriticalSection` at `0x18004408e`
- `KERNEL32!InitializeCriticalSection` at `0x18004408e`
- `KERNEL32!lstrlenW` at `0x180043ecd`
- `KERNEL32!lstrlenW` at `0x180043faa`
- `KERNEL32!lstrlenW` at `0x180043ecd`
- `KERNEL32!lstrlenW` at `0x180043faa`
- `KERNEL32!GlobalFree` at `0x180044178`
- `KERNEL32!GlobalFree` at `0x1800441c7`
- `KERNEL32!GlobalFree` at `0x1800441dc`
- `KERNEL32!GlobalFree` at `0x1800441f1`
- `KERNEL32!GlobalFree` at `0x180044203`
- `KERNEL32!GlobalFree` at `0x180044299`
- `KERNEL32!GlobalFree` at `0x1800442cb`
- `KERNEL32!GlobalFree` at `0x18004430a`
- `KERNEL32!GlobalFree` at `0x18004431f`
- `KERNEL32!GlobalFree` at `0x180044387`
- `KERNEL32!GlobalFree` at `0x180044404`
- `KERNEL32!GlobalFree` at `0x18004442c`
- `KERNEL32!GlobalFree` at `0x18004448c`
- `KERNEL32!GlobalFree` at `0x18004451d`
- `KERNEL32!GlobalFree` at `0x180044178`
- `KERNEL32!GlobalFree` at `0x1800441c7`
- `KERNEL32!GlobalFree` at `0x1800441dc`
- `KERNEL32!GlobalFree` at `0x1800441f1`
- `KERNEL32!GlobalFree` at `0x180044203`
- `KERNEL32!GlobalFree` at `0x180044299`
- `KERNEL32!GlobalFree` at `0x1800442cb`
- `KERNEL32!GlobalFree` at `0x18004430a`
- `KERNEL32!GlobalFree` at `0x18004431f`
- `KERNEL32!GlobalFree` at `0x180044387`
- `KERNEL32!GlobalFree` at `0x180044404`
- `KERNEL32!GlobalFree` at `0x18004442c`
- `KERNEL32!GlobalFree` at `0x18004448c`
- `KERNEL32!GlobalFree` at `0x18004451d`

## pseudocode

```c

```
