# CCtfServerPort::ForwardMessage(MsgBase *,_ALPC_MESSAGE_ATTRIBUTES *,CCtfServerPort::ClientInfo *)

- ea: `0x1800432a0`
- end: `0x180043442`
- name: `?ForwardMessage@CCtfServerPort@@AEAAXPEAUMsgBase@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAUClientInfo@1@@Z`
- size: `418`
- prototype: `void __fastcall(CCtfServerPort *__hidden this, struct MsgBase *, struct _ALPC_MESSAGE_ATTRIBUTES *, struct CCtfServerPort::ClientInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180040760`
- `0x1800415f0`
- `0x180043b68`

## callees

- `0x1800429e8`
- `0x1800432a0`
- `0x180043548`
- `0x18010a010`

## import_xrefs

- `ntdll!AlpcGetMessageAttribute` at `0x1800433a1`
- `ntdll!AlpcGetMessageAttribute` at `0x1800433e1`
- `ntdll!AlpcGetMessageAttribute` at `0x1800433a1`
- `ntdll!AlpcGetMessageAttribute` at `0x1800433e1`
- `ntdll!NtAlpcDeletePortSection` at `0x18004335e`
- `ntdll!NtAlpcDeletePortSection` at `0x18004335e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180043320`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180043320`
- `USER32!PostMessageW` at `0x18004340f`
- `USER32!PostMessageW` at `0x18004340f`
- `USER32!IsWindow` at `0x1800433f6`
- `USER32!IsWindow` at `0x1800433f6`

## pseudocode

```c

```
