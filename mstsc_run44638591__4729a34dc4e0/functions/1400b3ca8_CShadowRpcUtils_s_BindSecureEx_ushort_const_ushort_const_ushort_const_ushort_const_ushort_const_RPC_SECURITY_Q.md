# CShadowRpcUtils::s_BindSecureEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_RPC_SECURITY_QOS *,void * *)

- ea: `0x1400b3ca8`
- end: `0x1400b3e5b`
- name: `?s_BindSecureEx@CShadowRpcUtils@@SAJPEBG0000PEAU_RPC_SECURITY_QOS@@PEAPEAX@Z`
- size: `435`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _RPC_SECURITY_QOS *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400b3be8`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400b3aa8`
- `0x1400b3ca8`
- `0x1400b3e64`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400b3db3`
- `KERNEL32!LocalFree` at `0x1400b3db3`
- `RPCRT4!RpcBindingFree` at `0x1400b3e46`
- `RPCRT4!RpcBindingFree` at `0x1400b3e46`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400b3da7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400b3dbe`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400b3da7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400b3dbe`

## pseudocode

```c

```
