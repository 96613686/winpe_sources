# CAssociationContext::AsyncNotificationWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180037eb0`
- end: `0x180037fd6`
- name: `?AsyncNotificationWaitCallback@CAssociationContext@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `294`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800335bc`
- `0x180037eb0`
- `0x180037fdc`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037f8b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037f8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037fb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037fb5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037ec4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037ec4`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180037f42`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180037f42`
- `RPCRT4!RpcAsyncAbortCall` at `0x180037f62`
- `RPCRT4!RpcAsyncAbortCall` at `0x180037f62`

## string_xrefs

- `0x180037f9a`: `onecore\base\devices\association\service\lib\associationcontext.cpp`

## pseudocode

```c

```
