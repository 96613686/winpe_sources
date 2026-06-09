# RefsFsdShutdown(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1402d3280`
- end: `0x1402d34a5`
- name: `?RefsFsdShutdown@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `549`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x140039b20`
- `0x140041b40`
- `0x14007dd30`
- `0x1400e1534`
- `0x1400fe0f8`
- `0x14010bcc4`
- `0x1401e9ce0`
- `0x1402cc864`
- `0x1402d3280`
- `0x1402e245c`
- `0x1402f6e9c`
- `0x140330af8`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1402d3328`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1402d3328`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402d32c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402d32c1`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1402d32da`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1402d32da`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402d346f`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402d346f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402d347b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402d347b`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402d334b`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402d33d2`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402d334b`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402d33d2`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d3364`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d344a`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d3364`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d344a`

## pseudocode

```c

```
