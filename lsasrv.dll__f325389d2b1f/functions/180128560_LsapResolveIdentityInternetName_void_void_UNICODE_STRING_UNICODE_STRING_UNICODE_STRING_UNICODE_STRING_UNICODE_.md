# LsapResolveIdentityInternetName(void *,void *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180128560`
- end: `0x180128831`
- name: `?LsapResolveIdentityInternetName@@YAJPEAX0PEAU_UNICODE_STRING@@1111@Z`
- size: `721`
- prototype: `int(void *, void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180061e88`

## callees

- `0x1800040d0`
- `0x18000c300`
- `0x180011278`
- `0x18005ec24`
- `0x18005fecc`
- `0x18006064c`
- `0x180060c8c`
- `0x180060cb0`
- `0x1800626ac`
- `0x180128560`
- `0x18014d010`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180128634`
- `ntdll!RtlValidSid` at `0x180128634`
- `ntdll!RtlInitUnicodeString` at `0x1801285c2`
- `ntdll!RtlInitUnicodeString` at `0x1801285d3`
- `ntdll!RtlInitUnicodeString` at `0x1801285e5`
- `ntdll!RtlInitUnicodeString` at `0x1801285f7`
- `ntdll!RtlInitUnicodeString` at `0x180128609`
- `ntdll!RtlInitUnicodeString` at `0x18012870f`
- `ntdll!RtlInitUnicodeString` at `0x18012872f`
- `ntdll!RtlInitUnicodeString` at `0x18012874a`
- `ntdll!RtlInitUnicodeString` at `0x180128776`
- `ntdll!RtlInitUnicodeString` at `0x180128792`
- `ntdll!RtlInitUnicodeString` at `0x1801285c2`
- `ntdll!RtlInitUnicodeString` at `0x1801285d3`
- `ntdll!RtlInitUnicodeString` at `0x1801285e5`
- `ntdll!RtlInitUnicodeString` at `0x1801285f7`
- `ntdll!RtlInitUnicodeString` at `0x180128609`
- `ntdll!RtlInitUnicodeString` at `0x18012870f`
- `ntdll!RtlInitUnicodeString` at `0x18012872f`
- `ntdll!RtlInitUnicodeString` at `0x18012874a`
- `ntdll!RtlInitUnicodeString` at `0x180128776`
- `ntdll!RtlInitUnicodeString` at `0x180128792`

## string_xrefs

- `0x180128663`: `LsapRefIdProvByInternetSid`
- `0x1801286fb`: `ProvEntry->ProviderTable.LookUpSIDFromIdentityName`
- `0x1801287ad`: `SID Validation`

## pseudocode

```c

```
