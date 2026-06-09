# GetClientNetworkAddress(void *)

- ea: `0x1801dc6d4`
- end: `0x1801dc86a`
- name: `?GetClientNetworkAddress@@YAPEAGPEAX@Z`
- size: `406`
- prototype: `wchar_t *__fastcall(void *hRpc)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801dcf2c`

## callees

- `0x180087534`
- `0x180087660`
- `0x18008db2c`
- `0x1801dc6d4`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x1801dc7c6`
- `RPCRT4!RpcStringBindingParseW` at `0x1801dc7c6`
- `RPCRT4!RpcBindingToStringBindingW` at `0x1801dc76e`
- `RPCRT4!RpcBindingToStringBindingW` at `0x1801dc76e`
- `RPCRT4!RpcStringFreeW` at `0x1801dc840`
- `RPCRT4!RpcStringFreeW` at `0x1801dc857`
- `RPCRT4!RpcStringFreeW` at `0x1801dc840`
- `RPCRT4!RpcStringFreeW` at `0x1801dc857`
- `RPCRT4!RpcBindingServerFromClient` at `0x1801dc706`
- `RPCRT4!RpcBindingServerFromClient` at `0x1801dc706`
- `RPCRT4!RpcBindingFree` at `0x1801dc82f`
- `RPCRT4!RpcBindingFree` at `0x1801dc82f`

## string_xrefs

- `0x1801dc755`: `onecore\com\combase\catalog\services.cxx`
- `0x1801dc7fe`: `onecore\com\combase\catalog\services.cxx`

## pseudocode

```c

```
