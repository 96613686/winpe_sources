# DfsFindSid

- ea: `0x14005a2b0`
- end: `0x14005a3b7`
- name: `DfsFindSid`
- size: `263`
- prototype: `__int64 __fastcall(LPCWSTR lpSystemName, LPCWSTR lpAccountName)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005a010`
- `0x14005a52c`

## callees

- `0x14005a2b0`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a32a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14005a341`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14005a341`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14005a318`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14005a389`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14005a318`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14005a389`

## pseudocode

```c

```
