# SampDsAuthzCreateStarterContextFSP(void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)

- ea: `0x1804113d0`
- end: `0x1804116e3`
- name: `?SampDsAuthzCreateStarterContextFSP@@YAJPEAXPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@Z`
- size: `787`
- prototype: `__int64 __fastcall(PSID pSid, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180410934`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x18003de48`
- `0x1804113d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041145c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804115aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804115b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804115be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041145c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804115aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804115b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804115be`
- `AUTHZ!AuthzFreeContext` at `0x1804116bd`
- `AUTHZ!AuthzFreeContext` at `0x1804116cc`
- `AUTHZ!AuthzFreeContext` at `0x1804116bd`
- `AUTHZ!AuthzFreeContext` at `0x1804116cc`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18041143a`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18041143a`
- `AUTHZ!AuthzAddSidsToContext` at `0x18041159c`
- `AUTHZ!AuthzAddSidsToContext` at `0x18041159c`

## pseudocode

```c

```
