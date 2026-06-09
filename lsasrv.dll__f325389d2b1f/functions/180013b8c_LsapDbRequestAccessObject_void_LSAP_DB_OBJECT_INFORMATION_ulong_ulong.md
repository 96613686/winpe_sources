# LsapDbRequestAccessObject(void *,_LSAP_DB_OBJECT_INFORMATION *,ulong,ulong)

- ea: `0x180013b8c`
- end: `0x180014150`
- name: `?LsapDbRequestAccessObject@@YAJPEAXPEAU_LSAP_DB_OBJECT_INFORMATION@@KK@Z`
- size: `1476`
- prototype: `__int64 __fastcall(unsigned __int8 *, struct _LSAP_DB_OBJECT_INFORMATION *, DWORD, __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001efd0`

## callees

- `0x180009470`
- `0x180011278`
- `0x180013b8c`
- `0x180014160`
- `0x1800293c0`
- `0x180055ba0`
- `0x180078d2c`
- `0x1800ec7c4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014027`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014027`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013fbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013fbe`
- `ntdll!RtlMapGenericMask` at `0x180013c01`
- `ntdll!RtlMapGenericMask` at `0x180013c01`
- `ntdll!NtAccessCheckByTypeAndAuditAlarm` at `0x180013dca`
- `ntdll!NtAccessCheckByTypeAndAuditAlarm` at `0x180013dca`
- `RPCRT4!RpcRevertToSelf` at `0x180013e71`
- `RPCRT4!RpcRevertToSelf` at `0x180013e71`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180014096`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180014096`
- `RPCRT4!RpcStringBindingParseW` at `0x1800140bd`
- `RPCRT4!RpcStringBindingParseW` at `0x1800140bd`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013c3d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013e7f`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013c3d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013e7f`
- `RPCRT4!RpcImpersonateClient` at `0x180013c2f`
- `RPCRT4!RpcImpersonateClient` at `0x180013c2f`
- `RPCRT4!RpcBindingServerFromClient` at `0x18001407a`
- `RPCRT4!RpcBindingServerFromClient` at `0x18001407a`
- `RPCRT4!RpcStringFreeW` at `0x1800140f8`
- `RPCRT4!RpcStringFreeW` at `0x180014125`
- `RPCRT4!RpcStringFreeW` at `0x1800140f8`
- `RPCRT4!RpcStringFreeW` at `0x180014125`
- `RPCRT4!RpcBindingFree` at `0x18001413f`
- `RPCRT4!RpcBindingFree` at `0x18001413f`

## pseudocode

```c

```
