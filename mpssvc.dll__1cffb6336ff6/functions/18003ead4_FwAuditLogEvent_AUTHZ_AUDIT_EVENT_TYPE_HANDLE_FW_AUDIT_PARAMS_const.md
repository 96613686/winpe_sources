# FwAuditLogEvent(AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *,FW_AUDIT_PARAMS_ const *)

- ea: `0x18003ead4`
- end: `0x18003ebce`
- name: `?FwAuditLogEvent@@YAJPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@PEBUFW_AUDIT_PARAMS_@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *, const struct FW_AUDIT_PARAMS_ *)`
- caller_count: `18`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18003e3a4`
- `0x18003e55c`
- `0x18003e798`
- `0x18005c96c`
- `0x180079940`
- `0x18007a608`
- `0x18007a720`
- `0x18007a878`
- `0x18007a9fc`
- `0x18007ab14`
- `0x18007abec`
- `0x18007aca4`
- `0x18007ad5c`
- `0x18007ae8c`
- `0x18007afac`
- `0x18007b0b8`
- `0x18007b1b4`
- `0x18007b27c`

## callees

- `0x1800093b0`
- `0x18003ead4`
- `0x18006f520`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb9a`
- `AUTHZ!AuthziLogAuditEvent` at `0x18003eb4d`
- `AUTHZ!AuthziLogAuditEvent` at `0x18003eb4d`
- `AUTHZ!AuthzFreeAuditEvent` at `0x18003eb7a`
- `AUTHZ!AuthzFreeAuditEvent` at `0x18003eb7a`
- `fwbase!FwReportReturnError` at `0x18003ebc4`
- `fwbase!FwReportReturnError` at `0x18003ebc4`
- `fwbase!FwReportErrorAsWinError` at `0x18003ebb1`
- `fwbase!FwReportErrorAsWinError` at `0x18003ebb1`

## string_xrefs

- `0x18003eb91`: `FwAuditEventCreate`

## pseudocode

```c

```
