# CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)

- ea: `0x18000a4a0`
- end: `0x18000a5d8`
- name: `?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z`
- size: `312`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ad4`
- `0x180009bf4`

## callees

- `0x1800077a0`
- `0x18000a4a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a550`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a550`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a515`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a515`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5ca`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18000a4c6`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18000a539`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18000a4c6`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18000a539`

## pseudocode

```c

```
