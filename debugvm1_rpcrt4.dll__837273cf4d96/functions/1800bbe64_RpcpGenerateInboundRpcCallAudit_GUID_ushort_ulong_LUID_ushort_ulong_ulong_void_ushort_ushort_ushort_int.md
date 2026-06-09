# RpcpGenerateInboundRpcCallAudit(_GUID *,ushort *,ulong,_LUID *,ushort *,ulong,ulong,void *,ushort,ushort *,ushort *,int)

- ea: `0x1800bbe64`
- end: `0x1800bc0c7`
- name: `?RpcpGenerateInboundRpcCallAudit@@YAXPEAU_GUID@@PEAGKPEAU_LUID@@1KKPEAXG11H@Z`
- size: `611`
- prototype: `void __fastcall(struct _GUID *, unsigned __int16 *, unsigned int, struct _LUID *, unsigned __int16 *, unsigned int, unsigned int, void *, unsigned __int16, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800af218`

## callees

- `0x1800bbbdc`
- `0x1800bbd38`
- `0x1800bbe64`
- `0x1800ca049`
- `0x1800ca140`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc096`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc096`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x1800bbf1a`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x1800bbf1a`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x1800bc00b`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x1800bc00b`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x1800bc069`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x1800bc069`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x1800bc078`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x1800bc078`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x1800bc087`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x1800bc087`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x1800bc056`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x1800bc056`

## string_xrefs

- `0x1800bbf37`: `Security`

## pseudocode

```c

```
