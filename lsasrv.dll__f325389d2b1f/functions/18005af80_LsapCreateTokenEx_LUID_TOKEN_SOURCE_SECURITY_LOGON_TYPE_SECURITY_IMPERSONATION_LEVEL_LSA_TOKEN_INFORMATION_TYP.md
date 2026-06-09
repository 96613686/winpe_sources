# LsapCreateTokenEx(_LUID *,_TOKEN_SOURCE *,_SECURITY_LOGON_TYPE,_SECURITY_IMPERSONATION_LEVEL,_LSA_TOKEN_INFORMATION_TYPE,void *,_TOKEN_GROUPS *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_SECPKG_SESSIONINFO_TYPE,void * *,long *)

- ea: `0x18005af80`
- end: `0x18005b513`
- name: `?LsapCreateTokenEx@@YAJPEAU_LUID@@PEAU_TOKEN_SOURCE@@W4_SECURITY_LOGON_TYPE@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_LSA_TOKEN_INFORMATION_TYPE@@PEAXPEAU_TOKEN_GROUPS@@PEAU_UNICODE_STRING@@75W4_SECPKG_SESSIONINFO_TYPE@@PEAPEAXPEAJ@Z`
- size: `1427`
- prototype: `__int64 __usercall@<rax>(struct _LUID *@<rcx>, struct _TOKEN_SOURCE *@<rdx>, enum _SECURITY_LOGON_TYPE@<r8d>, enum _SECURITY_IMPERSONATION_LEVEL@<r9d>, enum _LSA_TOKEN_INFORMATION_TYPE, void *, struct _TOKEN_GROUPS *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *, enum _SECPKG_SESSIONINFO_TYPE, PHANDLE TokenHandle, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d80a0`

## callees

- `0x180006240`
- `0x1800072c8`
- `0x18000b7d0`
- `0x180011278`
- `0x1800284d4`
- `0x180056f84`
- `0x180059a94`
- `0x18005af80`
- `0x18005c8b4`
- `0x180081fa8`
- `0x1800890b4`
- `0x1800b86d0`
- `0x1800bc040`
- `0x1800bc2c4`
- `0x1800f0364`
- `0x1800f0584`

## import_xrefs

- `LSAADT!__imp_?LsapCrashOnAuditFailState@@3KA` at `0x18005b0d3`
- `LSAADT!__imp_?LsapAdtSglSidCount@@3KA` at `0x18005b2d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b4e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b4e4`
- `ntdll!NtClose` at `0x18005b422`
- `ntdll!NtClose` at `0x18005b422`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x18005b2f2`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x18005b2f2`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditSpecialPrivileges` at `0x18005b36d`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditSpecialPrivileges` at `0x18005b36d`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapReportGroupsAtLogonEvent` at `0x18005b483`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapReportGroupsAtLogonEvent` at `0x18005b483`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapReportClaimsAtLogonEvent` at `0x18005b4c2`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapReportClaimsAtLogonEvent` at `0x18005b4c2`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtGenerateSpecialGroupsLogonAudit` at `0x18005b341`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtGenerateSpecialGroupsLogonAudit` at `0x18005b341`

## pseudocode

```c

```
