# GetHttpErrorStringFromCode(ulong)

- ea: `0x18005ed58`
- end: `0x18005ee80`
- name: `?GetHttpErrorStringFromCode@@YAPEAGK@Z`
- size: `296`
- prototype: `unsigned __int16 *__fastcall(DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18005ee90`

## callees

- `0x180010200`
- `0x180011a58`
- `0x180047240`
- `0x18005ed58`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005ed83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005ed83`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005edfc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005edfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee25`

## string_xrefs

- `0x18005ed7c`: `winhttp.dll`

## pseudocode

```c

```
