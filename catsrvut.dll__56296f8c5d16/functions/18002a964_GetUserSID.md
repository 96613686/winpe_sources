# GetUserSID

- ea: `0x18002a964`
- end: `0x18002aabf`
- name: `GetUserSID`
- size: `347`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002aac8`
- `0x18002ac5c`

## callees

- `0x18002a964`
- `0x180055880`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002aa40`
- `msvcrt!wcsrchr` at `0x18002aa40`
- `msvcrt!realloc` at `0x18002aa26`
- `msvcrt!realloc` at `0x18002aa26`
- `msvcrt!malloc` at `0x18002a9c1`
- `msvcrt!malloc` at `0x18002a9c1`
- `msvcrt!free` at `0x18002aa8c`
- `msvcrt!free` at `0x18002aa8c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002aa53`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002aa53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa6f`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002a9b5`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002a9b5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002a9ff`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002a9ff`

## pseudocode

```c

```
