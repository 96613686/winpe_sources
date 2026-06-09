# myImpersonateAccountOrSid(ushort const *,WELL_KNOWN_SID_TYPE,ushort const *)

- ea: `0x18001e5f8`
- end: `0x18001e659`
- name: `?myImpersonateAccountOrSid@@YAJPEBGW4WELL_KNOWN_SID_TYPE@@0@Z`
- size: `97`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum WELL_KNOWN_SID_TYPE, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180010440`
- `0x1800156e4`

## callees

- `0x18001e46c`
- `0x18001e5f8`
- `0x18001e660`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e64b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e64b`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001e625`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001e625`

## pseudocode

```c

```
