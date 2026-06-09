# InterfaceContainer::FindInterfaceAndRef(void *,PacketFilterInterface * *)

- ea: `0x180053eec`
- end: `0x180053f49`
- name: `?FindInterfaceAndRef@InterfaceContainer@@QEAAKPEAXPEAPEAVPacketFilterInterface@@@Z`
- size: `93`
- prototype: `unsigned int __fastcall(InterfaceContainer *__hidden this, void *, struct PacketFilterInterface **)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180054bb0`
- `0x180054c30`
- `0x180054ce4`
- `0x180054d84`
- `0x180054df8`
- `0x180054ee0`

## callees

- `0x180053eec`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180053f36`
- `ntdll!RtlReleaseResource` at `0x180053f36`
- `ntdll!RtlAcquireResourceShared` at `0x180053f05`
- `ntdll!RtlAcquireResourceShared` at `0x180053f05`

## pseudocode

```c

```
