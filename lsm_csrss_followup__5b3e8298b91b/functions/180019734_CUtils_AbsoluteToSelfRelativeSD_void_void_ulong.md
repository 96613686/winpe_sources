# CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)

- ea: `0x180019734`
- end: `0x180019831`
- name: `?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z`
- size: `253`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018e68`
- `0x180018f6c`

## callees

- `0x1800074c0`
- `0x180019734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001980c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001980c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001976b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800197c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001976b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800197c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019793`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019793`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019829`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019829`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18001975a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800197b1`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18001975a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800197b1`

## pseudocode

```c

```
