# CFastBH::CreateFromBindingString(ushort const *,_RPC_BINDING_HANDLE_SECURITY_V1_W *,_GUID *,ulong)

- ea: `0x1801265b0`
- end: `0x180126804`
- name: `?CreateFromBindingString@CFastBH@@AEAAJPEBGPEAU_RPC_BINDING_HANDLE_SECURITY_V1_W@@PEAU_GUID@@K@Z`
- size: `596`
- prototype: `HRESULT __fastcall(CFastBH *this, const wchar_t *pAttrib, _RPC_BINDING_HANDLE_SECURITY_V1_W *pwszBindingString, _GUID *pAttrib, unsigned int pIPID)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801ab048`

## callees

- `0x180087534`
- `0x18008db2c`
- `0x1801265b0`
- `0x180131e1c`
- `0x1801999b0`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x18012661f`
- `RPCRT4!RpcStringBindingParseW` at `0x18012661f`
- `RPCRT4!RpcStringFreeW` at `0x1801267c7`
- `RPCRT4!RpcStringFreeW` at `0x1801267c7`
- `RPCRT4!RpcBindingCreateW` at `0x1801266e0`
- `RPCRT4!RpcBindingCreateW` at `0x1801266e0`
- `RPCRT4!RpcBindingFree` at `0x1801267b0`
- `RPCRT4!RpcBindingFree` at `0x1801267d8`
- `RPCRT4!RpcBindingFree` at `0x1801267b0`
- `RPCRT4!RpcBindingFree` at `0x1801267d8`
- `RPCRT4!RpcBindingUnbind` at `0x180126770`
- `RPCRT4!RpcBindingUnbind` at `0x180126770`

## string_xrefs

- `0x1801265da`: `ncalrpc:[epmapper,Security=Impersonation Dynamic False]`
- `0x18012665e`: `CFastBH::CreateFromBindingString`
- `0x18012666d`: `onecore\com\combase\common\core\fastbh.cxx`

## pseudocode

```c

```
