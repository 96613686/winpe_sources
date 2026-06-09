# OpenInstalledProductInstallPropertiesKeyPacked(ushort const *,ushort const *,CRegHandle &,bool)

- ea: `0x18000ed40`
- end: `0x18000f1ac`
- name: `?OpenInstalledProductInstallPropertiesKeyPacked@@YAKPEBG0AEAVCRegHandle@@_N@Z`
- size: `1132`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, struct CRegHandle *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800f3270`
- `0x180197ac4`

## callees

- `0x18000ed40`
- `0x180010ac0`
- `0x180013b7c`
- `0x18003a560`
- `0x18004cbfc`
- `0x1800b8f60`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000ee8c`
- `ADVAPI32!RegCloseKey` at `0x18000ef7e`
- `ADVAPI32!RegCloseKey` at `0x18000ee8c`
- `ADVAPI32!RegCloseKey` at `0x18000ef7e`
- `KERNEL32!LeaveCriticalSection` at `0x18000eeab`
- `KERNEL32!LeaveCriticalSection` at `0x18000ef9d`
- `KERNEL32!LeaveCriticalSection` at `0x18000eeab`
- `KERNEL32!LeaveCriticalSection` at `0x18000ef9d`
- `KERNEL32!EnterCriticalSection` at `0x18000ee78`
- `KERNEL32!EnterCriticalSection` at `0x18000ef6a`
- `KERNEL32!EnterCriticalSection` at `0x18000ee78`
- `KERNEL32!EnterCriticalSection` at `0x18000ef6a`
- `KERNEL32!GlobalFree` at `0x18000ef3a`
- `KERNEL32!GlobalFree` at `0x18000f0a2`
- `KERNEL32!GlobalFree` at `0x18000f113`
- `KERNEL32!GlobalFree` at `0x18000f15f`
- `KERNEL32!GlobalFree` at `0x18000f171`
- `KERNEL32!GlobalFree` at `0x18000f186`
- `KERNEL32!GlobalFree` at `0x18000f19b`
- `KERNEL32!GlobalFree` at `0x18000ef3a`
- `KERNEL32!GlobalFree` at `0x18000f0a2`
- `KERNEL32!GlobalFree` at `0x18000f113`
- `KERNEL32!GlobalFree` at `0x18000f15f`
- `KERNEL32!GlobalFree` at `0x18000f171`
- `KERNEL32!GlobalFree` at `0x18000f186`
- `KERNEL32!GlobalFree` at `0x18000f19b`

## string_xrefs

- `0x18000edf6`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18000f074`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18000ed81`: `InstallProperties`

## pseudocode

```c

```
