# LsapResolveIdentityInternetSid(void *,_UNICODE_STRING *,_UNICODE_STRING *,void * *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180128838`
- end: `0x180128d24`
- name: `?LsapResolveIdentityInternetSid@@YAJPEAXPEAU_UNICODE_STRING@@1PEAPEAX11111@Z`
- size: `1260`
- prototype: `int(void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void **, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180064628`
- `0x180114400`
- `0x180124194`

## callees

- `0x1800040d0`
- `0x180009330`
- `0x18000c300`
- `0x180011278`
- `0x18005fecc`
- `0x1800604d4`
- `0x18006064c`
- `0x180060c8c`
- `0x180060cb0`
- `0x1800626ac`
- `0x180082da0`
- `0x1800b86d0`
- `0x1800bd6e0`
- `0x180128838`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1801288aa`
- `ntdll!RtlInitUnicodeString` at `0x1801288bf`
- `ntdll!RtlInitUnicodeString` at `0x1801288d4`
- `ntdll!RtlInitUnicodeString` at `0x1801288e9`
- `ntdll!RtlInitUnicodeString` at `0x1801288fe`
- `ntdll!RtlInitUnicodeString` at `0x180128bbe`
- `ntdll!RtlInitUnicodeString` at `0x180128bd9`
- `ntdll!RtlInitUnicodeString` at `0x180128bf9`
- `ntdll!RtlInitUnicodeString` at `0x180128c24`
- `ntdll!RtlInitUnicodeString` at `0x180128c3f`
- `ntdll!RtlInitUnicodeString` at `0x1801288aa`
- `ntdll!RtlInitUnicodeString` at `0x1801288bf`
- `ntdll!RtlInitUnicodeString` at `0x1801288d4`
- `ntdll!RtlInitUnicodeString` at `0x1801288e9`
- `ntdll!RtlInitUnicodeString` at `0x1801288fe`
- `ntdll!RtlInitUnicodeString` at `0x180128bbe`
- `ntdll!RtlInitUnicodeString` at `0x180128bd9`
- `ntdll!RtlInitUnicodeString` at `0x180128bf9`
- `ntdll!RtlInitUnicodeString` at `0x180128c24`
- `ntdll!RtlInitUnicodeString` at `0x180128c3f`

## string_xrefs

- `0x180128866`: `LsapResolveIdentityInternetSid`
- `0x180128cf5`: `LsapResolveIdentityInternetSid`
- `0x180128ba2`: `ProvEntry->ProviderTable.LookUpSIDFromIdentityName`

## pseudocode

```c

```
