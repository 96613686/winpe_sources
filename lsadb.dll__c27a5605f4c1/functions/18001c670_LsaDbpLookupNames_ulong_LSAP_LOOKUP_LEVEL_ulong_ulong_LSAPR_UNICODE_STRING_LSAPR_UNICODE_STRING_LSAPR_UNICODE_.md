# LsaDbpLookupNames(ulong,_LSAP_LOOKUP_LEVEL,ulong,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_TRUST_INFORMATION_EX,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)

- ea: `0x18001c670`
- end: `0x18001c92f`
- name: `?LsaDbpLookupNames@@YAJKW4_LSAP_LOOKUP_LEVEL@@KKPEAU_LSAPR_UNICODE_STRING@@11U_LSAPR_TRUST_INFORMATION_EX@@PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK5@Z`
- size: `703`
- prototype: `__int64 __fastcall(unsigned int, int, struct _LSAPR_UNICODE_STRING *, unsigned int, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, __int64, struct _LSAPR_REFERENCED_DOMAIN_LIST **, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x18001c670`
- `0x18001c938`
- `0x18001cc08`
- `0x18001d228`
- `0x18001d334`

## import_xrefs

- `LSASRV!LsapDbLookupNamesInPrimaryDomain` at `0x18001c71e`
- `LSASRV!LsapDbLookupNamesInPrimaryDomain` at `0x18001c846`
- `LSASRV!LsapDbLookupNamesInPrimaryDomain` at `0x18001c71e`
- `LSASRV!LsapDbLookupNamesInPrimaryDomain` at `0x18001c846`
- `LSASRV!LsaIIsDsPaused` at `0x18001c6b5`
- `LSASRV!LsaIIsDsPaused` at `0x18001c6b5`

## pseudocode

```c

```
