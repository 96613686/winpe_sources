# ndisBindReadProtocolDriverFromV3Registry(NDIS_BIND_PROTOCOL_DRIVER *)

- ea: `0x14013d6c0`
- end: `0x14013d8f8`
- name: `?ndisBindReadProtocolDriverFromV3Registry@@YA_NPEAUNDIS_BIND_PROTOCOL_DRIVER@@@Z`
- size: `568`
- prototype: `bool __fastcall(struct NDIS_BIND_PROTOCOL_DRIVER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140170f10`

## callees

- `0x1400eb380`
- `0x14013d6c0`
- `0x140168a70`
- `0x1401690b0`
- `0x1401690f0`
- `0x140169770`
- `0x140170ae0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14013d81f`
- `ntoskrnl!ZwClose` at `0x14013d86f`
- `ntoskrnl!ZwClose` at `0x14013d885`
- `ntoskrnl!ZwClose` at `0x14013d8b3`
- `ntoskrnl!ZwClose` at `0x14013d8c9`
- `ntoskrnl!ZwClose` at `0x14013d81f`
- `ntoskrnl!ZwClose` at `0x14013d86f`
- `ntoskrnl!ZwClose` at `0x14013d885`
- `ntoskrnl!ZwClose` at `0x14013d8b3`
- `ntoskrnl!ZwClose` at `0x14013d8c9`

## string_xrefs

- `0x14013d6f2`: `\Registry\Machine\System\CurrentControlSet\Control\NetworkSetup2\Protocols\Lookup`

## pseudocode

```c

```
