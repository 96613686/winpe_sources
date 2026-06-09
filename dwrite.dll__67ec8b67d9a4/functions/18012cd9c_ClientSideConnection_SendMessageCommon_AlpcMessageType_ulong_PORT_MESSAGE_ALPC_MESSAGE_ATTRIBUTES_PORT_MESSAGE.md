# ClientSideConnection::SendMessageCommon(AlpcMessageType,ulong,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,unsigned __int64)

- ea: `0x18012cd9c`
- end: `0x18012cf2c`
- name: `?SendMessageCommon@ClientSideConnection@@AEAAJW4AlpcMessageType@@KPEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@1_K@Z`
- size: `400`
- prototype: ``
- caller_count: `13`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18012af0c`
- `0x18012cac0`
- `0x18012d230`
- `0x18012d734`
- `0x18012d788`
- `0x1801e8410`
- `0x1801f4bc8`
- `0x18022c950`
- `0x18028ee1c`
- `0x18028eeb4`
- `0x18028f140`
- `0x18028f248`
- `0x18028f2d8`

## callees

- `0x18012cd9c`
- `0x18012cf34`
- `0x18012cf64`
- `0x18012d1a8`
- `0x180167278`
- `0x18028ed58`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18012ce27`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18012cea1`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18012ce27`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18012cea1`

## pseudocode

```c

```
