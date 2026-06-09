# Acl::MakeAcl<AuditAce>(AceList<AuditAce> &)

- ea: `0x1401c5988`
- end: `0x1401c5c24`
- name: `??$MakeAcl@VAuditAce@@@Acl@@IEAAPEAVFrsStatus@@AEAV?$AceList@VAuditAce@@@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(Acl *this)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004b83c`
- `0x14004ef40`
- `0x1400c06b8`
- `0x1401c636c`

## callees

- `0x14001bf80`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401c5988`
- `0x1401c7a3c`
- `0x1401c7fbc`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c5acb`
- `KERNEL32!GetLastError` at `0x1401c5bb0`
- `KERNEL32!GetLastError` at `0x1401c5acb`
- `KERNEL32!GetLastError` at `0x1401c5bb0`
- `KERNEL32!GetCurrentThreadId` at `0x1401c5abd`
- `KERNEL32!GetCurrentThreadId` at `0x1401c5ba2`
- `KERNEL32!GetCurrentThreadId` at `0x1401c5abd`
- `KERNEL32!GetCurrentThreadId` at `0x1401c5ba2`
- `ADVAPI32!AddAce` at `0x1401c5b84`
- `ADVAPI32!AddAce` at `0x1401c5b84`
- `ADVAPI32!InitializeAcl` at `0x1401c5aa0`
- `ADVAPI32!InitializeAcl` at `0x1401c5aa0`

## string_xrefs

- `0x1401c5ae7`: `Acl::MakeAcl`
- `0x1401c5b36`: `Acl::MakeAcl`
- `0x1401c5adc`: `base\fs\remotefs\frs\src\util\SecurityUtil.h`
- `0x1401c5b3d`: `base\fs\remotefs\frs\src\util\SecurityUtil.h`

## pseudocode

```c

```
