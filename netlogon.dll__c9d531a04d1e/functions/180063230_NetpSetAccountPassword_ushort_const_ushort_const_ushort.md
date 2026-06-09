# NetpSetAccountPassword(ushort const *,ushort const *,ushort * *)

- ea: `0x180063230`
- end: `0x18006343f`
- name: `?NetpSetAccountPassword@@YAJPEBG0PEAPEAG@Z`
- size: `527`
- prototype: `__int64 __fastcall(LPCWSTR servername, const unsigned __int16 *, LPVOID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180060fa4`

## callees

- `0x18000d100`
- `0x18000e270`
- `0x18000ed34`
- `0x18005ffb0`
- `0x1800615f0`
- `0x180063230`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800632f5`
- `RPCRT4!RpcImpersonateClient` at `0x1800632f5`
- `RPCRT4!RpcRevertToSelf` at `0x180063334`
- `RPCRT4!RpcRevertToSelf` at `0x180063334`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800632fd`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800632fd`
- `netutils!NetApiBufferFree` at `0x180063418`
- `netutils!NetApiBufferFree` at `0x180063418`
- `netutils!NetApiBufferAllocate` at `0x180063347`
- `netutils!NetApiBufferAllocate` at `0x180063347`
- `samcli!NetUserSetInfo` at `0x180063325`
- `samcli!NetUserSetInfo` at `0x180063325`

## pseudocode

```c

```
