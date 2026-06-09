# GetUserSID

- ea: `0x180038330`
- end: `0x18003848b`
- name: `GetUserSID`
- size: `347`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038494`
- `0x180038628`

## callees

- `0x180038330`
- `0x180055550`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18003840c`
- `msvcrt!wcsrchr` at `0x18003840c`
- `msvcrt!realloc` at `0x1800383f2`
- `msvcrt!realloc` at `0x1800383f2`
- `msvcrt!malloc` at `0x18003838d`
- `msvcrt!malloc` at `0x18003838d`
- `msvcrt!free` at `0x180038458`
- `msvcrt!free` at `0x180038458`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003841f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003841f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800383d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003843b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800383d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003843b`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180038381`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180038381`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800383cb`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800383cb`

## pseudocode

```c

```
