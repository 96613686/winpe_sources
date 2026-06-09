# LsapDbDereferenceHandleNew(void *,uchar)

- ea: `0x1800a1dc4`
- end: `0x1800a211d`
- name: `?LsapDbDereferenceHandleNew@@YAEPEAXE@Z`
- size: `857`
- prototype: `unsigned __int8 __fastcall(struct _LSAP_DB_HANDLE *, unsigned __int8)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ddc0`
- `0x18000f8f0`
- `0x1800101e0`
- `0x180010ba0`
- `0x180083210`

## callees

- `0x180009470`
- `0x18000c300`
- `0x180011278`
- `0x1800284d4`
- `0x18009575c`
- `0x180097568`
- `0x1800a1dc4`
- `0x1800a2124`

## import_xrefs

- `LSAADT!__imp_LsapAuditFailed` at `0x1800a1f48`
- `LSAADT!__imp_LsapAuditFailed` at `0x1800a1fc5`
- `LSAADT!__imp_LsapAuditFailed` at `0x1800a1f48`
- `LSAADT!__imp_LsapAuditFailed` at `0x1800a1fc5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a20bd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a20bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1ffa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1fea`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1fea`
- `ntdll!RtlReleaseResource` at `0x1800a20aa`
- `ntdll!RtlReleaseResource` at `0x1800a20aa`
- `ntdll!RtlFreeUnicodeString` at `0x1800a2064`
- `ntdll!RtlFreeUnicodeString` at `0x1800a2064`
- `ntdll!NtClose` at `0x1800a1ea2`
- `ntdll!NtClose` at `0x1800a1ea2`
- `ntdll!NtCloseObjectAuditAlarm` at `0x1800a1f90`
- `ntdll!NtCloseObjectAuditAlarm` at `0x1800a1f90`
- `RPCRT4!RpcRevertToSelf` at `0x1800a201a`
- `RPCRT4!RpcRevertToSelf` at `0x1800a201a`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a1ef1`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a2028`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a1ef1`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a2028`
- `RPCRT4!RpcImpersonateClient` at `0x1800a1ee3`
- `RPCRT4!RpcImpersonateClient` at `0x1800a1ee3`

## pseudocode

```c

```
