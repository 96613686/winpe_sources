# DdmModernDevice::DisconnectDialedOutConnection(void *)

- ea: `0x180040d80`
- end: `0x18004134b`
- name: `?DisconnectDialedOutConnection@DdmModernDevice@@UEAAKPEAX@Z`
- size: `1483`
- prototype: `__int64 __fastcall(DdmModernDevice *this, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x180008efc`
- `0x18002f2ec`
- `0x1800304dc`
- `0x180030684`
- `0x1800306c4`
- `0x180037d88`
- `0x180040d80`
- `0x1800459d0`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180092b90`
- `0x180095010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800412eb`
- `KERNEL32!SetEvent` at `0x1800412eb`
- `KERNEL32!LeaveCriticalSection` at `0x180041239`
- `KERNEL32!LeaveCriticalSection` at `0x180041239`
- `KERNEL32!EnterCriticalSection` at `0x180041011`
- `KERNEL32!EnterCriticalSection` at `0x180041011`

## string_xrefs

- `0x180040ec1`: `DisconnectDialedOutConnection: SendMessageToProtocolEngine(PROTOCOL_MSG_Stop) on hPort:%ld returned 0x%x`

## pseudocode

```c

```
