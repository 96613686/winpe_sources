# LRPC_PIPE_SENDER::PipeAckReceived(_LRPC_PIPE_ACK *,LRPC_PIPE_CHUNK_SEND_CONTEXT *,LRPC_SEND_PIPE_BUFFER_DESCRIPTOR * *,LRPC_SENT_PIPE_BUFFER_INFO * *,unsigned __int64 *,int *)

- ea: `0x18009db44`
- end: `0x18009dd9b`
- name: `?PipeAckReceived@LRPC_PIPE_SENDER@@QEAAJPEAU_LRPC_PIPE_ACK@@PEAVLRPC_PIPE_CHUNK_SEND_CONTEXT@@PEAPEAVLRPC_SEND_PIPE_BUFFER_DESCRIPTOR@@PEAPEAVLRPC_SENT_PIPE_BUFFER_INFO@@PEA_KPEAH@Z`
- size: `599`
- prototype: `__int64 __fastcall(LRPC_PIPE_SENDER *__hidden this, struct _LRPC_PIPE_ACK *, struct LRPC_PIPE_CHUNK_SEND_CONTEXT *, struct LRPC_SEND_PIPE_BUFFER_DESCRIPTOR **, struct LRPC_SENT_PIPE_BUFFER_INFO **, unsigned __int64 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18009d938`
- `0x1800a8034`

## callees

- `0x18002b7c0`
- `0x180030af8`
- `0x18009db44`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18009dbc7`
- `ntdll!RtlLeaveCriticalSection` at `0x18009dc84`
- `ntdll!RtlLeaveCriticalSection` at `0x18009dd7e`
- `ntdll!RtlLeaveCriticalSection` at `0x18009dbc7`
- `ntdll!RtlLeaveCriticalSection` at `0x18009dc84`
- `ntdll!RtlLeaveCriticalSection` at `0x18009dd7e`
- `ntdll!RtlEnterCriticalSection` at `0x18009dbb8`
- `ntdll!RtlEnterCriticalSection` at `0x18009dbb8`

## pseudocode

```c

```
