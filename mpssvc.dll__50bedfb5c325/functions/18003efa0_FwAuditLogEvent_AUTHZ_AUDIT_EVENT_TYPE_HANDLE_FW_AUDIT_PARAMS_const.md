# FwAuditLogEvent(AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *,FW_AUDIT_PARAMS_ const *)

- ea: `0x18003efa0`
- end: `0x18003f0c2`
- name: `?FwAuditLogEvent@@YAJPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@PEBUFW_AUDIT_PARAMS_@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *, const struct FW_AUDIT_PARAMS_ *)`
- caller_count: `18`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18003e824`
- `0x18003e9f4`
- `0x18003ec48`
- `0x1800613d0`
- `0x18007d5dc`
- `0x18007e3c4`
- `0x18007e4f0`
- `0x18007e65c`
- `0x18007e7fc`
- `0x18007e928`
- `0x18007ea0c`
- `0x18007ead0`
- `0x18007eb98`
- `0x18007ecdc`
- `0x18007ee10`
- `0x18007ef30`
- `0x18007f048`
- `0x18007f11c`

## callees

- `0x1800089bc`
- `0x18003efa0`
- `0x1800729c0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f079`
- `AUTHZ!AuthziLogAuditEvent` at `0x18003f019`
- `AUTHZ!AuthziLogAuditEvent` at `0x18003f019`
- `AUTHZ!AuthzFreeAuditEvent` at `0x18003f04d`
- `AUTHZ!AuthzFreeAuditEvent` at `0x18003f04d`
- `fwbase!FwReportErrorAsWinError` at `0x18003f096`
- `fwbase!FwReportErrorAsWinError` at `0x18003f096`
- `fwbase!FwReportReturnError` at `0x18003f0af`
- `fwbase!FwReportReturnError` at `0x18003f0af`

## string_xrefs

- `0x18003f070`: `FwAuditEventCreate`

## pseudocode

```c

```
