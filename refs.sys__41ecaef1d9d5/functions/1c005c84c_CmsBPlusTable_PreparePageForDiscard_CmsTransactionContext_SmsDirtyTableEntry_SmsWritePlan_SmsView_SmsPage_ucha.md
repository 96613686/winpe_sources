# CmsBPlusTable::PreparePageForDiscard(CmsTransactionContext *,_SmsDirtyTableEntry *,SmsWritePlan *,_SmsView *,SmsPage *,uchar,uchar,uchar)

- ea: `0x1c005c84c`
- end: `0x1c005c9d6`
- name: `?PreparePageForDiscard@CmsBPlusTable@@AEAAXPEAVCmsTransactionContext@@PEAU_SmsDirtyTableEntry@@PEAUSmsWritePlan@@PEAU_SmsView@@PEAUSmsPage@@EEE@Z`
- size: `394`
- prototype: `void __usercall(CmsBPlusTable *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct _SmsDirtyTableEntry *@<r8>, struct SmsWritePlan *@<r9>, struct _SmsView *, struct SmsPage *, char, unsigned __int8, unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1c0021950`
- `0x1c00ee870`

## callees

- `0x1c001db20`
- `0x1c002a914`
- `0x1c0031080`
- `0x1c0036cac`
- `0x1c005c84c`
- `0x1c005c9dc`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c008cb6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c008cb7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c008cb6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c008cb7d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c008cb27`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c008cb38`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c008cb27`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c008cb38`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c005c90b`

## pseudocode

```c

```
