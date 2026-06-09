# CmsBPlusTable::MakeBoundSetLogDurable(CmsTransactionContext *,SmsWritePlan *)

- ea: `0x14005f2e0`
- end: `0x14005f68d`
- name: `?MakeBoundSetLogDurable@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAUSmsWritePlan@@@Z`
- size: `941`
- prototype: `void __fastcall(struct CmsTransactionContext *, struct SmsWritePlan *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14013ff9c`

## callees

- `0x14005e710`
- `0x14005f030`
- `0x14005f2e0`
- `0x14005ff20`
- `0x1400602cc`
- `0x1400b0e48`
- `0x1400b5838`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005f4b5`
- `ntoskrnl!KeSetEvent` at `0x14005f4b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005f477`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005f542`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005f58d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005f477`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005f542`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005f58d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005f4c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005f565`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005f5b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005f4c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005f565`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005f5b7`
- `ntoskrnl!KeClearEvent` at `0x14005f460`
- `ntoskrnl!KeClearEvent` at `0x14005f460`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005f4ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005f4ef`
- `ntoskrnl!KeInitializeEvent` at `0x14005f443`
- `ntoskrnl!KeInitializeEvent` at `0x14005f443`

## pseudocode

```c

```
