# GetErrorText

- ea: `0x180048d84`
- end: `0x180048f05`
- name: `GetErrorText`
- size: `385`
- prototype: `_BOOL8 __fastcall(__int64 dwMessageId, LPWSTR lpBuffer)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180006014`
- `0x180048b6c`

## callees

- `0x18001e944`
- `0x18003bea0`
- `0x180048d84`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048ec7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048ec7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180048e5c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180048e5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180048dfb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180048dfb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180048eb4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180048eb4`

## string_xrefs

- `0x180048df4`: `NETMSG.DLL`

## pseudocode

```c

```
