# DdmModernDevice::DisconnectDialedOutConnection(void *)

- ea: `0x18003f510`
- end: `0x18003fac2`
- name: `?DisconnectDialedOutConnection@DdmModernDevice@@UEAAKPEAX@Z`
- size: `1458`
- prototype: `unsigned int __fastcall(DdmModernDevice *__hidden this, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x180008e08`
- `0x18002d0c4`
- `0x18002e0ec`
- `0x18002e268`
- `0x18002e2a8`
- `0x180036248`
- `0x18003f510`
- `0x180044890`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18003f65a`
- `msvcrt!_itow_s` at `0x18003f71f`
- `msvcrt!_itow_s` at `0x18003f897`
- `msvcrt!_itow_s` at `0x18003f65a`
- `msvcrt!_itow_s` at `0x18003f71f`
- `msvcrt!_itow_s` at `0x18003f897`
- `KERNEL32!SetEvent` at `0x18003fa6e`
- `KERNEL32!SetEvent` at `0x18003fa6e`
- `KERNEL32!LeaveCriticalSection` at `0x18003f9f5`
- `KERNEL32!LeaveCriticalSection` at `0x18003f9f5`
- `KERNEL32!EnterCriticalSection` at `0x18003f7c0`
- `KERNEL32!EnterCriticalSection` at `0x18003f7c0`

## string_xrefs

- `0x18003f667`: `DisconnectDialedOutConnection: SendMessageToProtocolEngine(PROTOCOL_MSG_Stop) on hPort:%ld returned 0x%x`

## pseudocode

```c

```
