# CCtfServerPort::ForwardRequest(MsgBase *,_ALPC_MESSAGE_ATTRIBUTES *,CCtfServerPort::ClientInfo *,void *)

- ea: `0x180042cdc`
- end: `0x180042f8e`
- name: `?ForwardRequest@CCtfServerPort@@AEAAJPEAUMsgBase@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAUClientInfo@1@PEAX@Z`
- size: `690`
- prototype: `__int64 __fastcall(CCtfServerPort *this, struct MsgBase *, struct _ALPC_MESSAGE_ATTRIBUTES *, struct CCtfServerPort::ClientInfo *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180040760`

## callees

- `0x1800429e8`
- `0x180042cdc`
- `0x180043548`
- `0x18010a010`

## import_xrefs

- `ntdll!AlpcGetMessageAttribute` at `0x180042d9e`
- `ntdll!AlpcGetMessageAttribute` at `0x180042d9e`
- `ntdll!NtAlpcDeletePortSection` at `0x180042f83`
- `ntdll!NtAlpcDeletePortSection` at `0x180042f83`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180042e48`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180042e48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042dae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042dae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e60`
- `USER32!PostMessageW` at `0x180042f19`
- `USER32!PostMessageW` at `0x180042f19`
- `USER32!IsWindow` at `0x180042f00`
- `USER32!IsWindow` at `0x180042f00`

## pseudocode

```c

```
