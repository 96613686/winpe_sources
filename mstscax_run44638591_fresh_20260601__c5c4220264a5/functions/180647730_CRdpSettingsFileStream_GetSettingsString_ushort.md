# CRdpSettingsFileStream::GetSettingsString(ushort * *)

- ea: `0x180647730`
- end: `0x180647c20`
- name: `?GetSettingsString@CRdpSettingsFileStream@@UEAAJPEAPEAG@Z`
- size: `1264`
- prototype: `__int64 __fastcall(CRdpSettingsFileStream *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x180647730`
- `0x180647f14`
- `0x180688f3e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1806477fe`
- `KERNEL32!GetLastError` at `0x180647ba5`
- `KERNEL32!GetLastError` at `0x1806477fe`
- `KERNEL32!GetLastError` at `0x180647ba5`
- `KERNEL32!LocalAlloc` at `0x1806478ea`
- `KERNEL32!LocalAlloc` at `0x180647aaa`
- `KERNEL32!LocalAlloc` at `0x1806478ea`
- `KERNEL32!LocalAlloc` at `0x180647aaa`
- `KERNEL32!LocalFree` at `0x180647973`
- `KERNEL32!LocalFree` at `0x180647b67`
- `KERNEL32!LocalFree` at `0x180647c15`
- `KERNEL32!LocalFree` at `0x180647973`
- `KERNEL32!LocalFree` at `0x180647b67`
- `KERNEL32!LocalFree` at `0x180647c15`
- `KERNEL32!ReadFile` at `0x1806477f1`
- `KERNEL32!ReadFile` at `0x180647966`
- `KERNEL32!ReadFile` at `0x1806477f1`
- `KERNEL32!ReadFile` at `0x180647966`
- `KERNEL32!MultiByteToWideChar` at `0x180647a96`
- `KERNEL32!MultiByteToWideChar` at `0x180647b9b`
- `KERNEL32!MultiByteToWideChar` at `0x180647a96`
- `KERNEL32!MultiByteToWideChar` at `0x180647b9b`
- `KERNEL32!GetFileSize` at `0x1806477a9`
- `KERNEL32!GetFileSize` at `0x1806477a9`
- `ADVAPI32!IsTextUnicode` at `0x180647a16`
- `ADVAPI32!IsTextUnicode` at `0x180647a16`

## string_xrefs

- `0x1806478ab`: `Failed to move pointer to the beginning of the file!`
- `0x1806479be`: `Failed to move pointer to the beginning of the file!`

## pseudocode

```c

```
