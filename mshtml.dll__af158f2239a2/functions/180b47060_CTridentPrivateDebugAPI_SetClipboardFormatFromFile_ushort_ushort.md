# CTridentPrivateDebugAPI::SetClipboardFormatFromFile(ushort *,ushort *)

- ea: `0x180b47060`
- end: `0x180b4726e`
- name: `?SetClipboardFormatFromFile@CTridentPrivateDebugAPI@@UEAAJPEAG0@Z`
- size: `526`
- prototype: `__int64 __fastcall(CTridentPrivateDebugAPI *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1801bf528`
- `0x1801c0b08`
- `0x180b47060`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180b471ea`
- `msvcrt!memcpy_s` at `0x180b471ea`
- `KERNEL32!GlobalFree` at `0x180b47184`
- `KERNEL32!GlobalFree` at `0x180b47184`
- `KERNEL32!GlobalLock` at `0x180b471d0`
- `KERNEL32!GlobalLock` at `0x180b471d0`
- `KERNEL32!GlobalUnlock` at `0x180b47176`
- `KERNEL32!GlobalUnlock` at `0x180b47176`
- `KERNEL32!ReadFile` at `0x180b47132`
- `KERNEL32!ReadFile` at `0x180b47132`
- `KERNEL32!GlobalAlloc` at `0x180b471b5`
- `KERNEL32!GlobalAlloc` at `0x180b471b5`
- `KERNEL32!CreateFileW` at `0x180b470c0`
- `KERNEL32!CreateFileW` at `0x180b470c0`
- `KERNEL32!GetFileSize` at `0x180b470e1`
- `KERNEL32!GetFileSize` at `0x180b470e1`
- `KERNEL32!GetLastError` at `0x180b4713c`
- `KERNEL32!GetLastError` at `0x180b4723c`
- `KERNEL32!GetLastError` at `0x180b4713c`
- `KERNEL32!GetLastError` at `0x180b4723c`
- `KERNEL32!CloseHandle` at `0x180b47168`
- `KERNEL32!CloseHandle` at `0x180b47168`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180b47219`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180b47219`
- `USER32!OpenClipboard` at `0x180b471f6`
- `USER32!OpenClipboard` at `0x180b471f6`
- `USER32!CloseClipboard` at `0x180b4718f`
- `USER32!CloseClipboard` at `0x180b4718f`
- `USER32!SetClipboardData` at `0x180b47251`
- `USER32!SetClipboardData` at `0x180b47251`
- `USER32!RegisterClipboardFormatW` at `0x180b47230`
- `USER32!RegisterClipboardFormatW` at `0x180b47230`

## pseudocode

```c

```
