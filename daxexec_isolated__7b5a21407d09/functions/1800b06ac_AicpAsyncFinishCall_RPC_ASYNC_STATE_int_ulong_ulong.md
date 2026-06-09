# AicpAsyncFinishCall(_RPC_ASYNC_STATE *,int,ulong,ulong)

- ea: `0x1800b06ac`
- end: `0x1800b074c`
- name: `?AicpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@HKK@Z`
- size: `160`
- prototype: `unsigned int __fastcall(PRPC_ASYNC_STATE pAsync, int, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b0548`
- `0x1800b1074`
- `0x1800b11e0`
- `0x1800b137c`
- `0x1800b19e4`

## callees

- `0x1800b06ac`
- `0x1800b0d68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b06e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0711`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b06e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0711`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800b06fe`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800b06fe`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800b0725`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800b0725`

## pseudocode

```c

```
