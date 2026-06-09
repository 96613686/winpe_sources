# UpdateCBbyFragment(_PEAP_CONTROL_BLOCK *,_PPP_EAP_PACKET *,_PPP_EAP_PACKET *,ulong)

- ea: `0x180061e5c`
- end: `0x180061f76`
- name: `?UpdateCBbyFragment@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAU_PPP_EAP_PACKET@@1K@Z`
- size: `282`
- prototype: `unsigned int __fastcall(struct _PEAP_CONTROL_BLOCK *, struct _PPP_EAP_PACKET *, struct _PPP_EAP_PACKET *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180009418`
- `0x180030090`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180038e4c`
- `0x180061e5c`

## import_xrefs

- `eapputil!EapConvertHostToWireFormat16` at `0x180061eea`
- `eapputil!EapConvertHostToWireFormat16` at `0x180061eea`
- `eapputil!EapConvertHostToWireFormat32` at `0x180061efd`
- `eapputil!EapConvertHostToWireFormat32` at `0x180061efd`
- `eapputil!EapConvertWireToHostFormat16` at `0x180061e98`
- `eapputil!EapConvertWireToHostFormat16` at `0x180061e98`

## pseudocode

```c

```
