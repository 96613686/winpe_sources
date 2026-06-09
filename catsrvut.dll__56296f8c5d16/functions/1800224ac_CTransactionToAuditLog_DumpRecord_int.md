# CTransactionToAuditLog::DumpRecord(int)

- ea: `0x1800224ac`
- end: `0x180022739`
- name: `?DumpRecord@CTransactionToAuditLog@@AEAAJH@Z`
- size: `653`
- prototype: `__int64 __fastcall(CTransactionToAuditLog *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021c60`
- `0x180021eb0`

## callees

- `0x1800224ac`
- `0x180022740`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002269e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002269e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022706`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022706`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180022694`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180022694`
- `AUTHZ!AuthziInitializeAuditParams` at `0x18002262f`
- `AUTHZ!AuthziInitializeAuditParams` at `0x18002262f`
- `AUTHZ!AuthzFreeAuditEvent` at `0x1800226e8`
- `AUTHZ!AuthzFreeAuditEvent` at `0x1800226e8`
- `AUTHZ!AuthziLogAuditEvent` at `0x1800226bd`
- `AUTHZ!AuthziLogAuditEvent` at `0x1800226bd`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x180022577`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x180022577`
- `AUTHZ!AuthziFreeAuditEventType` at `0x1800226f7`
- `AUTHZ!AuthziFreeAuditEventType` at `0x1800226f7`

## string_xrefs

- `0x1800225a5`: `Security`

## pseudocode

```c

```
