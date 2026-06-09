# Dot11PacketConverterSendPacket(_VELAN *,_NET_BUFFER_LIST *,uchar *,ushort)

- ea: `0x14000e26c`
- end: `0x14000e64d`
- name: `?Dot11PacketConverterSendPacket@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAEG@Z`
- size: `993`
- prototype: `int(struct _VELAN *, struct _NET_BUFFER_LIST *, unsigned __int8 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d78c`

## callees

- `0x14000e26c`
- `0x140010520`
- `0x140055b20`
- `0x14009a3d0`
- `0x14009a410`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e447`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e447`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14000e3e5`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14000e3e5`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14000e40f`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14000e5bc`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14000e40f`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14000e5bc`

## pseudocode

```c

```
