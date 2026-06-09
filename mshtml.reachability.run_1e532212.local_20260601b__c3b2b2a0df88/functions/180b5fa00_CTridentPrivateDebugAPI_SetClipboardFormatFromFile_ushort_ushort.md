# CTridentPrivateDebugAPI::SetClipboardFormatFromFile(ushort *,ushort *)

- ea: `0x180b5fa00`
- end: `0x180b5fc72`
- name: `?SetClipboardFormatFromFile@CTridentPrivateDebugAPI@@UEAAJPEAG0@Z`
- size: `626`
- prototype: `__int64 __fastcall(CTridentPrivateDebugAPI *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18005d080`
- `0x18005e684`
- `0x180b5fa00`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180b5fbca`
- `msvcrt!memcpy_s` at `0x180b5fbca`
- `KERNEL32!GlobalFree` at `0x180b5fb48`
- `KERNEL32!GlobalFree` at `0x180b5fb48`
- `KERNEL32!GlobalLock` at `0x180b5fbaa`
- `KERNEL32!GlobalLock` at `0x180b5fbaa`
- `KERNEL32!GlobalUnlock` at `0x180b5fb34`
- `KERNEL32!GlobalUnlock` at `0x180b5fb34`
- `KERNEL32!ReadFile` at `0x180b5fade`
- `KERNEL32!ReadFile` at `0x180b5fade`
- `KERNEL32!GlobalAlloc` at `0x180b5fb86`
- `KERNEL32!GlobalAlloc` at `0x180b5fb86`
- `KERNEL32!CreateFileW` at `0x180b5fa60`
- `KERNEL32!CreateFileW` at `0x180b5fa60`
- `KERNEL32!GetFileSize` at `0x180b5fa87`
- `KERNEL32!GetFileSize` at `0x180b5fa87`
- `KERNEL32!GetLastError` at `0x180b5faee`
- `KERNEL32!GetLastError` at `0x180b5fc34`
- `KERNEL32!GetLastError` at `0x180b5faee`
- `KERNEL32!GetLastError` at `0x180b5fc34`
- `KERNEL32!CloseHandle` at `0x180b5fb20`
- `KERNEL32!CloseHandle` at `0x180b5fb20`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180b5fc05`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180b5fc05`
- `USER32!OpenClipboard` at `0x180b5fbdc`
- `USER32!OpenClipboard` at `0x180b5fbdc`
- `USER32!CloseClipboard` at `0x180b5fb59`
- `USER32!CloseClipboard` at `0x180b5fb59`
- `USER32!SetClipboardData` at `0x180b5fc4f`
- `USER32!SetClipboardData` at `0x180b5fc4f`
- `USER32!RegisterClipboardFormatW` at `0x180b5fc22`
- `USER32!RegisterClipboardFormatW` at `0x180b5fc22`

## pseudocode

```c

```
