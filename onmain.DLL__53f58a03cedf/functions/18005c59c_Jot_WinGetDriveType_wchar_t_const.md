# Jot::WinGetDriveType(wchar_t const *)

- ea: `0x18005c59c`
- end: `0x18005c970`
- name: `?WinGetDriveType@Jot@@YAIPEB_W@Z`
- size: `980`
- prototype: `unsigned int __fastcall(Jot *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path`

## callers

- `0x18005c470`

## callees

- `0x18004c77c`
- `0x18005b344`
- `0x18005b408`
- `0x18005bf98`
- `0x18005c59c`
- `0x18005c970`
- `0x1800941b8`
- `0x18009424c`
- `0x180094440`
- `0x1802e50d0`
- `0x1802e5170`
- `0x180728918`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005c964`
- `KERNEL32!CloseHandle` at `0x18005c964`
- `KERNEL32!GetLastError` at `0x18005c939`
- `KERNEL32!GetLastError` at `0x18005c939`
- `KERNEL32!SetLastError` at `0x18005c70d`
- `KERNEL32!SetLastError` at `0x18005c70d`
- `KERNEL32!GetDriveTypeW` at `0x18005c62e`
- `KERNEL32!GetDriveTypeW` at `0x18005c92c`
- `KERNEL32!GetDriveTypeW` at `0x18005c62e`
- `KERNEL32!GetDriveTypeW` at `0x18005c92c`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18005c891`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18005c891`
- `KERNEL32!DeviceIoControl` at `0x18005c76f`
- `KERNEL32!DeviceIoControl` at `0x18005c76f`
- `KERNEL32!GetTickCount64` at `0x18005c6bb`
- `KERNEL32!GetTickCount64` at `0x18005c6bb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005c7cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005c8dc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005c7cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005c8dc`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005c829`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005c917`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005c829`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005c917`
- `SHLWAPI!PathStripToRootW` at `0x18005c5f5`
- `SHLWAPI!PathStripToRootW` at `0x18005c5f5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18005c835`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18005c835`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x18005c6e0`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x18005c6e0`

## pseudocode

```c

```
