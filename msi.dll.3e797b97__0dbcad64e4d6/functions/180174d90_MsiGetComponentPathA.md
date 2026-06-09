# MsiGetComponentPathA

- ea: `0x180174d90`
- end: `0x180175231`
- name: `MsiGetComponentPathA`
- size: `1185`
- prototype: `INSTALLSTATE __stdcall(LPCSTR szProduct, LPCSTR szComponent, LPSTR lpPathBuf, LPDWORD pcchBuf)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180174c50`

## callees

- `0x180013b7c`
- `0x180044960`
- `0x1800459c0`
- `0x180086264`
- `0x1800b47bc`
- `0x1800b5ebc`
- `0x1800b6f2c`
- `0x1800b72c4`
- `0x180174d90`
- `0x1801a11a0`
- `0x180265240`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x180174e03`
- `KERNEL32!lstrlenA` at `0x180174e33`
- `KERNEL32!lstrlenA` at `0x180174e03`
- `KERNEL32!lstrlenA` at `0x180174e33`
- `KERNEL32!GlobalFree` at `0x180174edc`
- `KERNEL32!GlobalFree` at `0x180174efe`
- `KERNEL32!GlobalFree` at `0x18017500d`
- `KERNEL32!GlobalFree` at `0x180175028`
- `KERNEL32!GlobalFree` at `0x180175091`
- `KERNEL32!GlobalFree` at `0x1801750c0`
- `KERNEL32!GlobalFree` at `0x1801750ea`
- `KERNEL32!GlobalFree` at `0x18017510c`
- `KERNEL32!GlobalFree` at `0x180175147`
- `KERNEL32!GlobalFree` at `0x180175175`
- `KERNEL32!GlobalFree` at `0x180175197`
- `KERNEL32!GlobalFree` at `0x1801751c7`
- `KERNEL32!GlobalFree` at `0x1801751e9`
- `KERNEL32!GlobalFree` at `0x180174edc`
- `KERNEL32!GlobalFree` at `0x180174efe`
- `KERNEL32!GlobalFree` at `0x18017500d`
- `KERNEL32!GlobalFree` at `0x180175028`
- `KERNEL32!GlobalFree` at `0x180175091`
- `KERNEL32!GlobalFree` at `0x1801750c0`
- `KERNEL32!GlobalFree` at `0x1801750ea`
- `KERNEL32!GlobalFree` at `0x18017510c`
- `KERNEL32!GlobalFree` at `0x180175147`
- `KERNEL32!GlobalFree` at `0x180175175`
- `KERNEL32!GlobalFree` at `0x180175197`
- `KERNEL32!GlobalFree` at `0x1801751c7`
- `KERNEL32!GlobalFree` at `0x1801751e9`

## pseudocode

```c

```
