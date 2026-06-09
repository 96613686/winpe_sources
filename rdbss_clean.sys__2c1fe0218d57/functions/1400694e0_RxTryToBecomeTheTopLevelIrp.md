# RxTryToBecomeTheTopLevelIrp

- ea: `0x1400694e0`
- end: `0x14006954c`
- name: `RxTryToBecomeTheTopLevelIrp`
- size: `108`
- prototype: `BOOLEAN __stdcall(PRX_TOPLEVELIRP_CONTEXT TopLevelContext, PIRP Irp, PRDBSS_DEVICE_OBJECT RxDeviceObject, BOOLEAN ForceTopLevel)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008910`
- `0x140015290`
- `0x140048f10`

## callees

- `0x1400694e0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400694f6`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400694f6`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140069523`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140069523`

## pseudocode

```c

```
