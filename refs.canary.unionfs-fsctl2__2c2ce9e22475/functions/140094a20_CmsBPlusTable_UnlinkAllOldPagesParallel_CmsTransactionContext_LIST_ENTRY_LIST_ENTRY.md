# CmsBPlusTable::UnlinkAllOldPagesParallel(CmsTransactionContext *,_LIST_ENTRY *,_LIST_ENTRY *)

- ea: `0x140094a20`
- end: `0x140094e4f`
- name: `?UnlinkAllOldPagesParallel@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAU_LIST_ENTRY@@1@Z`
- size: `1071`
- prototype: `void __fastcall(struct CmsTransactionContext *, struct _LIST_ENTRY *, struct _LIST_ENTRY *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x14001d350`
- `0x140036df0`
- `0x140094a20`
- `0x1400970d0`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140094acb`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140094b1d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140094acb`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140094b1d`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140094d0b`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140094d0b`
- `ntoskrnl!ExAllocatePool2` at `0x140094ddf`
- `ntoskrnl!ExAllocatePool2` at `0x140094ddf`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140094aa7`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140094af9`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140094c48`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140094aa7`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140094af9`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140094c48`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140094d23`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140094d23`

## pseudocode

```c

```
