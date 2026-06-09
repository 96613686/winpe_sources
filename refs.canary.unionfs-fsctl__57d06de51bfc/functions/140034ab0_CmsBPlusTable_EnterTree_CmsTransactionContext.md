# CmsBPlusTable::EnterTree(CmsTransactionContext *)

- ea: `0x140034ab0`
- end: `0x1400352e1`
- name: `?EnterTree@CmsBPlusTable@@UEAAEPEAVCmsTransactionContext@@@Z`
- size: `2097`
- prototype: `unsigned __int8 __fastcall(CmsBPlusTable *__hidden this, struct CmsTransactionContext *)`
- caller_count: `77`
- callee_count: `13`
- tags: ``

## callers

- `0x1400121f0`
- `0x140012e10`
- `0x140013540`
- `0x140013bec`
- `0x14001b0b0`
- `0x14001d3d0`
- `0x14001e410`
- `0x14001f1a0`
- `0x140021f80`
- `0x140023480`
- `0x140024710`
- `0x140024e04`
- `0x140026350`
- `0x140027540`
- `0x140029ff0`
- `0x14002a0f0`
- `0x14002b320`
- `0x14002bd00`
- `0x14002d9b0`
- `0x140032b20`
- `0x140033480`
- `0x140033550`
- `0x14003586c`
- `0x140035d20`
- `0x1400367f0`
- `0x140048ab4`
- `0x140049620`
- `0x140049ee0`
- `0x14004b0a8`
- `0x14004b5c0`
- `0x14004c710`
- `0x14004c9d0`
- `0x14004ccd0`
- `0x14004d560`
- `0x140059a20`
- `0x1400635c8`
- `0x1400638a0`
- `0x140064480`
- `0x14007180c`
- `0x14007d060`
- `0x14007e2d0`
- `0x14007e5e0`
- `0x14007ea20`
- `0x14008cec4`
- `0x14008edd0`
- `0x14008eec0`
- `0x140099070`
- `0x140099bb0`
- `0x140099ec4`
- `0x14009c750`

## callees

- `0x140034ab0`
- `0x14003d410`
- `0x14007e850`
- `0x14007e900`
- `0x140087ea0`
- `0x1400885b0`
- `0x140088b0c`
- `0x14008a460`
- `0x1400bf9f0`
- `0x1400c39b4`
- `0x1400c3a64`
- `0x1400c8574`
- `0x14012e26c`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140034d93`
- `ntoskrnl!KdDebuggerEnabled` at `0x140034e24`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140034ecd`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140034ecd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140035284`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140035284`
- `ntoskrnl!ExAcquireFastResourceSharedStarveExclusive` at `0x140034ee5`
- `ntoskrnl!ExAcquireFastResourceSharedStarveExclusive` at `0x140035008`
- `ntoskrnl!ExAcquireFastResourceSharedStarveExclusive` at `0x1400350d6`
- `ntoskrnl!ExAcquireFastResourceSharedStarveExclusive` at `0x140034ee5`
- `ntoskrnl!ExAcquireFastResourceSharedStarveExclusive` at `0x140035008`
- `ntoskrnl!ExAcquireFastResourceSharedStarveExclusive` at `0x1400350d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140034cc7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140034cc7`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140034c5e`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140034e87`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140035063`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140034c5e`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140034e87`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140035063`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140035269`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140035269`

## string_xrefs

- `0x1400352d4`: `Attempting to acquire a tree w/synchronized path w/o having an available slot for the tree in the transaction.`

## pseudocode

```c

```
