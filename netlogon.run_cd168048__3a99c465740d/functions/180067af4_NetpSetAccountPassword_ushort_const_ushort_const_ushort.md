# NetpSetAccountPassword(ushort const *,ushort const *,ushort * *)

- ea: `0x180067af4`
- end: `0x180067d28`
- name: `?NetpSetAccountPassword@@YAJPEBG0PEAPEAG@Z`
- size: `564`
- prototype: `__int64 __fastcall(LPCWSTR servername, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180065520`

## callees

- `0x18000d7a0`
- `0x18000e910`
- `0x18000f3e4`
- `0x1800644a0`
- `0x180065bec`
- `0x180067af4`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180067bb9`
- `RPCRT4!RpcImpersonateClient` at `0x180067bb9`
- `RPCRT4!RpcRevertToSelf` at `0x180067c0a`
- `RPCRT4!RpcRevertToSelf` at `0x180067c0a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180067bc7`
- `RPCRT4!I_RpcMapWin32Status` at `0x180067bc7`
- `netutils!NetApiBufferFree` at `0x180067cfa`
- `netutils!NetApiBufferFree` at `0x180067cfa`
- `netutils!NetApiBufferAllocate` at `0x180067c23`
- `netutils!NetApiBufferAllocate` at `0x180067c23`
- `samcli!NetUserSetInfo` at `0x180067bf5`
- `samcli!NetUserSetInfo` at `0x180067bf5`

## pseudocode

```c

```
