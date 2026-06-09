# ndisBindReadProtocolDriverFromV3Registry(NDIS_BIND_PROTOCOL_DRIVER *)

- ea: `0x1401366c0`
- end: `0x1401368f8`
- name: `?ndisBindReadProtocolDriverFromV3Registry@@YA_NPEAUNDIS_BIND_PROTOCOL_DRIVER@@@Z`
- size: `568`
- prototype: `bool __fastcall(struct NDIS_BIND_PROTOCOL_DRIVER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14016a020`

## callees

- `0x1400e6160`
- `0x1401366c0`
- `0x140161ae0`
- `0x140162120`
- `0x140162160`
- `0x1401627e0`
- `0x140169bf0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14013681f`
- `ntoskrnl!ZwClose` at `0x14013686f`
- `ntoskrnl!ZwClose` at `0x140136885`
- `ntoskrnl!ZwClose` at `0x1401368b3`
- `ntoskrnl!ZwClose` at `0x1401368c9`
- `ntoskrnl!ZwClose` at `0x14013681f`
- `ntoskrnl!ZwClose` at `0x14013686f`
- `ntoskrnl!ZwClose` at `0x140136885`
- `ntoskrnl!ZwClose` at `0x1401368b3`
- `ntoskrnl!ZwClose` at `0x1401368c9`

## string_xrefs

- `0x1401366f2`: `\Registry\Machine\System\CurrentControlSet\Control\NetworkSetup2\Protocols\Lookup`

## pseudocode

```c

```
