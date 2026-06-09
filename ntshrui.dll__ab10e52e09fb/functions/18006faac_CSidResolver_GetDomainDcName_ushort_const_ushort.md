# CSidResolver::_GetDomainDcName(ushort const *,ushort * *)

- ea: `0x18006faac`
- end: `0x18006fb2d`
- name: `?_GetDomainDcName@CSidResolver@@IEAAJPEBGPEAPEAG@Z`
- size: `129`
- prototype: `int(CSidResolver *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18006f048`
- `0x18006ff1c`

## callees

- `0x18006faac`

## import_xrefs

- `SHLWAPI!StrDupW` at `0x18006fafc`
- `SHLWAPI!StrDupW` at `0x18006fafc`
- `netutils!NetApiBufferFree` at `0x18006fb0d`
- `netutils!NetApiBufferFree` at `0x18006fb0d`
- `logoncli!DsGetDcNameW` at `0x18006faea`
- `logoncli!DsGetDcNameW` at `0x18006faea`

## pseudocode

```c

```
