# AicpAsyncFinishCall(_RPC_ASYNC_STATE *,int,ulong,ulong)

- ea: `0x18003b708`
- end: `0x18003b791`
- name: `?AicpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@HKK@Z`
- size: `137`
- prototype: `unsigned int __fastcall(PRPC_ASYNC_STATE pAsync, int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003af40`
- `0x18003b114`
- `0x18003b300`

## callees

- `0x18003b708`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b76a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b789`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b76a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b789`
- `RPCRT4!RpcAsyncCancelCall` at `0x18003b77c`
- `RPCRT4!RpcAsyncCancelCall` at `0x18003b77c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003b73e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003b73e`

## pseudocode

```c

```
