# LsaDbrQueryTrustedDomainInfo(void *,_LSAPR_SID *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO * *)

- ea: `0x18000e920`
- end: `0x18000e9de`
- name: `?LsaDbrQueryTrustedDomainInfo@@YAJPEAXPEAU_LSAPR_SID@@W4_TRUSTED_INFORMATION_CLASS@@PEAPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(void *, PSID Sid, enum _TRUSTED_INFORMATION_CLASS, union _LSAPR_TRUSTED_DOMAIN_INFO **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x18000d5e0`
- `0x18000d680`
- `0x18000e920`
- `0x180035ea8`
- `0x180036d24`

## import_xrefs

- `LSASRV!LsapCloseHandle` at `0x18000e9c3`
- `LSASRV!LsapCloseHandle` at `0x18000e9c3`
- `LSASRV!LsapDbVerifyInfoQueryTrustedDomain` at `0x18000e975`
- `LSASRV!LsapDbVerifyInfoQueryTrustedDomain` at `0x18000e975`

## pseudocode

```c

```
