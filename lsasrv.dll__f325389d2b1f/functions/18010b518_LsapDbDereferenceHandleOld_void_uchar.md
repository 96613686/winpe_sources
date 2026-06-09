# LsapDbDereferenceHandleOld(void *,uchar)

- ea: `0x18010b518`
- end: `0x18010b7f6`
- name: `?LsapDbDereferenceHandleOld@@YAEPEAXE@Z`
- size: `734`
- prototype: `unsigned __int8 __fastcall(void *, unsigned __int8)`
- caller_count: `5`
- callee_count: `7`
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
- `0x18007e3e8`
- `0x18009575c`
- `0x180097568`
- `0x1800af908`
- `0x18010b518`

## import_xrefs

- `LSAADT!__imp_LsapAuditFailed` at `0x18010b698`
- `LSAADT!__imp_LsapAuditFailed` at `0x18010b6c7`
- `LSAADT!__imp_LsapAuditFailed` at `0x18010b698`
- `LSAADT!__imp_LsapAuditFailed` at `0x18010b6c7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010b77c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010b77c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18010b6ec`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18010b6ec`
- `ntdll!RtlReleaseResource` at `0x18010b769`
- `ntdll!RtlReleaseResource` at `0x18010b769`
- `ntdll!RtlFreeUnicodeString` at `0x18010b723`
- `ntdll!RtlFreeUnicodeString` at `0x18010b723`
- `ntdll!NtClose` at `0x18010b620`
- `ntdll!NtClose` at `0x18010b620`
- `ntdll!RtlLeaveCriticalSection` at `0x18010b7d6`
- `ntdll!RtlLeaveCriticalSection` at `0x18010b7d6`
- `ntdll!RtlEnterCriticalSection` at `0x18010b55f`
- `ntdll!RtlEnterCriticalSection` at `0x18010b55f`
- `ntdll!NtCloseObjectAuditAlarm` at `0x18010b6b5`
- `ntdll!NtCloseObjectAuditAlarm` at `0x18010b6b5`
- `RPCRT4!RpcRevertToSelf` at `0x18010b6fa`
- `RPCRT4!RpcRevertToSelf` at `0x18010b6fa`
- `RPCRT4!I_RpcMapWin32Status` at `0x18010b670`
- `RPCRT4!I_RpcMapWin32Status` at `0x18010b708`
- `RPCRT4!I_RpcMapWin32Status` at `0x18010b670`
- `RPCRT4!I_RpcMapWin32Status` at `0x18010b708`
- `RPCRT4!RpcImpersonateClient` at `0x18010b662`
- `RPCRT4!RpcImpersonateClient` at `0x18010b662`

## pseudocode

```c

```
