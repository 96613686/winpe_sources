# HTTP_PROTOCOL::GetIdentitySid(ushort const *,BUFFER *)

- ea: `0x18001e1dc`
- end: `0x18001e349`
- name: `?GetIdentitySid@HTTP_PROTOCOL@@AEAAJPEBGPEAVBUFFER@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(HTTP_PROTOCOL *this, const unsigned __int16 *, struct BUFFER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f810`

## callees

- `0x18001e1dc`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2ee`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001e308`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001e308`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001e25b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001e2cd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001e25b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001e2cd`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001e320`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001e320`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001e27a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001e28d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001e27a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001e28d`

## pseudocode

```c

```
