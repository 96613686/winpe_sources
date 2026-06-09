# _AfxGetThreadPreferredUILanguages(ulong,ulong *,wchar_t *,ulong *)

- ea: `0x1801d2ec8`
- end: `0x1801d30a9`
- name: `?_AfxGetThreadPreferredUILanguages@@YAHKPEAKPEA_W0@Z`
- size: `481`
- prototype: `int __fastcall(unsigned int pulNumLanguages, unsigned int *pwszLanguagesBuffer, wchar_t *pcchLanguagesBuffer, unsigned int *dwFlags)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1801d3bc0`

## callees

- `0x1801d2ec8`
- `0x1801d3734`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1801d2f1b`
- `KERNEL32!GetProcAddress` at `0x1801d2f1b`
- `KERNEL32!GetModuleHandleW` at `0x1801d2f06`
- `KERNEL32!GetModuleHandleW` at `0x1801d2f06`
- `KERNEL32!DecodePointer` at `0x1801d2f36`
- `KERNEL32!DecodePointer` at `0x1801d2f36`
- `KERNEL32!EncodePointer` at `0x1801d2f27`
- `KERNEL32!EncodePointer` at `0x1801d2f27`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1801d2f63`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1801d2f63`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1801d2fd3`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1801d2fd3`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d2f7b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d2fae`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d2feb`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d3025`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d305c`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d2f7b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d2fae`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d2feb`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d3025`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801d305c`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d2f90`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d2fc7`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d3004`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d303e`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d3074`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d2f90`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d2fc7`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d3004`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d303e`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801d3074`

## string_xrefs

- `0x1801d2eff`: `kernel32.dll`
- `0x1801d2f11`: `GetThreadPreferredUILanguages`

## pseudocode

```c

```
