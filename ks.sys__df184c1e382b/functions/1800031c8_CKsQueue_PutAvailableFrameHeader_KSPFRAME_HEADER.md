# CKsQueue::PutAvailableFrameHeader(_KSPFRAME_HEADER *)

- ea: `0x1800031c8`
- end: `0x180003478`
- name: `?PutAvailableFrameHeader@CKsQueue@@AEAAXPEAU_KSPFRAME_HEADER@@@Z`
- size: `688`
- prototype: `void __fastcall(CKsQueue *this, PLIST_ENTRY ListEntry, __int64, int)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x180001820`
- `0x180001a30`
- `0x180001f00`
- `0x1800021b0`
- `0x180002640`
- `0x18000e800`

## callees

- `0x1800031c8`
- `0x18000b7bc`
- `0x18000b9b4`
- `0x18000c630`
- `0x1800159b0`
- `0x1800168f4`
- `0x180019d00`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x180003460`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x180003460`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000325d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000325d`

## pseudocode

```c

```
