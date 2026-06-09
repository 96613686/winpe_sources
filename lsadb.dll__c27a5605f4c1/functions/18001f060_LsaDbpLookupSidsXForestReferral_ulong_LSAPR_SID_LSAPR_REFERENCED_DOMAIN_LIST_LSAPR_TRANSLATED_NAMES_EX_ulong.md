# LsaDbpLookupSidsXForestReferral(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *)

- ea: `0x18001f060`
- end: `0x18001f11d`
- name: `?LsaDbpLookupSidsXForestReferral@@YAJKPEAPEAU_LSAPR_SID@@PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK@Z`
- size: `189`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, struct _LSAPR_SID **@<rdx>, struct _LSAPR_REFERENCED_DOMAIN_LIST **@<r8>, struct _LSAPR_TRANSLATED_NAMES_EX *@<r9>, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18001c150`
- `0x18001edf4`
- `0x18001f060`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f0d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f0eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f0d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f0eb`

## pseudocode

```c

```
