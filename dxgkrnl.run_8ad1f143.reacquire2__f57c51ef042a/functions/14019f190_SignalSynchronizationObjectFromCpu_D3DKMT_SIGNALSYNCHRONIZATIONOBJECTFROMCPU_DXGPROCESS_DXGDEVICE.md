# SignalSynchronizationObjectFromCpu(_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU *,DXGPROCESS *,DXGDEVICE *)

- ea: `0x14019f190`
- end: `0x14019fcbe`
- name: `?SignalSynchronizationObjectFromCpu@@YAJPEAU_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU@@PEAVDXGPROCESS@@PEAVDXGDEVICE@@@Z`
- size: `2862`
- prototype: `int(struct _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU *, struct DXGPROCESS *, struct DXGDEVICE *)`
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x14019e980`
- `0x1403deb00`

## callees

- `0x140012380`
- `0x140012b14`
- `0x140013860`
- `0x14001b890`
- `0x14001d070`
- `0x14001d0e4`
- `0x14001dad4`
- `0x14001f870`
- `0x140020200`
- `0x140021fe0`
- `0x140033ce0`
- `0x1400478d4`
- `0x1400a0540`
- `0x14019f190`
- `0x14019fcc4`
- `0x14032d860`
- `0x14032f5f0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019f562`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019f562`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f38b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f3b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f690`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f6b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f7aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f7d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f92a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f9f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fa19`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fb04`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fb2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fc3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fc62`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f38b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f3b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f690`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f6b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f7aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f7d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f92a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019f9f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fa19`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fb04`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fb2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fc3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019fc62`
- `ntoskrnl!ExAllocatePool2` at `0x14019f411`
- `ntoskrnl!ExAllocatePool2` at `0x14019f411`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14019f556`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14019f556`
- `watchdog!WdLogSingleEntry4` at `0x14019f83a`
- `watchdog!WdLogSingleEntry4` at `0x14019f83a`
- `watchdog!WdLogSingleEntry0` at `0x14019f22b`
- `watchdog!WdLogSingleEntry0` at `0x14019f276`
- `watchdog!WdLogSingleEntry0` at `0x14019f2c2`
- `watchdog!WdLogSingleEntry0` at `0x14019f30e`
- `watchdog!WdLogSingleEntry0` at `0x14019f4ec`
- `watchdog!WdLogSingleEntry0` at `0x14019f5b9`
- `watchdog!WdLogSingleEntry0` at `0x14019f8a9`
- `watchdog!WdLogSingleEntry0` at `0x14019f22b`
- `watchdog!WdLogSingleEntry0` at `0x14019f276`
- `watchdog!WdLogSingleEntry0` at `0x14019f2c2`
- `watchdog!WdLogSingleEntry0` at `0x14019f30e`
- `watchdog!WdLogSingleEntry0` at `0x14019f4ec`
- `watchdog!WdLogSingleEntry0` at `0x14019f5b9`
- `watchdog!WdLogSingleEntry0` at `0x14019f8a9`
- `watchdog!WdLogSingleEntry5` at `0x14019f6f8`
- `watchdog!WdLogSingleEntry5` at `0x14019f6f8`
- `watchdog!WdLogSingleEntry1` at `0x14019f636`
- `watchdog!WdLogSingleEntry1` at `0x14019f748`
- `watchdog!WdLogSingleEntry1` at `0x14019fa9a`
- `watchdog!WdLogSingleEntry1` at `0x14019fbd7`
- `watchdog!WdLogSingleEntry1` at `0x14019f636`
- `watchdog!WdLogSingleEntry1` at `0x14019f748`
- `watchdog!WdLogSingleEntry1` at `0x14019fa9a`
- `watchdog!WdLogSingleEntry1` at `0x14019fbd7`

## string_xrefs

- `0x14019f759`: `0x%I64x object is opened as wait only and thus cannot be signaled.`

## pseudocode

```c

```
