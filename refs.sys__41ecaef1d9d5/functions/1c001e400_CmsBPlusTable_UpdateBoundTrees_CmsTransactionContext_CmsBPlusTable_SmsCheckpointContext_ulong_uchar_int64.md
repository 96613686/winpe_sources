# CmsBPlusTable::UpdateBoundTrees(CmsTransactionContext *,CmsBPlusTable *,_SmsCheckpointContext *,ulong,uchar *,__int64)

- ea: `0x1c001e400`
- end: `0x1c0020d00`
- name: `?UpdateBoundTrees@CmsBPlusTable@@SAJPEAVCmsTransactionContext@@PEAV1@PEAU_SmsCheckpointContext@@KPEAE_J@Z`
- size: `10496`
- prototype: `__int64 __usercall@<rax>(struct CmsTransactionContext *@<rcx>, struct CmsBPlusTable *this@<rdx>, struct _SmsCheckpointContext *@<r8>, unsigned int@<r9d>, unsigned __int8 *, __int64)`
- caller_count: `2`
- callee_count: `67`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c001db90`
- `0x1c0038af8`

## callees

- `0x1c0002b40`
- `0x1c000384c`
- `0x1c0018e20`
- `0x1c001dc60`
- `0x1c001e400`
- `0x1c0020d08`
- `0x1c0020fe0`
- `0x1c00224d0`
- `0x1c002357c`
- `0x1c0027480`
- `0x1c002a708`
- `0x1c002b8ec`
- `0x1c0030504`
- `0x1c00307e0`
- `0x1c003145c`
- `0x1c00314bc`
- `0x1c0031520`
- `0x1c003397c`
- `0x1c00340d4`
- `0x1c00341c0`
- `0x1c00342fc`
- `0x1c0034670`
- `0x1c0034a40`
- `0x1c003514c`
- `0x1c0035254`
- `0x1c00352f0`
- `0x1c0035408`
- `0x1c0035848`
- `0x1c0035a98`
- `0x1c0035af8`
- `0x1c0035c0c`
- `0x1c0035e30`
- `0x1c0036a10`
- `0x1c0036cac`
- `0x1c0036ddc`
- `0x1c0037844`
- `0x1c0039984`
- `0x1c004785c`
- `0x1c004e92c`
- `0x1c004ef58`
- `0x1c005217c`
- `0x1c0057c70`
- `0x1c0057fc8`
- `0x1c005a5d0`
- `0x1c005b4ac`
- `0x1c005c1e4`
- `0x1c0060874`
- `0x1c006140c`
- `0x1c006241c`
- `0x1c0063d0c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c001e9a3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0020256`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0020387`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00204b7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0077e15`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0078577`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c001e9a3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0020256`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0020387`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00204b7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0077e15`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0078577`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00200cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0077a04`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0077ab0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0077b5a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0077f50`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0078121`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00200cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0077a04`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0077ab0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0077b5a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0077f50`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0078121`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c001f4c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0020c89`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0077fc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00780a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0078194`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007826a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0078a08`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0078aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0078b3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c001f4c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0020c89`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0077fc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00780a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0078194`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007826a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0078a08`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0078aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0078b3c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c001e9d4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0020241`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c002032f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0020372`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c002045f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00204a2`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c002058f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00785a7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c001e9d4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0020241`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c002032f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0020372`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c002045f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00204a2`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c002058f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00785a7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e61b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e637`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e716`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e7b1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e82f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001ee7c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e61b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e637`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e716`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e7b1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001e82f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001ee7c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001e64a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001e757`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001e7fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001e8cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001eef8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001f2df`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001f37f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001fdb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001fe71`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00778f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0077b96`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0077c21`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0077dea`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001e64a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001e757`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001e7fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001e8cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001eef8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001f2df`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001f37f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001fdb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c001fe71`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00778f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0077b96`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0077c21`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0077dea`
- `ntoskrnl!KeInitializeEvent` at `0x1c001ef18`
- `ntoskrnl!KeInitializeEvent` at `0x1c001f039`
- `ntoskrnl!KeInitializeEvent` at `0x1c001f0d9`
- `ntoskrnl!KeInitializeEvent` at `0x1c001fd27`
- `ntoskrnl!KeInitializeEvent` at `0x1c001fef5`
- `ntoskrnl!KeInitializeEvent` at `0x1c0077e5a`
- `ntoskrnl!KeInitializeEvent` at `0x1c001ef18`
- `ntoskrnl!KeInitializeEvent` at `0x1c001f039`
- `ntoskrnl!KeInitializeEvent` at `0x1c001f0d9`
- `ntoskrnl!KeInitializeEvent` at `0x1c001fd27`
- `ntoskrnl!KeInitializeEvent` at `0x1c001fef5`
- `ntoskrnl!KeInitializeEvent` at `0x1c0077e5a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c001e669`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c001f1ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c001f20a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c001f2ab`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c001e669`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c001f1ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c001f20a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c001f2ab`
- `ntoskrnl!KeClearEvent` at `0x1c001e84f`
- `ntoskrnl!KeClearEvent` at `0x1c0020123`
- `ntoskrnl!KeClearEvent` at `0x1c001e84f`
- `ntoskrnl!KeClearEvent` at `0x1c0020123`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c001e816`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c001fdcf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c001e816`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c001fdcf`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c001f045`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0077950`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0078602`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c007868e`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c001f045`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0077950`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0078602`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c007868e`
- `ntoskrnl!KeSetEvent` at `0x1c001eeca`
- `ntoskrnl!KeSetEvent` at `0x1c001efcb`
- `ntoskrnl!KeSetEvent` at `0x1c001f192`
- `ntoskrnl!KeSetEvent` at `0x1c001fe9a`
- `ntoskrnl!KeSetEvent` at `0x1c0077bda`
- `ntoskrnl!KeSetEvent` at `0x1c00780ff`
- `ntoskrnl!KeSetEvent` at `0x1c0078592`
- `ntoskrnl!KeSetEvent` at `0x1c001eeca`
- `ntoskrnl!KeSetEvent` at `0x1c001efcb`
- `ntoskrnl!KeSetEvent` at `0x1c001f192`
- `ntoskrnl!KeSetEvent` at `0x1c001fe9a`
- `ntoskrnl!KeSetEvent` at `0x1c0077bda`
- `ntoskrnl!KeSetEvent` at `0x1c00780ff`
- `ntoskrnl!KeSetEvent` at `0x1c0078592`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00206b5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c002075f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0020809`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00779d5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0077a81`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0077b2b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00206b5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c002075f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0020809`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00779d5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0077a81`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0077b2b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001f72d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001f7e4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001f89b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00789ee`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0078a88`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0078b22`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001f72d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001f7e4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001f89b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00789ee`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0078a88`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0078b22`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f710`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f7c7`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f87e`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f710`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f7c7`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f87e`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1c001eee1`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1c001fe55`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1c001eee1`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1c001fe55`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c001ec29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c001f3c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c001ec29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c001f3c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c001ec56`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c001f3f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0020168`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c001ec56`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c001f3f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0020168`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c001facb`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c007842d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c002066c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0020716`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c00207c0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c002066c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0020716`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c00207c0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c002021f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c0020350`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::UpdateBoundTrees(
        struct CmsTransactionContext *a1,
        struct CmsBPlusTable *this,
        struct _SmsCheckpointContext *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        __int64 a6)
{
  __int64 v6; // rax
  CmsBPlusTable *v8; // rsi
  struct CmsTransactionContext *v9; // r15
  struct _ERESOURCE *v10; // rdi
  CmsVolume *v11; // r13
  unsigned int v12; // r14d
  __int64 v13; // rdx
  char v14; // al
  char v15; // al
  int v16; // r14d
  __int64 v17; // rbx
  CmsBPlusTable *v18; // rax
  CmsBPlusTable *m; // rbx
  CmsBPlusTable *n; // rax
  __int64 v21; // rbx
  struct _ERESOURCE *v22; // rcx
  __int64 v23; // rdi
  _QWORD *v24; // rbx
  CmsBPlusTable *v25; // rcx
  CmsBPlusTable *v26; // rcx
  CmsBPlusTable *ii; // rax
  CmsBPlusTable *jj; // rcx
  struct _LIST_ENTRY *v29; // rbx
  struct _ERESOURCE *v30; // rcx
  __int64 v31; // r14
  struct _LIST_ENTRY *v32; // rdi
  struct _LIST_ENTRY *v33; // rdi
  struct CmsTransactionContext *v34; // r14
  struct _LIST_ENTRY *Flink; // rcx
  CmsBPlusTable *v36; // rax
  CmsBPlusTable *v37; // rcx
  CmsBPlusTable *kk; // rcx
  struct _LIST_ENTRY *v39; // r15
  struct _LIST_ENTRY *v40; // r13
  struct _LIST_ENTRY *v41; // rbx
  CmsBPlusTable *v42; // rcx
  CmsBPlusTable *v43; // rbx
  char v44; // di
  struct _LIST_ENTRY *v45; // rcx
  struct _LIST_ENTRY *v46; // r8
  struct _LIST_ENTRY *v47; // rax
  struct _LIST_ENTRY *Blink; // rdx
  struct _SmsDirtyTableEntries *v49; // r12
  int Blink_high; // ecx
  CmsVolume *v51; // rsi
  struct _LIST_ENTRY **p_Blink; // r12
  struct _LIST_ENTRY **v53; // rbx
  CmsBPlusTable *v54; // rcx
  __int64 v55; // rdi
  struct _LIST_ENTRY *v56; // rbx
  CmsBPlusTable *v57; // rcx
  CmsVolume *v58; // rbx
  struct _LIST_ENTRY *v59; // rsi
  CmsReferenced *v60; // rdi
  _QWORD *v61; // rdx
  __int64 v62; // rbx
  _QWORD *v63; // rax
  CmsBPlusTable **v64; // rdi
  CmsBPlusTable **v65; // rdi
  CmsBPlusTable **v66; // rcx
  _QWORD *v67; // rdx
  __int64 v68; // rbx
  _QWORD *v69; // rax
  CmsBPlusTable **v70; // rdi
  CmsBPlusTable **v71; // rdi
  CmsBPlusTable **v72; // rcx
  _QWORD *v73; // rdx
  __int64 v74; // rbx
  _QWORD *v75; // rax
  CmsBPlusTable **v76; // rdi
  CmsBPlusTable **v77; // rdi
  CmsBPlusTable **v78; // rcx
  struct _SmsCheckpointContext *v79; // rbx
  LARGE_INTEGER v80; // rax
  struct _ERESOURCE *v81; // rcx
  struct _LIST_ENTRY *v82; // rbx
  struct _LIST_ENTRY *v83; // rax
  __int64 v84; // rax
  struct _LIST_ENTRY *v85; // rax
  CmsBPlusTable *v86; // rbx
  __int64 v87; // rdx
  __int64 v88; // r8
  struct _LIST_ENTRY *v89; // rax
  __int64 v90; // rax
  struct _LIST_ENTRY *v91; // rax
  int v92; // edi
  unsigned int v93; // ebx
  int v94; // r14d
  int v95; // edi
  struct _LIST_ENTRY *v96; // rbx
  unsigned int v97; // r8d
  unsigned int i3; // ebx
  struct _LIST_ENTRY *v99; // r9
  struct _LIST_ENTRY *v100; // rdx
  struct CmsTransactionContext *v101; // rbx
  CmsVolume *v102; // rsi
  struct _LIST_ENTRY *v103; // rdi
  struct _LIST_ENTRY *v104; // rax
  CmsReferenced **v105; // rbx
  _QWORD *v106; // r12
  signed int v107; // edi
  KSPIN_LOCK *v108; // rbx
  KIRQL v109; // si
  _QWORD *v110; // rdx
  __int64 v111; // rbx
  _QWORD *v112; // rax
  __int64 v113; // rdi
  __int64 v114; // rcx
  volatile signed __int32 *v115; // rsi
  _QWORD *v116; // rdi
  _QWORD *v117; // rcx
  CmsVolume *v118; // rsi
  void *v119; // r8
  struct _SmsCheckpointContext *v120; // rbx
  int v121; // edi
  _QWORD *v122; // rsi
  __int64 v123; // r15
  struct _SmsCheckpointContext *v124; // rbx
  int v125; // edi
  _QWORD *v126; // rsi
  __int64 v127; // r15
  struct _SmsCheckpointContext *v128; // rbx
  int v129; // edi
  _QWORD *v130; // rsi
  __int64 v131; // r15
  PVOID v132; // rbx
  PVOID v133; // rbx
  struct _SmsCheckpointContext *v134; // rcx
  void *v135; // rcx
  __int64 v136; // rdi
  struct _SLIST_ENTRY *v137; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v138; // rcx
  void *v139; // rcx
  __int64 v140; // rdi
  struct _SLIST_ENTRY *v141; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v142; // rcx
  void *v143; // rcx
  __int64 v144; // rdi
  struct _SLIST_ENTRY *v145; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v146; // rcx
  unsigned int v148; // edx
  unsigned int v149; // ecx
  __int64 v150; // rbx
  __int64 v151; // rbx
  signed __int32 v152; // ett
  struct _LIST_ENTRY *v153; // r9
  struct _LIST_ENTRY *v154; // rdx
  struct _LIST_ENTRY *v155; // rdx
  struct _LIST_ENTRY *v156; // rcx
  struct CmsTransactionContext *v157; // rdi
  int v158; // r8d
  struct SmsPage **v159; // rdx
  struct SmsPage **v160; // rcx
  __int64 v161; // rcx
  struct _LIST_ENTRY *v162; // rdx
  struct _LIST_ENTRY *v163; // r8
  struct _LIST_ENTRY *v164; // r9
  struct _LIST_ENTRY *v165; // r10
  struct _LIST_ENTRY *i1; // rax
  struct _LIST_ENTRY *v167; // rbx
  __int64 v168; // rax
  struct _LIST_ENTRY *v169; // r11
  struct _LIST_ENTRY *i2; // rcx
  struct _SmsLsn *v171; // r8
  CmsDurableLog *v172; // rcx
  struct _LIST_ENTRY *v173; // rcx
  struct _LIST_ENTRY *v174; // rax
  struct _LIST_ENTRY *v175; // rdi
  struct _LIST_ENTRY *v176; // rbx
  struct _LIST_ENTRY *v177; // rax
  struct _LIST_ENTRY *v178; // rdx
  struct _LIST_ENTRY *v179; // rcx
  struct _LIST_ENTRY *v180; // rax
  struct _LIST_ENTRY **v181; // rdi
  struct _LIST_ENTRY **v182; // rbx
  struct _LIST_ENTRY **v183; // rax
  CmsVolume *v184; // rdx
  int v185; // ecx
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rax
  MsAllocator::RangeArrayStrategy::State *v189; // rcx
  __int64 v190; // rax
  __int64 v191; // rax
  __int64 v192; // kr00_8
  unsigned int v193; // r15d
  unsigned int v194; // eax
  unsigned int v195; // r12d
  unsigned int v196; // r15d
  struct _MS_WORK_QUEUE_ITEM *v197; // rax
  struct _SmsLazyWriterEntry *v198; // rcx
  unsigned int v199; // ebx
  unsigned int v200; // ebx
  _QWORD *v201; // r9
  unsigned int i; // edx
  __int64 v203; // rax
  unsigned int v204; // ebx
  unsigned int v205; // ebx
  _QWORD *PoolWithTag; // r9
  unsigned int j; // edx
  __int64 v208; // rax
  unsigned int v209; // ebx
  unsigned int v210; // ebx
  _QWORD *v211; // r9
  unsigned int k; // eax
  __int64 v213; // rcx
  unsigned int v214; // ecx
  __int64 *v215; // rax
  unsigned int v216; // edx
  unsigned int v217; // ecx
  __int64 *v218; // rax
  unsigned int v219; // edx
  unsigned int v220; // ecx
  __int64 *v221; // rax
  unsigned int v222; // edx
  unsigned __int64 v223; // rsi
  unsigned int *v224; // rdi
  struct _PAGED_LOOKASIDE_LIST *v225; // rcx
  unsigned __int64 v226; // rsi
  unsigned int *v227; // rdi
  struct _PAGED_LOOKASIDE_LIST *v228; // rcx
  unsigned __int64 v229; // rsi
  unsigned int *v230; // rdi
  struct _PAGED_LOOKASIDE_LIST *v231; // rcx
  _QWORD *v232; // rax
  _QWORD *v233; // rax
  _QWORD *v234; // rax
  struct _LIST_ENTRY **v235; // rdi
  struct _LIST_ENTRY *v236; // rax
  CmsBPlusTable **v237; // rbx
  CmsBPlusTable *v238; // rdx
  char v239; // cl
  CmsAllocator *v240; // rcx
  __int64 v241; // rcx
  __int64 v242; // rax
  struct CmsBPlusTable *v243; // rax
  struct _LIST_ENTRY *v244; // rcx
  struct _LIST_ENTRY *v245; // rax
  struct _LIST_ENTRY *v246; // r8
  struct _LIST_ENTRY *v247; // rdx
  struct _LIST_ENTRY *v248; // r9
  struct _LIST_ENTRY *v249; // r10
  struct _LIST_ENTRY *mm; // rdx
  struct _LIST_ENTRY **p_Flink; // rbx
  struct _LIST_ENTRY *v252; // r8
  struct _LIST_ENTRY *v253; // r11
  struct _LIST_ENTRY *v254; // r10
  struct _LIST_ENTRY *v255; // r9
  bool v256; // zf
  struct _LIST_ENTRY *nn; // rax
  struct _SmsCheckpointContext *v258; // rbx
  __int64 v259; // rdi
  __int64 v260; // rcx
  __int64 v261; // rcx
  int ActivityIdThread; // eax
  int v263; // eax
  SIZE_T v264; // rsi
  int v265; // eax
  SIZE_T v266; // rsi
  int v267; // eax
  SIZE_T v268; // rsi
  struct _LIST_ENTRY *v269; // rsi
  struct CmsBPlusTable *v270; // rax
  struct _SmsBindable *v271; // rdx
  struct CmsTransactionContext *v272; // rcx
  __int64 v273; // rcx
  __int64 v274; // rax
  struct _SmsCheckpointContext *v275; // rcx
  struct _SmsCheckpointContext *v276; // rax
  struct _ERESOURCE *v277; // rcx
  unsigned __int8 v278; // r9
  struct _SmsLsn *v279; // r8
  CmsDurableLog *v280; // rcx
  char *v281; // rax
  enum _WORK_QUEUE_TYPE v282; // r9d
  void *v283; // rbx
  CmsTransactionContext *v284; // rax
  CmsTransactionContext *v285; // rbx
  int v286; // eax
  int v287; // ecx
  char *v288; // rax
  enum _WORK_QUEUE_TYPE v289; // r9d
  void *v290; // rbx
  CmsTransactionContext *v291; // rax
  CmsTransactionContext *v292; // rbx
  int v293; // eax
  int v294; // ecx
  CmsBlockRefcount *v295; // rcx
  struct CmsTransactionContext *v296; // rcx
  struct _LIST_ENTRY *v298; // rcx
  struct _LIST_ENTRY *v299; // rax
  __int64 v300; // rsi
  __int64 v301; // rcx
  __int64 v302; // rdi
  __int64 v303; // rcx
  int v304; // ebx
  int v305; // eax
  CmsBPlusTable *v306; // rbx
  __int64 v307; // rsi
  __int64 v308; // rcx
  __int64 v309; // rdi
  __int64 v310; // rdi
  int v311; // ebx
  int v312; // eax
  int v313; // eax
  _QWORD *v314; // r12
  void *v315; // rcx
  int v316; // eax
  _QWORD *v317; // r12
  void *v318; // rcx
  int v319; // eax
  _QWORD *v320; // r12
  void *v321; // rcx
  void *v322; // rcx
  void *v323; // rcx
  int v324; // eax
  int v325; // eax
  int v326; // eax
  union _ML_LSN *Timeout; // [rsp+20h] [rbp-E0h]
  union _ML_LSN *Timeouta; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v329; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v330[7]; // [rsp+41h] [rbp-BFh] BYREF
  CmsVolume *v331; // [rsp+48h] [rbp-B8h]
  struct _LIST_ENTRY *v332; // [rsp+50h] [rbp-B0h]
  struct CmsTransactionContext *v333; // [rsp+58h] [rbp-A8h]
  CmsBPlusTable *v334; // [rsp+60h] [rbp-A0h]
  int v335; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v336; // [rsp+6Ch] [rbp-94h]
  struct SmsPage *v337; // [rsp+70h] [rbp-90h] BYREF
  PVOID P; // [rsp+78h] [rbp-88h]
  char v339; // [rsp+80h] [rbp-80h]
  PERESOURCE Resource; // [rsp+88h] [rbp-78h]
  int v341; // [rsp+90h] [rbp-70h]
  signed int v342; // [rsp+94h] [rbp-6Ch] BYREF
  void *v343; // [rsp+98h] [rbp-68h] BYREF
  void *v344; // [rsp+A0h] [rbp-60h] BYREF
  void *v345; // [rsp+A8h] [rbp-58h] BYREF
  PRKEVENT p_Event; // [rsp+B0h] [rbp-50h] BYREF
  char v347; // [rsp+B8h] [rbp-48h]
  bool v348; // [rsp+B9h] [rbp-47h]
  _BYTE v349[5]; // [rsp+BAh] [rbp-46h]
  char v350; // [rsp+BFh] [rbp-41h]
  struct _LIST_ENTRY *v351; // [rsp+C0h] [rbp-40h]
  int v352; // [rsp+C8h] [rbp-38h]
  int v353; // [rsp+CCh] [rbp-34h]
  PRKEVENT p_Object; // [rsp+D0h] [rbp-30h] BYREF
  char v355; // [rsp+D8h] [rbp-28h]
  bool v356; // [rsp+D9h] [rbp-27h]
  _BYTE v357[5]; // [rsp+DAh] [rbp-26h]
  char v358; // [rsp+DFh] [rbp-21h]
  struct _LIST_ENTRY *v359; // [rsp+E0h] [rbp-20h]
  int v360; // [rsp+E8h] [rbp-18h]
  int v361; // [rsp+ECh] [rbp-14h]
  LARGE_INTEGER v362; // [rsp+F0h] [rbp-10h]
  int v363; // [rsp+F8h] [rbp-8h]
  unsigned __int8 *v364; // [rsp+100h] [rbp+0h]
  __int128 v365; // [rsp+108h] [rbp+8h] BYREF
  __int64 v366; // [rsp+118h] [rbp+18h]
  __int128 v367; // [rsp+120h] [rbp+20h] BYREF
  __int64 v368; // [rsp+130h] [rbp+30h]
  __int128 v369; // [rsp+138h] [rbp+38h] BYREF
  __int64 v370; // [rsp+148h] [rbp+48h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+150h] [rbp+50h] BYREF
  __int64 v372; // [rsp+158h] [rbp+58h]
  LARGE_INTEGER PerformanceCounter; // [rsp+160h] [rbp+60h]
  __int128 v374; // [rsp+168h] [rbp+68h] BYREF
  __int64 v375; // [rsp+178h] [rbp+78h]
  __int128 v376; // [rsp+180h] [rbp+80h] BYREF
  __int64 v377; // [rsp+190h] [rbp+90h]
  __int128 v378; // [rsp+198h] [rbp+98h] BYREF
  __int64 v379; // [rsp+1A8h] [rbp+A8h]
  struct _LIST_ENTRY *v380; // [rsp+1B0h] [rbp+B0h]
  _BYTE v381[80]; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _KEVENT Event; // [rsp+210h] [rbp+110h] BYREF
  struct _KEVENT Object; // [rsp+228h] [rbp+128h] BYREF
  char v384[16]; // [rsp+240h] [rbp+140h] BYREF
  struct _LIST_ENTRY v385[16]; // [rsp+250h] [rbp+150h] BYREF
  __int128 v386; // [rsp+350h] [rbp+250h] BYREF
  PVOID v387; // [rsp+360h] [rbp+260h]
  int v388; // [rsp+368h] [rbp+268h]
  PVOID v389[2]; // [rsp+370h] [rbp+270h]
  __int64 v390; // [rsp+380h] [rbp+280h]
  struct _SmsCheckpointContext *v391[13]; // [rsp+388h] [rbp+288h] BYREF
  __int64 v392; // [rsp+3F0h] [rbp+2F0h] BYREF
  void *v393[2]; // [rsp+3F8h] [rbp+2F8h]
  __int128 v394; // [rsp+408h] [rbp+308h]
  __int64 v395; // [rsp+418h] [rbp+318h]
  __int64 v396; // [rsp+420h] [rbp+320h] BYREF
  int v397; // [rsp+428h] [rbp+328h]
  char v398; // [rsp+42Ch] [rbp+32Ch]
  __int16 v399; // [rsp+42Dh] [rbp+32Dh]
  __int64 v400; // [rsp+430h] [rbp+330h] BYREF
  void *v401[2]; // [rsp+438h] [rbp+338h]
  __int128 v402; // [rsp+448h] [rbp+348h]
  __int64 v403; // [rsp+458h] [rbp+358h]
  __int64 v404; // [rsp+460h] [rbp+360h] BYREF
  int v405; // [rsp+468h] [rbp+368h]
  char v406; // [rsp+46Ch] [rbp+36Ch]
  __int16 v407; // [rsp+46Dh] [rbp+36Dh]
  __int64 AutoExpandPushLock; // [rsp+470h] [rbp+370h] BYREF
  void *v409[2]; // [rsp+478h] [rbp+378h]
  __int128 v410; // [rsp+488h] [rbp+388h]
  __int64 v411; // [rsp+498h] [rbp+398h]
  __int64 v412; // [rsp+4A0h] [rbp+3A0h] BYREF
  int v413; // [rsp+4A8h] [rbp+3A8h]
  char v414; // [rsp+4ACh] [rbp+3ACh]
  __int16 v415; // [rsp+4ADh] [rbp+3ADh]

  v6 = *((_QWORD *)this + 12);
  v8 = this;
  v334 = this;
  v9 = a1;
  v333 = a1;
  v10 = 0;
  v331 = *(CmsVolume **)(v6 + 24);
  v11 = v331;
  v336 = a4;
  v12 = a4;
  v364 = a5;
  Resource = 0;
  P = 0;
  memset(v385, 0, sizeof(v385));
  v387 = 0;
  v388 = 0;
  v386 = 0;
  v390 = 0;
  *(_OWORD *)v389 = 0;
  memset(v391, 0, sizeof(v391));
  *(_OWORD *)v381 = 0;
  PerformanceCounter.QuadPart = 0;
  v362.QuadPart = 0;
  PerformanceFrequency.QuadPart = 0;
  memset(&v381[24], 0, 56);
  v14 = *((_BYTE *)v331 + 76) + 1;
  AutoExpandPushLock = 0;
  v414 = v14;
  *(_OWORD *)v409 = 0;
  v413 = 500;
  v410 = 0;
  v415 = 0;
  v411 = 0;
  v412 = 0;
  v15 = *((_BYTE *)v331 + 76) + 1;
  v400 = 0;
  v406 = v15;
  v405 = 500;
  v407 = 0;
  v403 = 0;
  v404 = 0;
  *(_OWORD *)v401 = 0;
  v402 = 0;
  v398 = *((_BYTE *)v331 + 76);
  v392 = 0;
  v397 = 500;
  v399 = 0;
  v395 = 0;
  v396 = 0;
  v342 = 0;
  *(_OWORD *)v393 = 0;
  v394 = 0;
  if ( !v12 )
  {
    LOBYTE(v12) = 1;
    v336 = 1;
  }
  if ( a5 )
    *a5 = 0;
  if ( !a3 && (*((_DWORD *)v8 + 4) & 0x40000LL) != 0 )
  {
    v94 = 0;
    goto LABEL_210;
  }
  v16 = v12 & 1;
  v363 = v16;
  if ( v16 && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 12) + 24LL) + 3116LL) & 0x20000000) != 0 )
  {
    v94 = -1073741202;
    goto LABEL_210;
  }
  if ( a3 )
  {
    LOBYTE(v17) = 0;
  }
  else
  {
    ExAcquireResourceSharedLite((PERESOURCE)((char *)v11 + 1016), 1u);
    Resource = (PERESOURCE)*((_QWORD *)v11 + 188);
    v10 = Resource;
    ExAcquireResourceSharedLite(Resource, 1u);
    ExReleaseResourceLite((PERESOURCE)((char *)v11 + 1016));
    LOBYTE(v17) = 0;
    KeWaitForSingleObject(&Resource[1], Executive, 0, 0, 0);
    a3 = (struct _SmsCheckpointContext *)Resource;
  }
  if ( v16 && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 12) + 24LL) + 3116LL) & 0x20000000) != 0 )
  {
    if ( v10 )
      ExReleaseResourceLite(v10);
    v94 = -1073741202;
    goto LABEL_210;
  }
  *((_QWORD *)v9 + 2) |= 0x800uLL;
  if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    LOBYTE(v259) = 0;
    v260 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v8) + 10);
    if ( v260 )
      v259 = *(_QWORD *)(v260 + 384);
    v261 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v8) + 10);
    if ( v261 )
      v17 = *(_QWORD *)(v261 + 376);
    ActivityIdThread = IoGetActivityIdThread();
    McTemplateK0qii_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)TableTreeUpdateStart,
      ActivityIdThread,
      0,
      v17,
      v259);
    v10 = Resource;
  }
  v385[15].Flink = 0;
  v341 = v336 & 2;
  memset(&v391[1], 0, 24);
  if ( (v336 & 7) != 6 )
  {
    v94 = 0;
    ExAcquirePushLockSharedEx(&v412, 0);
    if ( HIBYTE(v415) )
      goto LABEL_379;
    ExReleasePushLockEx(&v412, 0);
    ExAcquirePushLockExclusiveEx(&v412, 0);
    if ( HIBYTE(v415) )
      goto LABEL_379;
    v199 = v413;
    AutoExpandPushLock = ExAllocateAutoExpandPushLock(1);
    if ( !AutoExpandPushLock )
    {
      v94 = -1073741670;
      goto LABEL_379;
    }
    v200 = v199 >> 2;
    if ( v200 < 3 )
      v200 = 3;
    v201 = 0;
    while ( 1 )
    {
      if ( v201 )
      {
LABEL_375:
        v11 = v331;
        v10 = Resource;
        v8 = v334;
        v409[0] = v201;
        if ( v201 )
        {
          memset(v201, 0, 24LL * LODWORD(v409[1]));
          for ( i = 0; i < LODWORD(v409[1]); *((_QWORD *)v409[0] + 3 * v203 + 2) = 0 )
            v203 = i++;
          v94 = 0;
          HIBYTE(v415) = 1;
        }
        else
        {
          v94 = -1073741670;
        }
LABEL_379:
        ExReleasePushLockEx(&v412, 0);
        if ( v94 < 0 )
          goto LABEL_582;
        v94 = 0;
        ExAcquirePushLockSharedEx(&v404, 0);
        if ( !HIBYTE(v407) )
        {
          ExReleasePushLockEx(&v404, 0);
          ExAcquirePushLockExclusiveEx(&v404, 0);
          if ( !HIBYTE(v407) )
          {
            v204 = v405;
            v400 = ExAllocateAutoExpandPushLock(1);
            if ( !v400 )
            {
              v94 = -1073741670;
              goto LABEL_391;
            }
            v205 = v204 >> 2;
            if ( v205 < 3 )
              v205 = 3;
            PoolWithTag = 0;
            while ( 2 )
            {
              if ( PoolWithTag )
              {
LABEL_387:
                v9 = v333;
                v10 = Resource;
                v8 = v334;
                v401[0] = PoolWithTag;
                if ( PoolWithTag )
                {
                  memset(PoolWithTag, 0, 24LL * LODWORD(v401[1]));
                  for ( j = 0; j < LODWORD(v401[1]); *((_QWORD *)v401[0] + 3 * v208 + 2) = 0 )
                    v208 = j++;
                  v94 = 0;
                  HIBYTE(v407) = 1;
                }
                else
                {
                  v94 = -1073741670;
                }
                break;
              }
              v217 = 0;
              v218 = qword_1C0108FF0;
              do
              {
                v219 = *(_DWORD *)v218;
                if ( *(_DWORD *)v218 > v205 )
                  goto LABEL_429;
                ++v217;
                v218 = (__int64 *)((char *)v218 + 4);
              }
              while ( v217 < 0x48 );
              v219 = 7199369;
LABEL_429:
              LODWORD(v401[1]) = v219;
              if ( v219 == -1 )
                goto LABEL_567;
              v226 = 24LL * v219;
              if ( !is_mul_ok(v219, 0x18u) )
                v226 = -1;
              v227 = (unsigned int *)(qword_1C0136FB8 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
              if ( v226 > *v227 )
              {
                v227 = 0;
                v266 = v226 + 8;
              }
              else
              {
                if ( *((_BYTE *)v227 + 8) )
                {
                  v228 = (struct _PAGED_LOOKASIDE_LIST *)(v227 + 16);
                  if ( *((_BYTE *)v227 + 9) )
                  {
                    ++v227[21];
                    PoolWithTag = ExpInterlockedPopEntrySList(&v228->L.ListHead);
                    if ( PoolWithTag )
                      goto LABEL_436;
                    ++v227[22];
                    v233 = (_QWORD *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v227 + 14))(
                                       v227[25],
                                       v227[27],
                                       v227[26]);
                  }
                  else
                  {
                    v233 = ExAllocateFromPagedLookasideList(v228);
                  }
LABEL_456:
                  PoolWithTag = v233;
LABEL_436:
                  if ( PoolWithTag )
                  {
LABEL_437:
                    *PoolWithTag++ = v227;
                    goto LABEL_438;
                  }
                }
                else if ( (int)v227[20] > (int)v227[22] )
                {
                  v265 = _InterlockedDecrement((volatile signed __int32 *)v227 + 20);
                  if ( v265 >= (int)v227[22] && v265 >= 0 )
                  {
                    v233 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v227 + 4);
                    goto LABEL_456;
                  }
                  _InterlockedIncrement((volatile signed __int32 *)v227 + 20);
                }
                v266 = v227[1];
              }
              PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v266, 0x6950534Du);
              if ( PoolWithTag )
                goto LABEL_437;
LABEL_438:
              if ( !PoolWithTag )
LABEL_567:
                v205 >>= 2;
              if ( v205 <= 1 )
                goto LABEL_387;
              continue;
            }
          }
        }
LABEL_391:
        ExReleasePushLockEx(&v404, 0);
        if ( v94 < 0 )
          goto LABEL_582;
        v94 = 0;
        ExAcquirePushLockSharedEx(&v396, 0);
        if ( HIBYTE(v399) )
          goto LABEL_403;
        ExReleasePushLockEx(&v396, 0);
        ExAcquirePushLockExclusiveEx(&v396, 0);
        if ( HIBYTE(v399) )
          goto LABEL_403;
        v209 = v397;
        v392 = ExAllocateAutoExpandPushLock(1);
        if ( !v392 )
        {
          v94 = -1073741670;
          goto LABEL_403;
        }
        v210 = v209 >> 2;
        if ( v210 < 3 )
          v210 = 3;
        v211 = 0;
        while ( 2 )
        {
          if ( v211 )
          {
LABEL_399:
            v11 = v331;
            v10 = Resource;
            v8 = v334;
            v393[0] = v211;
            if ( v211 )
            {
              memset(v211, 0, 24LL * LODWORD(v393[1]));
              for ( k = 0; k < LODWORD(v393[1]); *((_QWORD *)v393[0] + 3 * v213 + 2) = 0 )
                v213 = k++;
              v94 = 0;
              HIBYTE(v399) = 1;
            }
            else
            {
              v94 = -1073741670;
            }
LABEL_403:
            ExReleasePushLockEx(&v396, 0);
            if ( v94 >= 0 )
            {
              v391[1] = (struct _SmsCheckpointContext *)&AutoExpandPushLock;
              v391[2] = (struct _SmsCheckpointContext *)&v400;
              v391[3] = (struct _SmsCheckpointContext *)&v392;
              goto LABEL_15;
            }
LABEL_582:
            if ( v10 )
              ExReleaseResourceLite(v10);
            goto LABEL_180;
          }
          v220 = 0;
          v221 = qword_1C0108FF0;
          while ( 1 )
          {
            v222 = *(_DWORD *)v221;
            if ( *(_DWORD *)v221 > v210 )
              break;
            ++v220;
            v221 = (__int64 *)((char *)v221 + 4);
            if ( v220 >= 0x48 )
            {
              v222 = 7199369;
              break;
            }
          }
          LODWORD(v393[1]) = v222;
          if ( v222 == -1 )
            goto LABEL_580;
          v229 = 24LL * v222;
          if ( !is_mul_ok(v222, 0x18u) )
            v229 = -1;
          v230 = (unsigned int *)(qword_1C0136FB8 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
          if ( v229 > *v230 )
          {
            v230 = 0;
            v268 = v229 + 8;
          }
          else
          {
            if ( *((_BYTE *)v230 + 8) )
            {
              v231 = (struct _PAGED_LOOKASIDE_LIST *)(v230 + 16);
              if ( *((_BYTE *)v230 + 9) )
              {
                ++v230[21];
                v211 = ExpInterlockedPopEntrySList(&v231->L.ListHead);
                if ( v211 )
                  goto LABEL_448;
                ++v230[22];
                v234 = (_QWORD *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v230 + 14))(
                                   v230[25],
                                   v230[27],
                                   v230[26]);
              }
              else
              {
                v234 = ExAllocateFromPagedLookasideList(v231);
              }
LABEL_458:
              v211 = v234;
LABEL_448:
              if ( v211 )
              {
LABEL_449:
                *v211++ = v230;
                goto LABEL_450;
              }
            }
            else if ( (int)v230[20] > (int)v230[22] )
            {
              v267 = _InterlockedDecrement((volatile signed __int32 *)v230 + 20);
              if ( v267 >= (int)v230[22] && v267 >= 0 )
              {
                v234 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v230 + 4);
                goto LABEL_458;
              }
              _InterlockedIncrement((volatile signed __int32 *)v230 + 20);
            }
            v268 = v230[1];
          }
          v211 = ExAllocatePoolWithTag((POOL_TYPE)512, v268, 0x6950534Du);
          if ( v211 )
            goto LABEL_449;
LABEL_450:
          if ( !v211 )
LABEL_580:
            v210 >>= 2;
          if ( v210 <= 1 )
            goto LABEL_399;
          continue;
        }
      }
      v214 = 0;
      v215 = qword_1C0108FF0;
      do
      {
        v216 = *(_DWORD *)v215;
        if ( *(_DWORD *)v215 > v200 )
          goto LABEL_417;
        ++v214;
        v215 = (__int64 *)((char *)v215 + 4);
      }
      while ( v214 < 0x48 );
      v216 = 7199369;
LABEL_417:
      LODWORD(v409[1]) = v216;
      if ( v216 == -1 )
      {
LABEL_554:
        v200 >>= 2;
        goto LABEL_427;
      }
      v223 = 24LL * v216;
      if ( !is_mul_ok(v216, 0x18u) )
        v223 = -1;
      v224 = (unsigned int *)(qword_1C0136FB8 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v223 <= *v224 )
        break;
      v224 = 0;
      v264 = v223 + 8;
LABEL_552:
      v201 = ExAllocatePoolWithTag((POOL_TYPE)512, v264, 0x6950534Du);
      if ( v201 )
LABEL_425:
        *v201++ = v224;
      if ( !v201 )
        goto LABEL_554;
LABEL_427:
      if ( v200 <= 1 )
        goto LABEL_375;
    }
    if ( *((_BYTE *)v224 + 8) )
    {
      v225 = (struct _PAGED_LOOKASIDE_LIST *)(v224 + 16);
      if ( *((_BYTE *)v224 + 9) )
      {
        ++v224[21];
        v201 = ExpInterlockedPopEntrySList(&v225->L.ListHead);
        if ( v201 )
          goto LABEL_424;
        ++v224[22];
        v232 = (_QWORD *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v224 + 14))(v224[25], v224[27], v224[26]);
      }
      else
      {
        v232 = ExAllocateFromPagedLookasideList(v225);
      }
LABEL_454:
      v201 = v232;
LABEL_424:
      if ( v201 )
        goto LABEL_425;
      goto LABEL_550;
    }
    if ( (int)v224[20] > (int)v224[22] )
    {
      v263 = _InterlockedDecrement((volatile signed __int32 *)v224 + 20);
      if ( v263 >= (int)v224[22] && v263 >= 0 )
      {
        v232 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v224 + 4);
        goto LABEL_454;
      }
      _InterlockedIncrement((volatile signed __int32 *)v224 + 20);
    }
LABEL_550:
    v264 = v224[1];
    goto LABEL_552;
  }
LABEL_15:
  v18 = (CmsBPlusTable *)*((_QWORD *)v8 + 4);
  for ( m = v8; v18 != m; v18 = (CmsBPlusTable *)*((_QWORD *)v18 + 4) )
    m = v18;
  for ( n = (CmsBPlusTable *)*((_QWORD *)m + 9); n != m; n = (CmsBPlusTable *)*((_QWORD *)n + 9) )
    m = n;
  v21 = *((_QWORD *)m + 10);
  v22 = (struct _ERESOURCE *)(*((_QWORD *)v9 + 4) + 3160LL);
  v335 = 0;
  ExAcquireResourceSharedLite(v22, 1u);
  v23 = *(_QWORD *)(v21 + 128) + 112LL;
  v24 = (_QWORD *)v23;
  do
  {
    v25 = (CmsBPlusTable *)*(v24 - 14);
    v24 = (_QWORD *)*v24;
    CmsBPlusTable::ReservePageFreeBuffersWorker(v25, v9, &v335);
  }
  while ( v24 != (_QWORD *)v23 );
  ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v9 + 4) + 3160LL));
  if ( v335 > SLODWORD(v385[15].Flink)
    && (int)CmsLookasides::SatisfyReservation(17, (unsigned int)(v335 - LODWORD(v385[15].Flink))) >= 0 )
  {
    if ( (int)CmsLookasides::SatisfyReservation(18, (unsigned int)(v335 - HIDWORD(v385[15].Flink))) < 0 )
    {
      _InterlockedExchangeAdd((volatile signed __int32 *)(qword_1C0136F98 + 88), LODWORD(v385[15].Flink) - v335);
    }
    else
    {
      LODWORD(v385[15].Flink) = v335;
      HIDWORD(v385[15].Flink) = v335;
    }
  }
  v26 = (CmsBPlusTable *)*((_QWORD *)v8 + 4);
  for ( ii = v8; v26 != ii; v26 = (CmsBPlusTable *)*((_QWORD *)v26 + 4) )
    ii = v26;
  for ( jj = (CmsBPlusTable *)*((_QWORD *)ii + 9); jj != ii; jj = (CmsBPlusTable *)*((_QWORD *)jj + 9) )
    ii = jj;
  v29 = 0;
  v30 = (struct _ERESOURCE *)(*((_QWORD *)v9 + 4) + 3160LL);
  v31 = **((_QWORD **)ii + 10);
  v332 = 0;
  ExAcquireResourceSharedLite(v30, 1u);
LABEL_23:
  v32 = v29;
  v29 = *(struct _LIST_ENTRY **)(*(_QWORD *)(v31 + 80) + 128LL);
  _InterlockedIncrement((volatile signed __int32 *)&v29->Flink->Blink);
  if ( v32 != v29 && v32 )
  {
    v32[9].Flink = 0;
    KeSetEvent((PRKEVENT)&v32[10], 0, 0);
    v332 = v32 + 7;
    do
    {
      v269 = v332;
      v332 = v332->Flink;
      if ( !(unsigned __int8)ExIsFastResourceHeldExclusive(&v269[-7].Blink) )
        break;
      ExReleaseResourceLite((PERESOURCE)&v269[-7].Flink[5].Flink->Blink);
    }
    while ( v332 != &v29[7] );
    CmsReferenced::Release((CmsReferenced *)v32->Flink);
  }
  v332 = v29 + 7;
  do
  {
    v33 = v332 - 7;
    ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v9 + 4) + 3160LL));
    ExAcquireResourceExclusiveLite((PERESOURCE)&v332[-7].Flink[5].Flink->Blink, 1u);
    ExAcquireResourceSharedLite((PERESOURCE)(*((_QWORD *)v9 + 4) + 3160LL), 1u);
    v332 = v332->Flink;
    KeClearEvent((PRKEVENT)&v33[10]);
    if ( v33 == v29 )
      v33[9].Flink = (struct _LIST_ENTRY *)KeGetCurrentThread();
    if ( *(struct _LIST_ENTRY **)(*(_QWORD *)(v31 + 80) + 128LL) != v29 || v33[8].Flink != v29 )
      goto LABEL_23;
  }
  while ( v332 != &v29[7] );
  v34 = v333;
  v29[9].Blink = (struct _LIST_ENTRY *)KeGetCurrentThread();
  v29[9].Flink = 0;
  ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v34 + 4) + 3160LL));
  Flink = v29->Flink;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v29->Flink->Blink, 0xFFFFFFFF) == 1 && Flink )
    ((void (__fastcall *)(struct _LIST_ENTRY *, __int64))Flink->Flink->Flink)(Flink, 1);
  *((_QWORD *)v34 + 2) |= 0x20000000uLL;
  if ( (*((_QWORD *)v34 + 2) & 0x400LL) != 0 && a6 != *((_QWORD *)v11 + 233) )
  {
    v43 = v334;
    v94 = -1073741823;
    v270 = CmsBPlusTable::BindableUnitTable(v334);
    CmsBPlusTable::UnbindLastBoundList(
      *((struct CmsTransactionContext **)v270 + 10),
      *(struct _SmsBindable **)(*((_QWORD *)v270 + 10) + 128LL));
    v9 = v333;
    CmsBPlusTable::ReleaseBoundTreesWithoutUnbinding(v333, v271);
    goto LABEL_181;
  }
  PerformanceCounter = KeQueryPerformanceCounter(0);
  KeQueryPerformanceCounter(&PerformanceFrequency);
  v36 = v334;
  v37 = (CmsBPlusTable *)*((_QWORD *)v334 + 4);
  if ( v37 != v334 )
  {
    do
    {
      v36 = v37;
      v37 = (CmsBPlusTable *)*((_QWORD *)v37 + 4);
    }
    while ( v37 != v36 );
  }
  for ( kk = (CmsBPlusTable *)*((_QWORD *)v36 + 9); kk != v36; kk = (CmsBPlusTable *)*((_QWORD *)kk + 9) )
    v36 = kk;
  v39 = *(struct _LIST_ENTRY **)(*((_QWORD *)v36 + 10) + 128LL);
  v40 = v39 + 7;
  v41 = v39 + 7;
  do
  {
    v42 = (CmsBPlusTable *)v41[-7].Flink;
    v41 = v41->Flink;
    CmsBPlusTable::MergeDeleteQueueIntoPreviousGeneration(v42, v34, v385);
  }
  while ( v41 != v40 );
  v380 = v40->Flink;
  if ( (*((_DWORD *)v34 + 4) & 0x400LL) != 0 )
  {
    if ( !*((_QWORD *)v331 + 366) )
      goto LABEL_41;
    memset(v381, 0, sizeof(v381));
    KeInitializeEvent((PRKEVENT)&v381[32], NotificationEvent, 0);
    CmsDurableLog::InsertVirtualWaiter(
      (CmsVolume *)((char *)v331 + 2608),
      (struct _SmsFlushWaiter *)v381,
      (CmsVolume *)((char *)v331 + 2928),
      0);
    CmsDurableLog::WriteLog((CmsVolume *)((char *)v331 + 2608));
    *((_QWORD *)v331 + 366) = 0;
    goto LABEL_307;
  }
  ExAcquirePushLockExclusiveEx(&v39[32].Blink, 0);
  if ( v39[33].Flink || v39[31].Flink )
  {
    KeInitializeEvent((PRKEVENT)&v381[32], NotificationEvent, 0);
    CmsDurableLog::MergeMemLog(
      (CmsVolume *)((char *)v331 + 2608),
      (struct CmsMemLog *)&v39[27],
      v171,
      (struct _SmsFlushWaiter *)v381,
      Timeout,
      1u);
LABEL_307:
    CmsDurableLog::WaitForLogFlush(v172, (struct _SmsFlushWaiter *)v381);
    goto LABEL_41;
  }
  ExReleasePushLockEx(&v39[32].Blink, 0);
LABEL_41:
  if ( (*((_DWORD *)v34 + 4) & 0x400LL) != 0 )
  {
    v184 = v331;
    v185 = *((_DWORD *)v331 + 726) & 4;
    if ( v185 && *((_QWORD *)v331 + 335) )
    {
      v186 = *((_QWORD *)v331 + 361);
      if ( v186 )
        v187 = *(_QWORD *)(v186 + 104);
      else
        v187 = *((_QWORD *)v331 + 342) + 1LL;
    }
    else
    {
      v187 = ML_LSN_NULL;
    }
    v372 = v187;
    if ( v185 && *((_QWORD *)v331 + 335) )
      *((_QWORD *)v331 + 343) = v187;
    CmsVolume::MergeBufferedCheckpointState(v184, v184, a3);
  }
  v43 = v334;
  v44 = v336;
  v385[2].Flink = (struct _LIST_ENTRY *)&v385[1].Blink;
  v385[1].Blink = (struct _LIST_ENTRY *)&v385[1].Blink;
  v385[3].Flink = (struct _LIST_ENTRY *)&v385[2].Blink;
  v385[2].Blink = (struct _LIST_ENTRY *)&v385[2].Blink;
  v385[4].Flink = (struct _LIST_ENTRY *)&v385[3].Blink;
  v385[3].Blink = (struct _LIST_ENTRY *)&v385[3].Blink;
  v385[5].Flink = (struct _LIST_ENTRY *)&v385[4].Blink;
  v385[4].Blink = (struct _LIST_ENTRY *)&v385[4].Blink;
  v385[11].Blink = &v385[11];
  v385[11].Flink = &v385[11];
  v45 = v39 + 7;
  v385[0].Flink = v39->Flink[6].Flink[1].Blink;
  v385[14].Blink = 0;
  v46 = 0;
  v385[13].Flink = 0;
  memset(&v391[4], 0, 45);
  v391[11] = 0;
  LODWORD(v391[12]) = 0;
  v332 = 0;
  v385[0].Blink = v39;
  v385[15].Blink = (struct _LIST_ENTRY *)v336;
  v385[1].Flink = (struct _LIST_ENTRY *)v334;
  v391[0] = a3;
  do
  {
    v47 = v45 - 7;
    v45 = v45->Flink;
    if ( v39 != v47 )
    {
      v153 = v39[12].Flink;
      v154 = (struct _LIST_ENTRY *)((char *)v47 + 184);
      if ( v153->Flink != (struct _LIST_ENTRY *)&v39[11].Blink )
        goto LABEL_677;
      v154->Flink = (struct _LIST_ENTRY *)((char *)v39 + 184);
      v47[12].Flink = v153;
      v153->Flink = v154;
      v39[12].Flink = v154;
      v46 = v332;
    }
    Blink = v47[12].Blink;
    if ( Blink )
    {
      if ( !v46 )
      {
        v46 = v47[13].Flink;
        v49 = (struct _SmsDirtyTableEntries *)v47[12].Blink;
        v332 = v46;
        P = Blink;
        continue;
      }
      v46->Flink = Blink;
      v46 = v47[13].Flink;
      v332 = v46;
    }
    v49 = (struct _SmsDirtyTableEntries *)P;
  }
  while ( v45 != v40 );
  CmsBPlusTable::RunFailableTreeUpdateForAllDirtyTrees(v34, (struct SmsWritePlan *)v385, v49);
  Blink_high = HIDWORD(v385[15].Blink);
  if ( (BYTE4(v385[15].Blink) & 1) != 0 )
  {
    Blink_high = HIDWORD(v385[15].Blink) | 2;
    HIDWORD(v385[15].Blink) |= 2u;
  }
  if ( (Blink_high & 2) == 0 && (*((_DWORD *)v34 + 4) & 0x400LL) != 0 && a6 != *((_QWORD *)v331 + 233) )
  {
    Blink_high |= 2u;
    LODWORD(v391[8]) = -1073741823;
    v34 = v333;
    HIDWORD(v385[15].Blink) = Blink_high;
  }
  v51 = v331;
  if ( (Blink_high & 2) != 0 )
  {
    if ( (*((_QWORD *)v34 + 2) & 0x400LL) != 0 && (v44 & 1) != 0 )
    {
      CmsBPlusTable::PersistSmallAllocatorForCheckpoint(
        v34,
        *((struct CmsAllocator **)v331 + 380),
        (struct SmsWritePlan *)v385,
        v391[0],
        1);
      CmsBPlusTable::PersistSmallAllocatorForCheckpoint(
        v34,
        *((struct CmsAllocator **)v331 + 380),
        (struct SmsWritePlan *)v385,
        v391[0],
        1);
    }
    CmsBPlusTable::ForEachBindableInList(
      (_DWORD)v34,
      (_DWORD)v39 + 184,
      (unsigned int)CmsBPlusTable::RunPageCleanupForAllDirtyTrees,
      (unsigned int)v385,
      108);
    CmsBPlusTable::UnbindLastBoundList(v272, (struct _SmsBindable *)v39);
    v273 = *((_QWORD *)v34 + 2);
    if ( (v273 & 0x400) != 0 )
    {
      v274 = *((_QWORD *)v331 + 381);
      if ( v274 )
      {
        if ( *(_QWORD *)(v274 + 64) )
        {
          *(_BYTE *)(v274 + 372) &= ~0x20u;
          v273 = *((_QWORD *)v34 + 2);
        }
      }
    }
    if ( (v273 & 0x400) != 0 )
      *((_DWORD *)v51 + 779) &= ~0x800u;
    CmsTxMemLog::DiscardPendingRecords((CmsTxMemLog *)&v386, (CmsVolume *)((char *)v51 + 2608));
    v275 = v391[11];
    if ( v391[11] )
    {
      do
      {
        v276 = v275;
        v275 = *(struct _SmsCheckpointContext **)v275;
        *(_QWORD *)v276 = 0;
      }
      while ( v275 );
      v391[11] = 0;
    }
    CmsBPlusTable::ReleaseBoundTreesWithoutUnbinding(v34, (struct _SmsBindable *)v39);
    v277 = Resource;
    *((_QWORD *)v34 + 2) &= ~0x20000000uLL;
    if ( v277 )
      ExReleaseResourceLite(v277);
    v94 = (int)v391[8];
    v9 = v333;
    v11 = v331;
    goto LABEL_181;
  }
  if ( (*((_QWORD *)v34 + 2) & 0x400) != 0 )
  {
    v188 = *((_QWORD *)v331 + 300);
    if ( v188 )
    {
      v189 = *(MsAllocator::RangeArrayStrategy::State **)(v188 + 16);
      if ( v189 )
        MsAllocator::RangeArrayStrategy::State::ResetHinting(v189);
    }
    CmsVolume::TrimAllocators(v331, v34);
  }
  p_Blink = &v39[11].Blink;
  v53 = &v39[11].Blink;
  do
  {
    v54 = (CmsBPlusTable *)*(v53 - 23);
    v53 = (struct _LIST_ENTRY **)*v53;
    CmsBPlusTable::ResetDirtyTablesLists(v54, v34, 0);
  }
  while ( v53 != p_Blink );
  v55 = *((_QWORD *)v34 + 4);
  if ( (*((_QWORD *)v34 + 2) & 0x2000000000LL) == 0 )
  {
    v56 = v39 + 7;
    do
    {
      v57 = (CmsBPlusTable *)v56[-7].Flink;
      v56 = v56->Flink;
      CmsBPlusTable::LogTreeUpdateRedo(v57, v34, v385);
    }
    while ( v56 != v40 );
  }
  if ( (_QWORD)v386 )
  {
    ExAcquirePushLockExclusiveEx(&v39[32].Blink, 0);
    CmsMemLog::MergeTxLog(
      (CmsMemLog *)&v39[27],
      (struct CmsTxMemLog *)&v386,
      (struct CmsDurableLog *)(v55 + 2608),
      v278,
      0,
      0,
      0);
    KeInitializeEvent((PRKEVENT)&v381[32], NotificationEvent, 0);
    CmsDurableLog::MergeMemLog(
      (CmsDurableLog *)(v55 + 2608),
      (struct CmsMemLog *)&v39[27],
      v279,
      (struct _SmsFlushWaiter *)v381,
      Timeouta,
      1u);
    CmsDurableLog::WaitForLogFlush(v280, (struct _SmsFlushWaiter *)v381);
  }
  if ( (*((_DWORD *)v34 + 4) & 0x400LL) == 0 )
  {
    v58 = v331;
    v59 = v39 + 27;
    v60 = 0;
    *((_BYTE *)v331 + 2672) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v331 + 333);
    if ( v39[28].Flink )
    {
      v173 = v59->Flink;
      if ( v59->Flink->Blink != v59 || (v174 = v39[27].Blink, v174->Flink != v59) )
LABEL_677:
        __fastfail(3u);
      v174->Flink = v173;
      v173->Blink = v174;
      v39[28].Flink = 0;
      v59->Flink = 0;
      v60 = (CmsReferenced *)v39->Flink;
    }
    v51 = v58;
    KeReleaseSpinLock((PKSPIN_LOCK)v58 + 333, *((_BYTE *)v58 + 2672));
    if ( v60 )
      CmsReferenced::Release(v60);
  }
  if ( P )
  {
    v61 = P;
    do
    {
      v62 = 0;
      v63 = v61 + 1;
      do
      {
        if ( *v63 )
        {
          v64 = (CmsBPlusTable **)&v61[8 * v62 + 1 + (unsigned int)v62];
          goto LABEL_70;
        }
        v62 = (unsigned int)(v62 + 1);
        v63 += 9;
      }
      while ( (unsigned int)v62 < 8 );
      v61 = (_QWORD *)*v61;
    }
    while ( v61 );
    v64 = 0;
    LODWORD(v62) = -1;
LABEL_70:
    while ( v64 )
    {
      CmsBPlusTable::CopyStateToTreeUpdateGenAndAcquireGeometryLock(*v64, v34, 0, (struct _SmsDirtyTableEntry *)v64);
      v65 = &v64[-9 * (int)v62 - 1];
      if ( !v65 )
        break;
      while ( 1 )
      {
        v62 = (unsigned int)(v62 + 1);
        if ( (unsigned int)v62 < 8 )
          break;
LABEL_76:
        v65 = (CmsBPlusTable **)*v65;
        LODWORD(v62) = -1;
        if ( !v65 )
          goto LABEL_77;
      }
      v66 = &v65[8 * v62 + 1] + (unsigned int)v62;
      while ( !*v66 )
      {
        v62 = (unsigned int)(v62 + 1);
        v66 += 9;
        if ( (unsigned int)v62 >= 8 )
          goto LABEL_76;
      }
      v64 = &v65[9 * v62 + 1];
    }
LABEL_77:
    v67 = P;
    do
    {
      v68 = 0;
      v69 = v67 + 1;
      do
      {
        if ( *v69 )
        {
          v70 = (CmsBPlusTable **)&v67[8 * v68 + 1 + (unsigned int)v68];
          goto LABEL_81;
        }
        v68 = (unsigned int)(v68 + 1);
        v69 += 9;
      }
      while ( (unsigned int)v68 < 8 );
      v67 = (_QWORD *)*v67;
    }
    while ( v67 );
    v70 = 0;
    LODWORD(v68) = -1;
LABEL_81:
    while ( v70 )
    {
      CmsBPlusTable::ResetStateForNextGeneration(*v70, v34, v385, (struct _SmsDirtyTableEntry *)v70);
      v71 = &v70[-9 * (int)v68 - 1];
      if ( !v71 )
        break;
      while ( 1 )
      {
        v68 = (unsigned int)(v68 + 1);
        if ( (unsigned int)v68 < 8 )
          break;
LABEL_87:
        v71 = (CmsBPlusTable **)*v71;
        LODWORD(v68) = -1;
        if ( !v71 )
          goto LABEL_88;
      }
      v72 = &v71[8 * v68 + 1] + (unsigned int)v68;
      while ( !*v72 )
      {
        v68 = (unsigned int)(v68 + 1);
        v72 += 9;
        if ( (unsigned int)v68 >= 8 )
          goto LABEL_87;
      }
      v70 = &v71[9 * v68 + 1];
    }
LABEL_88:
    v73 = P;
    do
    {
      v74 = 0;
      v75 = v73 + 1;
      do
      {
        if ( *v75 )
        {
          v76 = (CmsBPlusTable **)&v73[8 * v74 + 1 + (unsigned int)v74];
          goto LABEL_92;
        }
        v74 = (unsigned int)(v74 + 1);
        v75 += 9;
      }
      while ( (unsigned int)v74 < 8 );
      v73 = (_QWORD *)*v73;
    }
    while ( v73 );
    v76 = 0;
    LODWORD(v74) = -1;
LABEL_92:
    while ( v76 )
    {
      CmsBPlusTable::IncrementPersistGeneration(*v76, v34, &v342, (struct _SmsDirtyTableEntry *)v76);
      v77 = &v76[-9 * (int)v74 - 1];
      if ( !v77 )
        break;
      while ( 1 )
      {
        v74 = (unsigned int)(v74 + 1);
        if ( (unsigned int)v74 < 8 )
          break;
LABEL_98:
        v77 = (CmsBPlusTable **)*v77;
        LODWORD(v74) = -1;
        if ( !v77 )
          goto LABEL_99;
      }
      v78 = &v77[8 * v74 + 1] + (unsigned int)v74;
      while ( !*v78 )
      {
        v74 = (unsigned int)(v74 + 1);
        v78 += 9;
        if ( (unsigned int)v74 >= 8 )
          goto LABEL_98;
      }
      v76 = &v77[9 * v74 + 1];
    }
  }
  else if ( CmsBPlusTable::IsRootOfBindableUnit((CmsBPlusTable *)v39->Flink) )
  {
    v198 = (struct _SmsLazyWriterEntry *)&v39[36].Blink;
    if ( *(struct _SmsLazyWriterEntry **)v198 != v198 )
      MspRemoveLazyWriterEntry(v198);
  }
LABEL_99:
  v79 = v391[11];
  if ( v391[11] )
  {
    do
    {
      v243 = CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)v79 + 15));
      CmsVolume::FormatPageHeader(
        v51,
        *((_QWORD *)v79 + 16),
        (char *)v79 + 8,
        *((_QWORD *)v243 + 10) + 376LL,
        725766989);
      if ( (*((_QWORD *)v79 + 51) & 0x20000000LL) != 0 )
      {
        v244 = v385[2].Flink;
        v245 = (struct _LIST_ENTRY *)((char *)v79 + 88);
        if ( v385[2].Flink->Flink != (struct _LIST_ENTRY *)&v385[1].Blink )
          goto LABEL_677;
        *((_QWORD *)v79 + 12) = v385[2].Flink;
        v245->Flink = (struct _LIST_ENTRY *)&v385[1].Blink;
        v244->Flink = v245;
        ++LODWORD(v385[14].Blink);
        v385[2].Flink = (struct _LIST_ENTRY *)((char *)v79 + 88);
      }
      v79 = *(struct _SmsCheckpointContext **)v79;
    }
    while ( v79 );
    v391[11] = 0;
  }
  if ( (*((_DWORD *)v34 + 4) & 0x400LL) != 0 )
  {
    v190 = *((_QWORD *)v51 + 381);
    if ( v190 && *(_QWORD *)(v190 + 64) )
      *(_BYTE *)(v190 + 372) &= ~0x20u;
    *((_DWORD *)v51 + 779) &= ~0x800u;
    if ( (*((_DWORD *)v51 + 779) & 2) == 0 )
    {
      v191 = *(_QWORD *)CmsDurableLog::GetOldestRecordReference((char *)v51 + 2608, v384, 0);
      if ( v191 )
        *((_QWORD *)v51 + 234) = v191;
      if ( *((_BYTE *)v51 + 3114) )
      {
        _InterlockedIncrement64((volatile signed __int64 *)v51 + 231);
      }
      else
      {
        v241 = *((_QWORD *)v51 + 361);
        if ( v241 )
        {
          if ( (*((_DWORD *)v51 + 726) & 4) != 0 && *((_QWORD *)v51 + 335) )
            v242 = *(_QWORD *)(v241 + 112);
          else
            v242 = *(_QWORD *)(*((_QWORD *)v51 + 336) + 1848LL);
          _InterlockedExchange64((volatile __int64 *)v51 + 231, v242);
        }
      }
      _InterlockedIncrement64((volatile signed __int64 *)v51 + 230);
      *((_QWORD *)v51 + 232) = 0;
    }
    CmsDurableLog::ReleaseRecordReference((CmsVolume *)((char *)v51 + 2608), (struct CmsMemLog *)&v39[27]);
  }
  if ( !v341 )
  {
    v80 = KeQueryPerformanceCounter(0);
    v81 = (struct _ERESOURCE *)(*((_QWORD *)v34 + 4) + 3160LL);
    v362 = v80;
    ExAcquireResourceSharedLite(v81, 1u);
    v82 = v39[8].Flink;
    if ( v82[7].Flink == &v82[7] )
    {
      v83 = v82->Flink;
      v82[31].Flink = 0;
      if ( ((__int64)v83[1].Flink & 0x40000) == 0 )
        v82[32].Blink = 0;
      v82[9].Blink = 0;
      KeSetEvent((PRKEVENT)&v82[10], 0, 0);
      ExConvertExclusiveToSharedLite((PERESOURCE)&v82->Flink[5].Flink->Blink);
      ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v34 + 4) + 3160LL));
    }
    else
    {
      ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v34 + 4) + 3160LL));
      ExAcquireResourceExclusiveLite((PERESOURCE)(*((_QWORD *)v34 + 4) + 3160LL), 1u);
      v175 = v39[8].Flink;
      v176 = v175 + 7;
      do
      {
        v177 = v176[-7].Flink;
        v178 = v176 - 7;
        v179 = v176;
        v176 = v176->Flink;
        v178[8].Blink = v177;
        v180 = v178->Flink;
        v178[8].Flink = v178;
        v179->Blink = v179;
        v179->Flink = v179;
        v178[31].Flink = 0;
        if ( ((__int64)v180[1].Flink & 0x40000) == 0 )
          v178[32].Blink = 0;
        if ( v178 == v175 )
        {
          v178[9].Blink = 0;
          KeSetEvent((PRKEVENT)&v178[10], 0, 0);
        }
      }
      while ( v176 != &v175[7] );
      v181 = &v175[11].Blink;
      v182 = v181;
      do
      {
        v183 = v182 - 23;
        v182 = (struct _LIST_ENTRY **)*v182;
        ExConvertExclusiveToSharedLite((PERESOURCE)&(*v183)[5].Flink->Blink);
      }
      while ( v182 != v181 );
      ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v34 + 4) + 3160LL));
      v51 = v331;
    }
  }
  *((_QWORD *)v34 + 2) |= 0x1000uLL;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  if ( LODWORD(v385[14].Blink) < 0x64
    || (v281 = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x60u, 0x6950534Du), (v283 = v281) == 0) )
  {
LABEL_107:
    *(_DWORD *)&v349[1] = 0;
    p_Event = &Event;
    v84 = *((_QWORD *)v34 + 2);
    v350 = 0;
    v353 = 0;
    v347 = 0;
    v348 = (v84 & 0x400) != 0;
    *(_DWORD *)v349 = (v84 & 0x800) != 0;
    v352 = 0;
    v351 = v385;
    v85 = v385[1].Blink;
    if ( LODWORD(v385[14].Blink) <= dword_1C013689C
      && v385[1].Blink != (struct _LIST_ENTRY *)&v385[1].Blink
      && v385[1].Blink->Flink != (struct _LIST_ENTRY *)&v385[1].Blink )
    {
      v385[2].Flink = v385[1].Blink;
      v246 = v385[1].Blink->Flink;
      v247 = v385[1].Blink;
      if ( v385[1].Blink->Flink != (struct _LIST_ENTRY *)&v385[1].Blink )
      {
        v248 = v385[1].Blink;
        do
        {
          v249 = v246;
          if ( (char *)v247[-3].Flink - (char *)v246[-3].Flink > 0 )
          {
            v248->Blink = v246;
            v248 = v246;
            v247->Flink = 0;
          }
          v246 = v246->Flink;
          v247 = v249;
        }
        while ( v246 != (struct _LIST_ENTRY *)&v385[1].Blink );
        if ( v385[2].Flink != v248 )
        {
          v249->Flink = 0;
          v248->Blink = 0;
          for ( mm = v385[2].Flink; v385[2].Flink->Blink; mm = v385[2].Flink )
          {
            p_Flink = &v385[1].Blink;
            do
            {
              v252 = mm->Blink;
              v253 = v252->Blink;
              if ( (char *)mm[-3].Flink - (char *)v252[-3].Flink <= 0 )
              {
                v254 = mm;
                mm = mm->Flink;
              }
              else
              {
                v254 = mm->Blink;
                v252 = v252->Flink;
              }
              v255 = v254;
              v256 = mm == 0;
              if ( mm )
              {
                do
                {
                  if ( !v252 )
                    break;
                  if ( (char *)mm[-3].Flink - (char *)v252[-3].Flink <= 0 )
                  {
                    v255->Flink = mm;
                    v255 = mm;
                    mm = mm->Flink;
                  }
                  else
                  {
                    v255->Flink = v252;
                    v255 = v252;
                    v252 = v252->Flink;
                  }
                }
                while ( mm );
                v256 = mm == 0;
              }
              if ( v256 )
                mm = v252;
              v255->Flink = mm;
              mm = v253;
              p_Flink[1] = v254;
              p_Flink = &v254->Flink;
              v254->Blink = v253;
            }
            while ( v253 && v253->Blink );
          }
          v385[1].Blink = mm;
          for ( nn = (struct _LIST_ENTRY *)&v385[1].Blink; mm; mm = mm->Flink )
          {
            mm->Blink = nn;
            nn = mm;
          }
          nn->Flink = (struct _LIST_ENTRY *)&v385[1].Blink;
          v385[2].Flink = nn;
          v85 = v385[1].Blink;
          goto LABEL_109;
        }
        v85 = v385[1].Blink;
      }
      v385[2].Flink = v247;
    }
LABEL_109:
    v385[12].Flink = v85;
    v385[13].Blink = v85;
    LODWORD(v385[13].Flink) = 0;
    if ( LODWORD(v385[14].Blink) )
    {
      if ( (HIDWORD(v385[0].Flink[194].Blink) & 0x400000) == 0 )
      {
        if ( v347 )
        {
          v284 = (CmsTransactionContext *)CmsLookasides::Allocate(4944, 1, 2);
          v285 = v284 ? CmsTransactionContext::CmsTransactionContext(v284, (struct CmsVolume *)v385[0].Flink) : 0LL;
          v329 = 0;
          if ( v285 )
          {
            if ( v348 )
              *((_QWORD *)v285 + 2) |= 0x20000C00uLL;
            if ( v349[0] )
              *((_QWORD *)v285 + 2) |= 0x20000800uLL;
            v286 = CmsBPlusTable::WriteBindableUpdate(v285, (struct SmsWritePlan *)v385, 0, 0, &v329);
            v287 = (int)v391[12];
            if ( v286 < 0 )
              v287 = v286;
            BYTE4(v391[9]) |= v329;
            LODWORD(v391[12]) = v287;
            CmsTransactionContext::Commit(v285, 0, 0, 0);
            CmsReferenced::Release(v285);
          }
        }
      }
    }
    KeSetEvent(p_Event, 0, 0);
    if ( v347 )
      ExFreePoolWithTag(&p_Event, 0);
    goto LABEL_112;
  }
  v281[8] = 1;
  *((_DWORD *)v281 + 6) = 0;
  *(_QWORD *)v281 = &Event;
  *((_QWORD *)v281 + 2) = v385;
  v281[9] = (*((_DWORD *)v34 + 4) & 0x400LL) != 0;
  v281[10] = (*((_DWORD *)v34 + 4) & 0x800LL) != 0;
  if ( !MsInitializeAndTryQueueWorkItem(
          (struct _MS_WORK_QUEUE_ITEM *)(v281 + 32),
          (void (*)(void *))SortWritePlanWorker,
          v281,
          v282) )
  {
    ExFreePoolWithTag(v283, 0);
    goto LABEL_107;
  }
LABEL_112:
  v86 = v334;
  CmsBPlusTable::PrepareBoundSetUpdate(
    v34,
    v334,
    (struct _SmsBindable *)v39,
    (struct _SmsDirtyTableEntries *)P,
    (struct SmsWritePlan *)v385);
  *((_QWORD *)v34 + 2) &= ~0x1000uLL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDDD(WPP_GLOBAL_Control->AttachedDevice, v87, v88, v86, v385[14].Blink, HIDWORD(v391[8]), v391[9]);
  }
  KeInitializeEvent((PRKEVENT)&v385[9].Blink, NotificationEvent, 0);
  v89 = (struct _LIST_ENTRY *)IoGetActivityIdThread();
  if ( v89 && KeGetCurrentIrql() < 2u )
    *(struct _LIST_ENTRY *)&v385[5].Blink = *v89;
  else
    *(_OWORD *)&v385[5].Blink = 0;
  v385[6].Blink = 0;
  v385[8].Blink = (struct _LIST_ENTRY *)CmsBPlusTable::DiscardPagesWorker;
  v385[9].Flink = v385;
  v385[7].Blink = (struct _LIST_ENTRY *)MspWorkerRoutine;
  v385[8].Flink = (struct _LIST_ENTRY *)&v385[5].Blink;
  if ( !(unsigned __int8)ExTryQueueWorkItem(&v385[6].Blink, 0) )
    KeSetEvent((PRKEVENT)&v385[9].Blink, 0, 0);
  KeInitializeEvent(&Object, NotificationEvent, 0);
  if ( HIDWORD(v385[14].Blink) < 0x64
    || (v288 = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x60u, 0x6950534Du), (v290 = v288) == 0) )
  {
LABEL_120:
    *(_DWORD *)&v357[1] = 0;
    p_Object = &Object;
    v90 = *((_QWORD *)v34 + 2);
    v358 = 0;
    v361 = 0;
    v355 = 0;
    v356 = (v90 & 0x400) != 0;
    *(_DWORD *)v357 = (v90 & 0x800) != 0;
    v360 = 1;
    v359 = v385;
    v91 = v385[2].Blink;
    if ( HIDWORD(v385[14].Blink) <= dword_1C013689C )
    {
      v339 = 0;
      if ( v385[2].Blink != (struct _LIST_ENTRY *)&v385[2].Blink
        && v385[2].Blink->Flink != (struct _LIST_ENTRY *)&v385[2].Blink )
      {
        v385[3].Flink = v385[2].Blink;
        v162 = v385[2].Blink->Flink;
        v163 = v385[2].Blink;
        if ( v385[2].Blink->Flink != (struct _LIST_ENTRY *)&v385[2].Blink )
        {
          v164 = v385[2].Blink;
          do
          {
            v165 = v162;
            if ( (char *)v163[-3].Flink - (char *)v162[-3].Flink > 0 )
            {
              v164->Blink = v162;
              v164 = v162;
              v163->Flink = 0;
            }
            v162 = v162->Flink;
            v163 = v165;
          }
          while ( v162 != (struct _LIST_ENTRY *)&v385[2].Blink );
          if ( v385[3].Flink != v164 )
          {
            v165->Flink = 0;
            v164->Blink = 0;
            for ( i1 = v385[3].Flink; v385[3].Flink->Blink; i1 = v385[3].Flink )
            {
              v167 = &v385[3];
              do
              {
                v168 = MergeSortedLists_0__lambda_0d187bcbc206ca3786012504b4cf4a2d_(i1, i1->Blink, v163);
                v167->Flink = (struct _LIST_ENTRY *)v168;
                *(_QWORD *)(v168 + 8) = v169;
                v167 = (struct _LIST_ENTRY *)(v168 + 8);
                i1 = v169;
              }
              while ( v169 && v169->Blink );
            }
            v385[2].Blink = i1;
            for ( i2 = (struct _LIST_ENTRY *)&v385[2].Blink; i1; i1 = i1->Flink )
            {
              i1->Blink = i2;
              i2 = i1;
            }
            i2->Flink = (struct _LIST_ENTRY *)&v385[2].Blink;
            v91 = v385[2].Blink;
            v385[3].Flink = i2;
            goto LABEL_122;
          }
          v91 = v385[2].Blink;
        }
        v385[3].Flink = v163;
      }
    }
LABEL_122:
    v385[12].Blink = v91;
    v385[14].Flink = v91;
    HIDWORD(v385[13].Flink) = 0;
    if ( HIDWORD(v385[14].Blink) )
    {
      if ( (HIDWORD(v385[0].Flink[194].Blink) & 0x400000) == 0 )
      {
        if ( v355 )
        {
          v291 = (CmsTransactionContext *)CmsLookasides::Allocate(4944, 1, 2);
          v292 = v291 ? CmsTransactionContext::CmsTransactionContext(v291, (struct CmsVolume *)v385[0].Flink) : 0LL;
          v330[0] = 0;
          if ( v292 )
          {
            if ( v356 )
              *((_QWORD *)v292 + 2) |= 0x20000C00uLL;
            if ( v357[0] )
              *((_QWORD *)v292 + 2) |= 0x20000800uLL;
            v293 = CmsBPlusTable::WriteBindableUpdate(v292, (struct SmsWritePlan *)v385, 1u, 1u, v330);
            v294 = (int)v391[12];
            if ( v293 < 0 )
              v294 = v293;
            BYTE4(v391[9]) |= v330[0];
            LODWORD(v391[12]) = v294;
            CmsTransactionContext::Commit(v292, 0, 0, 0);
            CmsReferenced::Release(v292);
          }
        }
      }
    }
    KeSetEvent(p_Object, 0, 0);
    if ( v355 )
      ExFreePoolWithTag(&p_Object, 0);
    goto LABEL_125;
  }
  v288[8] = 1;
  *((_DWORD *)v288 + 6) = 1;
  *(_QWORD *)v288 = &Object;
  *((_QWORD *)v288 + 2) = v385;
  v288[9] = (*((_DWORD *)v34 + 4) & 0x400LL) != 0;
  v288[10] = (*((_DWORD *)v34 + 4) & 0x800LL) != 0;
  if ( !MsInitializeAndTryQueueWorkItem(
          (struct _MS_WORK_QUEUE_ITEM *)(v288 + 32),
          (void (*)(void *))SortWritePlanWorker,
          v288,
          v289) )
  {
    ExFreePoolWithTag(v290, 0);
    goto LABEL_120;
  }
LABEL_125:
  if ( (*((_DWORD *)v34 + 4) & 0x400LL) == 0
    && *((_BYTE *)v51 + 3113)
    && (*((_DWORD *)v51 + 779) & 0x20000000) == 0
    && (v336 & 3) != 2 )
  {
    v235 = &v39[11].Blink;
    while ( 1 )
    {
      v236 = v235[73];
      v237 = (CmsBPlusTable **)(v235 - 23);
      v235 = (struct _LIST_ENTRY **)*v235;
      if ( v236 )
      {
        _InterlockedExchangeAdd64((volatile signed __int64 *)v51 + 418, -(__int64)v236);
        ExAcquireAutoExpandPushLockExclusive(*((_QWORD *)v51 + 428), 0);
        CmsVolume::RemoveReservationForGlobalStreamReserve(v51, (__int64)v237[96]);
        ExReleaseAutoExpandPushLockExclusive(*((_QWORD *)v51 + 428), 0);
        v237[96] = 0;
      }
      if ( !v237[93] )
        goto LABEL_463;
      v295 = (CmsBlockRefcount *)(v237 + 97);
      if ( (*((_DWORD *)v34 + 4) & 0x400LL) != 0 )
        break;
      if ( CmsBlockRefcount::ProcessDeleteQueue(
             v295,
             v34,
             (struct CmsContainerRangeMap *)(v237 + 88),
             (struct CmsContainerRangeMap *)(v237 + 97)) >= 0 )
        goto LABEL_654;
      CmsBPlusTable::EnqueueTreeUpdate(*v237, v34, 12);
LABEL_655:
      CmsTransactionContext::Commit(v34, 0, 0, 0);
      v51 = v331;
LABEL_463:
      v238 = *v237;
      if ( (*((_DWORD *)*v237 + 4) & 0x20000) == 0 || CmsVolume::TableIsIntegrityState(v51, v238) )
      {
        v239 = *(_BYTE *)(*((_QWORD *)v238 + 5) + 84LL);
        if ( v239 == 4 )
          v240 = (CmsAllocator *)*((_QWORD *)v51 + 379);
        else
          v240 = (CmsAllocator *)(v239 == 1 ? *((_QWORD *)v51 + 380) : *((_QWORD *)v51 + 378));
        if ( v237[102] )
        {
          CmsAllocator::MergeIntoProcessedDeleteQueue(
            v240,
            v238,
            (struct CmsContainerRangeMap *)(v237 + 97),
            (__int64)v237[105]);
          v237[105] = 0;
        }
      }
      if ( v235 == p_Blink )
        goto LABEL_129;
    }
    CmsContainerRangeMap::Merge(v295, (struct CmsContainerRangeMap *)(v237 + 88));
LABEL_654:
    CmsContainerRangeMap::DeleteAll((CmsContainerRangeMap *)(v237 + 88));
    goto LABEL_655;
  }
LABEL_129:
  KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
  KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  if ( (*((_DWORD *)v34 + 4) & 0x400LL) == 0 )
    _InterlockedIncrement64((volatile signed __int64 *)v51 + 232);
  v92 = *((_DWORD *)v51 + 779) & 0x20000000;
  v93 = 0;
  while ( 1 )
  {
    v94 = CmsBPlusTable::WriteBindableUpdate(v34, (struct SmsWritePlan *)v385, v93, 1u, v364);
    if ( v94 < 0 )
      break;
    if ( ++v93 >= 2 )
    {
      if ( SLODWORD(v391[12]) < 0 )
        v94 = (int)v391[12];
      break;
    }
    v34 = v333;
  }
  if ( v364 )
    *v364 |= BYTE4(v391[9]);
  if ( v94 < 0 )
  {
    v296 = v333;
LABEL_664:
    if ( !v92 && (*((_DWORD *)v51 + 779) & 0x20000000) == 0 )
      CmsBPlusTable::TryEnqueueWriteFailuresForRetry(v296, (struct SmsWritePlan *)v385);
  }
  else if ( v92 )
  {
    if ( v363 )
    {
      v296 = v333;
      if ( (*((_DWORD *)v333 + 4) & 0x400LL) == 0 )
      {
        v94 = -1073741202;
        goto LABEL_664;
      }
    }
  }
  KeWaitForSingleObject(&v385[9].Blink, Executive, 0, 0, 0);
  v95 = -1;
  while ( 1 )
  {
    v96 = v385[11].Flink;
    v97 = v95;
    if ( v385[11].Flink == &v385[11] )
      break;
    if ( !v95-- )
      break;
    CmsBPlusTable::TryCombinedPageClean(v333, (struct SmsPage *)&v385[11].Flink[-6].Blink, v97, &v385[11]);
    v298 = v96->Flink;
    if ( v96->Flink->Blink != v96 )
      goto LABEL_677;
    v299 = v96->Blink;
    if ( v299->Flink != v96 )
      goto LABEL_677;
    v299->Flink = v298;
    v298->Blink = v299;
    v96->Blink = 0;
    v96->Flink = 0;
    if ( (_BYTE)KdDebuggerEnabled && ((__int64)v96[20].Flink & 0x20000000) != 0 )
      __debugbreak();
    _InterlockedAnd64((volatile signed __int64 *)&v96[20], 0xFFFFFFFFDFE7FFBFuLL);
    CmsBPlusTable::DiscardPage((CmsBPlusTable *)v96[2].Flink, v333, (struct SmsPage *)&v96[-6].Blink);
  }
  if ( Resource )
    ExReleaseResourceLite(Resource);
  for ( i3 = 0; i3 < 2; ++i3 )
  {
    while ( 1 )
    {
      v99 = (struct _LIST_ENTRY *)&v385[i3 + 1].Blink;
      v100 = v99->Flink;
      if ( v99->Flink == v99 )
        break;
      v157 = v333;
      v337 = (struct SmsPage *)&v100[-6].Blink;
      CmsBPlusTable::TryCombinedPageClean(v333, (struct SmsPage *)&v100[-6].Blink, 0xAu, v99);
      v159 = (struct SmsPage **)*((_QWORD *)v337 + 11);
      if ( v159[1] != (struct SmsPage *)((char *)v337 + 88) )
        goto LABEL_677;
      v160 = (struct SmsPage **)*((_QWORD *)v337 + 12);
      if ( *v160 != (struct SmsPage *)((char *)v337 + 88) )
        goto LABEL_677;
      *v160 = (struct SmsPage *)v159;
      v159[1] = (struct SmsPage *)v160;
      *((_QWORD *)v337 + 11) = 0;
      *((_QWORD *)v337 + 12) = 0;
      if ( (_BYTE)KdDebuggerEnabled
        && (*((_QWORD *)v337 + 51) & 0x80000LL) != 0
        && (*((_QWORD *)v337 + 51) & 0x40000LL) == 0 )
      {
        __debugbreak();
      }
      _InterlockedAnd64((volatile signed __int64 *)v337 + 51, 0x5FF3FFAFu);
      if ( (*((_QWORD *)v337 + 51) & 0x4000000LL) != 0 )
      {
        v161 = *((_QWORD *)v157 + 4);
        if ( (*(_DWORD *)(v161 + 3116) & 0x2000) == 0 )
          CmsVolumeContainer::SetContainerStationaryVolatile(
            *(CmsVolumeContainer **)(v161 + 3048),
            v157,
            (struct SmsPage *)((char *)v337 + 8),
            0,
            0);
        _InterlockedAnd64((volatile signed __int64 *)v337 + 51, 0xFFFFFFFFFBFFFFFFuLL);
      }
      CmsBPlusTable::SetPageDirtyGeneration(v157, v337, v158);
      (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct SmsPage **, __int64))(**(_QWORD **)(*((_QWORD *)v337 + 15) + 96LL)
                                                                                                 + 72LL))(
        *(_QWORD *)(*((_QWORD *)v337 + 15) + 96LL),
        v157,
        &v337,
        10);
    }
  }
  if ( v341 )
  {
    if ( (v336 & 8) != 0 && *v364 )
    {
      v101 = v333;
    }
    else
    {
      v101 = v333;
      if ( (v336 & 4) != 0 )
      {
        CmsBPlusTable::PurgeTablesInDirtyTableList(v333, (struct _SmsDirtyTableEntries *)P);
        CmsBPlusTable::PurgeTablesInBoundSet(v101, (struct _SmsBindable *)v39);
      }
      else
      {
        CmsBPlusTable::PurgeOneTable(v333, v334);
      }
    }
    CmsTransactionContext::Commit(v101, 0, 0, 0);
    v362 = KeQueryPerformanceCounter(0);
    CmsBPlusTable::UnbindBoundTrees(v101, (struct _SmsBindable *)v39);
  }
  else
  {
    v101 = v333;
  }
  v102 = v331;
  if ( (*((_DWORD *)v101 + 4) & 0x400LL) == 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v331 + 215);
    _InterlockedIncrement((volatile signed __int32 *)v102 + 212);
    _InterlockedExchangeAdd(
      (volatile signed __int32 *)v102 + 211,
      10000000 * (v362.QuadPart - PerformanceCounter.QuadPart) / PerformanceFrequency.QuadPart);
  }
  v103 = v380;
  do
  {
    v104 = *p_Blink;
    v105 = (CmsReferenced **)&(*p_Blink)[-12].Blink;
    if ( v105 != (CmsReferenced **)v39 )
    {
      v155 = v104->Flink;
      if ( v104->Flink->Blink != v104 )
        goto LABEL_677;
      v156 = v104->Blink;
      if ( v156->Flink != v104 )
        goto LABEL_677;
      v156->Flink = v155;
      v155->Blink = v156;
      v104->Blink = v104;
      v104->Flink = v104;
    }
    ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)*v105 + 10) + 8LL));
    if ( v103 != v40 )
      CmsReferenced::Release(*v105);
  }
  while ( v105 != (CmsReferenced **)v39 );
  v9 = v333;
  v106 = P;
  v107 = v342;
  *((_QWORD *)v333 + 2) &= ~0x20000000uLL;
  if ( v106 )
  {
    v108 = (KSPIN_LOCK *)((char *)v102 + 3536);
    v109 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v102 + 442);
    if ( (*((_DWORD *)v9 + 4) & 0x400LL) != 0 )
      goto LABEL_160;
    v11 = v331;
    if ( *((_BYTE *)v331 + 3593) || v107 <= 0 )
      goto LABEL_160;
    v192 = v107 + *((_DWORD *)v331 + 899) + 255;
    v193 = (BYTE4(v192) + (int)v192) >> 8;
    if ( v193 >= 8 )
      v193 = 8;
    v194 = *((_DWORD *)v331 + 890);
    if ( v193 > v194 )
    {
      v195 = 0;
      v196 = v193 - v194;
      if ( v196 )
      {
        do
        {
          v197 = (struct _MS_WORK_QUEUE_ITEM *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x48u, 0x6950534Du);
          if ( !v197 )
            break;
          ++*((_DWORD *)v11 + 890);
          _InterlockedIncrement((volatile signed __int32 *)v11 + 2);
          *((_QWORD *)v197 + 8) = v11;
          MsInitializeAndQueueWorkItem(
            v197,
            (void (*)(void *))MspCleanupDirtyTableListWorkerFn,
            v197,
            CriticalWorkQueue);
          ++v195;
        }
        while ( v195 < v196 );
      }
      v106 = P;
    }
    if ( *((_DWORD *)v11 + 890) )
    {
      KeClearEvent((PRKEVENT)((char *)v11 + 3568));
      if ( *((_QWORD *)v11 + 443) )
        **((_QWORD **)v11 + 444) = v106;
      else
        *((_QWORD *)v11 + 443) = v106;
      *((_QWORD *)v11 + 444) = v332;
      _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 899, v107);
      *((_BYTE *)v11 + 3592) = 0;
      KeReleaseSpinLock(v108, v109);
      v9 = v333;
    }
    else
    {
      v9 = v333;
LABEL_160:
      KeReleaseSpinLock(v108, v109);
      v110 = v106;
      do
      {
        v111 = 0;
        v112 = v110 + 1;
        do
        {
          if ( *v112 )
          {
            v113 = (__int64)&v110[8 * v111 + 1 + (unsigned int)v111];
            goto LABEL_164;
          }
          v111 = (unsigned int)(v111 + 1);
          v112 += 9;
        }
        while ( (unsigned int)v111 < 8 );
        v110 = (_QWORD *)*v110;
      }
      while ( v110 );
      v113 = 0;
      LODWORD(v111) = -1;
LABEL_164:
      while ( v113 )
      {
        v114 = *(_QWORD *)(v113 + 8);
        v115 = *(volatile signed __int32 **)v113;
        if ( v114 )
        {
          ((void (__fastcall *)(__int64, _QWORD))qword_1C0136A40)(v114, 0);
          if ( *(_BYTE *)(v113 + 16) )
            ((void (__fastcall *)(_QWORD, _QWORD))qword_1C0136A40)(*(_QWORD *)(v113 + 8), 0);
        }
        if ( (*(_DWORD *)(v113 + 20) & 2) != 0 )
          (*(void (__fastcall **)(volatile signed __int32 *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v115 + 8LL))(
            v115,
            0,
            0,
            0,
            0);
        if ( _InterlockedExchangeAdd(v115 + 2, 0xFFFFFFFF) == 1 && v115 )
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v115)(v115, 1);
        v116 = (_QWORD *)(v113 - (72 * (int)v111 + 8));
        if ( !v116 )
          break;
        while ( 1 )
        {
          v111 = (unsigned int)(v111 + 1);
          if ( (unsigned int)v111 < 8 )
            break;
LABEL_174:
          v116 = (_QWORD *)*v116;
          LODWORD(v111) = -1;
          if ( !v116 )
            goto LABEL_175;
        }
        v117 = &v116[8 * v111 + 1 + (unsigned int)v111];
        while ( !*v117 )
        {
          v111 = (unsigned int)(v111 + 1);
          v117 += 9;
          if ( (unsigned int)v111 >= 8 )
            goto LABEL_174;
        }
        v113 = (__int64)&v116[9 * v111 + 1];
      }
LABEL_175:
      v118 = v331;
      do
      {
        v119 = v106;
        v106 = (_QWORD *)*v106;
        if ( *((_DWORD *)v118 + 25) && (v148 = *((_DWORD *)v118 + 24), v149 = 0, v148) )
        {
          while ( 1 )
          {
            v150 = v149;
            if ( *(void **)(*((_QWORD *)v118 + 11) + 16LL * v149) == v119 )
              break;
            if ( ++v149 >= v148 )
              goto LABEL_177;
          }
          if ( *((_BYTE *)v118 + 144) )
            ExAcquirePushLockExclusiveEx((char *)v118 + 136, 0);
          v151 = *((_QWORD *)v118 + 11) + 16 * v150;
          do
            v152 = *(_DWORD *)(v151 + 8);
          while ( v152 != _InterlockedCompareExchange((volatile signed __int32 *)(v151 + 8), v152 & 0xFFFFFFFE, v152) );
          _InterlockedDecrement((volatile signed __int32 *)v118 + 25);
          if ( *((_BYTE *)v118 + 144) )
          {
            KeSetEvent((PRKEVENT)((char *)v118 + 112), 0, 0);
            ExReleasePushLockEx((char *)v118 + 136, 0);
          }
        }
        else
        {
LABEL_177:
          ExFreePoolWithTag(v119, 0);
        }
      }
      while ( v106 );
      v11 = v118;
    }
  }
  else
  {
    v11 = v331;
  }
LABEL_180:
  v43 = v334;
LABEL_181:
  *((_QWORD *)v9 + 2) &= 0xFFFFFFFFDFFFF7FFuLL;
  if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    LOBYTE(v300) = 0;
    v301 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v43) + 10);
    if ( v301 )
      v300 = *(_QWORD *)(v301 + 384);
    LOBYTE(v302) = 0;
    v303 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v43) + 10);
    if ( v303 )
      v302 = *(_QWORD *)(v303 + 376);
    v304 = (int)v391[10];
    v305 = IoGetActivityIdThread();
    McTemplateK0qii_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)TableTreeUpdateEnd,
      v305,
      v304,
      v302,
      v300);
    if ( dword_1C012D0B4 == 1 )
    {
      v306 = v334;
      if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
      {
        LOBYTE(v307) = 0;
        v308 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v334) + 10);
        if ( v308 )
          v307 = *(_QWORD *)(v308 + 384);
        v309 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v306) + 10);
        if ( v309 )
          v310 = *(_QWORD *)(v309 + 376);
        else
          LOBYTE(v310) = 0;
        v311 = HIDWORD(v391[10]);
        v312 = IoGetActivityIdThread();
        McTemplateK0qii_EtwWriteTransfer(
          (unsigned int)MinstoreEventProvider_Context,
          (unsigned int)TableTreeUpdateEnd,
          v312,
          v311,
          v310,
          v307);
      }
    }
  }
  v120 = v391[1];
  if ( v391[1] )
  {
    v344 = 0;
    v121 = 0;
    v366 = 0;
    v122 = 0;
    v375 = 0;
    v123 = 0;
    v365 = 0;
    v374 = 0;
    if ( *((_BYTE *)v391[1] + 62) )
    {
      while ( 1 )
      {
        if ( v121 == 1 )
        {
          v313 = CmsHashTableLite::EnumerateNext<0>((_DWORD)v120, 0, -1, (unsigned int)&v365, 1);
        }
        else
        {
          v121 = 1;
          if ( !(*((_DWORD *)v120 + 5) + *((_DWORD *)v120 + 9)) )
            break;
          *((_QWORD *)&v365 + 1) = 0;
          v366 = 0;
          v313 = CmsHashTableLite::PinNextInIndex<0>((_DWORD)v120, 1, (unsigned int)&v365, 0, -1);
        }
        if ( v313 )
          break;
        v122 = (_QWORD *)v365;
        v314 = *(_QWORD **)(v365 + 24);
        while ( v314 )
        {
          v315 = v314;
          v314 = (_QWORD *)*v314;
          CmsLookasides::Free(v315);
        }
        v122[3] = 0;
        v122[4] = 0;
        v122[5] = 0;
        if ( (_QWORD)v374 )
        {
          CmsHashTableLite::DeleteFromIndex<0>(v120, v123, &v344, &v374);
          CmsLookasides::Free(v344);
        }
        v123 = v122[2];
        v374 = v365;
        v375 = v366;
      }
      if ( (_QWORD)v374 )
      {
        CmsHashTableLite::DeleteFromIndex<0>(v120, v122[2], &v344, &v374);
        CmsLookasides::Free(v344);
      }
      v256 = *((_BYTE *)v120 + 61) == 0;
      *((_QWORD *)v120 + 5) = 0;
      if ( !v256 )
        CmsContainerRangeMap::UninitializeMap(v120);
    }
  }
  v124 = v391[2];
  if ( v391[2] )
  {
    v345 = 0;
    v125 = 0;
    v368 = 0;
    v126 = 0;
    v377 = 0;
    v127 = 0;
    v367 = 0;
    v376 = 0;
    if ( *((_BYTE *)v391[2] + 62) )
    {
      while ( 1 )
      {
        if ( v125 == 1 )
        {
          v316 = CmsHashTableLite::EnumerateNext<0>((_DWORD)v124, 0, -1, (unsigned int)&v367, 1);
        }
        else
        {
          v125 = 1;
          if ( !(*((_DWORD *)v124 + 5) + *((_DWORD *)v124 + 9)) )
            break;
          *((_QWORD *)&v367 + 1) = 0;
          v368 = 0;
          v316 = CmsHashTableLite::PinNextInIndex<0>((_DWORD)v124, 1, (unsigned int)&v367, 0, -1);
        }
        if ( v316 )
          break;
        v126 = (_QWORD *)v367;
        v317 = *(_QWORD **)(v367 + 24);
        while ( v317 )
        {
          v318 = v317;
          v317 = (_QWORD *)*v317;
          CmsLookasides::Free(v318);
        }
        v126[3] = 0;
        v126[4] = 0;
        v126[5] = 0;
        if ( (_QWORD)v376 )
        {
          CmsHashTableLite::DeleteFromIndex<0>(v124, v127, &v345, &v376);
          CmsLookasides::Free(v345);
        }
        v127 = v126[2];
        v376 = v367;
        v377 = v368;
      }
      if ( (_QWORD)v376 )
      {
        CmsHashTableLite::DeleteFromIndex<0>(v124, v126[2], &v345, &v376);
        CmsLookasides::Free(v345);
      }
      v256 = *((_BYTE *)v124 + 61) == 0;
      *((_QWORD *)v124 + 5) = 0;
      if ( !v256 )
        CmsContainerRangeMap::UninitializeMap(v124);
    }
  }
  v128 = v391[3];
  if ( v391[3] )
  {
    v343 = 0;
    v129 = 0;
    v370 = 0;
    v130 = 0;
    v379 = 0;
    v131 = 0;
    v369 = 0;
    v378 = 0;
    if ( *((_BYTE *)v391[3] + 62) )
    {
      while ( 1 )
      {
        if ( v129 == 1 )
        {
          v319 = CmsHashTableLite::EnumerateNext<0>((_DWORD)v128, 0, -1, (unsigned int)&v369, 1);
        }
        else
        {
          v129 = 1;
          if ( !(*((_DWORD *)v128 + 5) + *((_DWORD *)v128 + 9)) )
            break;
          *((_QWORD *)&v369 + 1) = 0;
          v370 = 0;
          v319 = CmsHashTableLite::PinNextInIndex<0>((_DWORD)v128, 1, (unsigned int)&v369, 0, -1);
        }
        if ( v319 )
          break;
        v130 = (_QWORD *)v369;
        v320 = *(_QWORD **)(v369 + 24);
        while ( v320 )
        {
          v321 = v320;
          v320 = (_QWORD *)*v320;
          CmsLookasides::Free(v321);
        }
        v130[3] = 0;
        v130[4] = 0;
        v130[5] = 0;
        if ( (_QWORD)v378 )
        {
          CmsHashTableLite::DeleteFromIndex<0>(v128, v131, &v343, &v378);
          CmsLookasides::Free(v343);
        }
        v131 = v130[2];
        v378 = v369;
        v379 = v370;
      }
      if ( (_QWORD)v378 )
      {
        CmsHashTableLite::DeleteFromIndex<0>(v128, v130[2], &v343, &v378);
        CmsLookasides::Free(v343);
      }
      v256 = *((_BYTE *)v128 + 61) == 0;
      *((_QWORD *)v128 + 5) = 0;
      if ( !v256 )
        CmsContainerRangeMap::UninitializeMap(v128);
    }
  }
  v132 = v389[0];
  while ( v132 )
  {
    v322 = v132;
    v132 = (PVOID)*((_QWORD *)v132 + 6);
    CmsTxMemLog::FreeRedoBlock(v322);
  }
  v133 = v387;
  *(_OWORD *)v389 = 0;
  v386 = 0;
  while ( v133 )
  {
    v323 = v133;
    v133 = (PVOID)*((_QWORD *)v133 + 6);
    CmsTxMemLog::FreeRedoBlock(v323);
  }
  v387 = 0;
  _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 724, -v388);
  v134 = v391[7];
  v388 = 0;
  v390 = 0;
  if ( v391[7] )
  {
    do
    {
      v258 = *(struct _SmsCheckpointContext **)v134;
      ExFreePoolWithTag(v134, 0);
      v134 = v258;
    }
    while ( v258 );
  }
  _InterlockedExchangeAdd((volatile signed __int32 *)(qword_1C0136F98 + 88), -LODWORD(v385[15].Flink));
  v13 = (unsigned int)_InterlockedExchangeAdd(
                        (volatile signed __int32 *)(qword_1C0136FA0 + 88),
                        -HIDWORD(v385[15].Flink));
LABEL_210:
  v135 = v393[0];
  if ( !v393[0] )
    goto LABEL_217;
  v136 = *((_QWORD *)v393[0] - 1);
  v137 = (struct _SLIST_ENTRY *)((char *)v393[0] - 8);
  if ( !v136 )
  {
LABEL_733:
    ExFreePoolWithTag((char *)v393[0] - 8, 0);
    goto LABEL_216;
  }
  if ( !*(_BYTE *)(v136 + 8) )
  {
    v324 = *(_DWORD *)(v136 + 80);
    if ( v324 < *(_DWORD *)(v136 + 84) || *(_DWORD *)(v136 + 88) >= v324 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v136 + 64), v137);
      _InterlockedIncrement((volatile signed __int32 *)(v136 + 80));
      goto LABEL_216;
    }
    goto LABEL_733;
  }
  v138 = (struct _NPAGED_LOOKASIDE_LIST *)(v136 + 64);
  if ( *(_BYTE *)(v136 + 9) )
  {
    ++*(_DWORD *)(v136 + 92);
    if ( ExQueryDepthSList(&v138->L.ListHead) >= *(_WORD *)(v136 + 80) )
    {
      ++*(_DWORD *)(v136 + 96);
      (*(void (__fastcall **)(struct _SLIST_ENTRY *))(v136 + 120))(v137);
    }
    else
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v136 + 64), v137);
    }
  }
  else
  {
    ExFreeToNPagedLookasideList(v138, v137);
  }
LABEL_216:
  v135 = 0;
  LODWORD(v393[1]) = -1;
  v393[0] = 0;
LABEL_217:
  if ( v392 )
  {
    ExFreeAutoExpandPushLock(v392, v13);
    v135 = v393[0];
    v392 = 0;
  }
  if ( v135 )
  {
    CmsLookasides::Free(v135);
    v393[0] = 0;
    LODWORD(v393[1]) = -1;
  }
  if ( v392 )
  {
    ExFreeAutoExpandPushLock(v392, v13);
    v392 = 0;
  }
  v139 = v401[0];
  if ( !v401[0] )
    goto LABEL_230;
  v140 = *((_QWORD *)v401[0] - 1);
  v141 = (struct _SLIST_ENTRY *)((char *)v401[0] - 8);
  if ( !v140 )
  {
LABEL_739:
    ExFreePoolWithTag((char *)v401[0] - 8, 0);
    goto LABEL_229;
  }
  if ( !*(_BYTE *)(v140 + 8) )
  {
    v325 = *(_DWORD *)(v140 + 80);
    if ( v325 < *(_DWORD *)(v140 + 84) || *(_DWORD *)(v140 + 88) >= v325 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v140 + 64), v141);
      _InterlockedIncrement((volatile signed __int32 *)(v140 + 80));
      goto LABEL_229;
    }
    goto LABEL_739;
  }
  v142 = (struct _NPAGED_LOOKASIDE_LIST *)(v140 + 64);
  if ( *(_BYTE *)(v140 + 9) )
  {
    ++*(_DWORD *)(v140 + 92);
    if ( ExQueryDepthSList(&v142->L.ListHead) >= *(_WORD *)(v140 + 80) )
    {
      ++*(_DWORD *)(v140 + 96);
      (*(void (__fastcall **)(struct _SLIST_ENTRY *))(v140 + 120))(v141);
    }
    else
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v140 + 64), v141);
    }
  }
  else
  {
    ExFreeToNPagedLookasideList(v142, v141);
  }
LABEL_229:
  v139 = 0;
  LODWORD(v401[1]) = -1;
  v401[0] = 0;
LABEL_230:
  if ( v400 )
  {
    ExFreeAutoExpandPushLock(v400, v13);
    v139 = v401[0];
    v400 = 0;
  }
  if ( v139 )
  {
    CmsLookasides::Free(v139);
    v401[0] = 0;
    LODWORD(v401[1]) = -1;
  }
  if ( v400 )
  {
    ExFreeAutoExpandPushLock(v400, v13);
    v400 = 0;
  }
  v143 = v409[0];
  if ( !v409[0] )
    goto LABEL_243;
  v144 = *((_QWORD *)v409[0] - 1);
  v145 = (struct _SLIST_ENTRY *)((char *)v409[0] - 8);
  if ( !v144 )
  {
LABEL_745:
    ExFreePoolWithTag((char *)v409[0] - 8, 0);
    goto LABEL_242;
  }
  if ( !*(_BYTE *)(v144 + 8) )
  {
    v326 = *(_DWORD *)(v144 + 80);
    if ( v326 < *(_DWORD *)(v144 + 84) || *(_DWORD *)(v144 + 88) >= v326 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v144 + 64), v145);
      _InterlockedIncrement((volatile signed __int32 *)(v144 + 80));
      goto LABEL_242;
    }
    goto LABEL_745;
  }
  v146 = (struct _NPAGED_LOOKASIDE_LIST *)(v144 + 64);
  if ( *(_BYTE *)(v144 + 9) )
  {
    ++*(_DWORD *)(v144 + 92);
    if ( ExQueryDepthSList(&v146->L.ListHead) >= *(_WORD *)(v144 + 80) )
    {
      ++*(_DWORD *)(v144 + 96);
      (*(void (__fastcall **)(struct _SLIST_ENTRY *))(v144 + 120))(v145);
    }
    else
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v144 + 64), v145);
    }
  }
  else
  {
    ExFreeToNPagedLookasideList(v146, v145);
  }
LABEL_242:
  v143 = 0;
  LODWORD(v409[1]) = -1;
  v409[0] = 0;
LABEL_243:
  if ( AutoExpandPushLock )
  {
    ExFreeAutoExpandPushLock(AutoExpandPushLock, v13);
    v143 = v409[0];
    AutoExpandPushLock = 0;
  }
  if ( v143 )
  {
    CmsLookasides::Free(v143);
    v409[0] = 0;
    LODWORD(v409[1]) = -1;
  }
  if ( AutoExpandPushLock )
    ExFreeAutoExpandPushLock(AutoExpandPushLock, v13);
  return (unsigned int)v94;
}

```

## disassembly

```asm
0x1c001e400  mov     [rsp-8+arg_18], rbx
0x1c001e405  push    rbp
0x1c001e406  push    rsi
0x1c001e407  push    rdi
0x1c001e408  push    r12
0x1c001e40a  push    r13
0x1c001e40c  push    r14
0x1c001e40e  push    r15
0x1c001e410  lea     rbp, [rsp-3C0h]
0x1c001e418  sub     rsp, 4C0h
0x1c001e41f  mov     rax, cs:__security_cookie
0x1c001e426  xor     rax, rsp
0x1c001e429  mov     [rbp+3F0h+var_40], rax
0x1c001e430  mov     rax, [rdx+60h]
0x1c001e434  mov     r12, r8
0x1c001e437  mov     rbx, [rbp+3F0h+arg_20]
0x1c001e43e  mov     rsi, rdx
0x1c001e441  mov     [rsp+4F0h+var_490], rdx
0x1c001e446  mov     r15, rcx
0x1c001e449  mov     [rsp+4F0h+var_498], rcx
0x1c001e44e  xor     edi, edi
0x1c001e450  mov     r13, [rax+18h]
0x1c001e454  lea     rcx, [rbp+3F0h+var_2A0]; void *
0x1c001e45b  xor     edx, edx; Val
0x1c001e45d  mov     [rsp+4F0h+var_4A8], r13
0x1c001e462  mov     r8d, 100h; Size
0x1c001e468  mov     [rsp+4F0h+var_484], r9d
0x1c001e46d  mov     r14d, r9d
0x1c001e470  mov     [rbp+3F0h+var_3F0], rbx
0x1c001e474  mov     [rbp+3F0h+Resource], rdi
0x1c001e478  mov     [rsp+4F0h+P], rdi
0x1c001e47d  call    memset
0x1c001e482  xor     ecx, ecx
0x1c001e484  lea     r8d, [rdi+68h]; Size
0x1c001e488  xor     eax, eax
0x1c001e48a  mov     [rbp+3F0h+var_190], rcx
0x1c001e491  mov     [rbp+3F0h+var_188], ecx
0x1c001e497  xorps   xmm0, xmm0
0x1c001e49a  xorps   xmm1, xmm1
0x1c001e49d  movdqa  [rbp+3F0h+var_1A0], xmm0
0x1c001e4a5  lea     rcx, [rbp+3F0h+var_168]; void *
0x1c001e4ac  mov     [rbp+3F0h+var_170], rax
0x1c001e4b3  xor     edx, edx; Val
0x1c001e4b5  mov     [rbp+3F0h+var_104], eax
0x1c001e4bb  movups  xmmword ptr [rbp+3F0h+var_180], xmm1
0x1c001e4c2  call    memset
0x1c001e4c7  xor     ecx, ecx
0x1c001e4c9  xorps   xmm0, xmm0
0x1c001e4cc  xor     eax, eax
0x1c001e4ce  movaps  [rbp+3F0h+var_330], xmm0
0x1c001e4d5  mov     [rbp+3F0h+var_2E8], rax
0x1c001e4dc  mov     [rbp+3F0h+var_390], rax
0x1c001e4e0  mov     [rbp+3F0h+var_400], rax
0x1c001e4e4  mov     qword ptr [rbp+3F0h+PerformanceFrequency], rax
0x1c001e4e8  movups  xmmword ptr [rbp+3F0h+var_318.Header], xmm0
0x1c001e4ef  movups  xmmword ptr [rbp+3F0h+var_318.Header.WaitListHead.Blink], xmm0
0x1c001e4f6  movups  [rbp+3F0h+var_2F8], xmm0
0x1c001e4fd  movzx   eax, byte ptr [r13+4Ch]
0x1c001e502  inc     al
0x1c001e504  mov     [rbp+3F0h+var_80], rcx
0x1c001e50b  mov     [rbp+3F0h+var_44], al
0x1c001e511  movups  xmmword ptr [rbp+3F0h+var_78], xmm0
0x1c001e518  mov     [rbp+3F0h+var_48], 1F4h
0x1c001e522  movups  [rbp+3F0h+var_68], xmm0
0x1c001e529  mov     [rbp+3F0h+var_43], cx
0x1c001e530  mov     [rbp+3F0h+var_58], rcx
0x1c001e537  mov     [rbp+3F0h+var_50], rcx
0x1c001e53e  movzx   eax, byte ptr [r13+4Ch]
0x1c001e543  inc     al
0x1c001e545  mov     [rbp+3F0h+var_C0], rcx
0x1c001e54c  mov     [rbp+3F0h+var_84], al
0x1c001e552  mov     [rbp+3F0h+var_88], 1F4h
0x1c001e55c  mov     [rbp+3F0h+var_83], cx
0x1c001e563  mov     [rbp+3F0h+var_98], rcx
0x1c001e56a  mov     [rbp+3F0h+var_90], rcx
0x1c001e571  movups  xmmword ptr [rbp+3F0h+var_B8], xmm0
0x1c001e578  movups  [rbp+3F0h+var_A8], xmm0
0x1c001e57f  movzx   eax, byte ptr [r13+4Ch]
0x1c001e584  mov     [rbp+3F0h+var_C4], al
0x1c001e58a  mov     [rbp+3F0h+var_100], rcx
0x1c001e591  mov     [rbp+3F0h+var_C8], 1F4h
0x1c001e59b  mov     [rbp+3F0h+var_C3], cx
0x1c001e5a2  mov     [rbp+3F0h+var_D8], rcx
0x1c001e5a9  mov     [rbp+3F0h+var_D0], rcx
0x1c001e5b0  mov     [rbp+3F0h+var_45C], ecx
0x1c001e5b3  movups  xmmword ptr [rbp+3F0h+var_F8], xmm0
0x1c001e5ba  movups  [rbp+3F0h+var_E8], xmm0
0x1c001e5c1  test    r14d, r14d
0x1c001e5c4  jz      loc_1C00778DE
0x1c001e5ca  test    rbx, rbx
0x1c001e5cd  jnz     loc_1C001FD06
0x1c001e5d3  test    r12, r12
0x1c001e5d6  jnz     short loc_1C001E5E7
0x1c001e5d8  mov     eax, [rsi+10h]
0x1c001e5db  shr     rax, 12h
0x1c001e5df  test    al, 1
0x1c001e5e1  jnz     loc_1C0020A77
0x1c001e5e7  and     r14d, 1
0x1c001e5eb  mov     [rbp+3F0h+var_3F8], r14d
0x1c001e5ef  jz      short loc_1C001E609
0x1c001e5f1  mov     rax, [rsi+60h]
0x1c001e5f5  mov     rcx, [rax+18h]
0x1c001e5f9  test    dword ptr [rcx+0C2Ch], 20000000h
0x1c001e603  jnz     loc_1C0020CA2
0x1c001e609  test    r12, r12
0x1c001e60c  jnz     loc_1C001FEAB
0x1c001e612  mov     dl, 1; Wait
0x1c001e614  lea     rcx, [r13+3F8h]; Resource
0x1c001e61b  call    cs:__imp_ExAcquireResourceSharedLite
0x1c001e622  nop     dword ptr [rax+rax+00h]
0x1c001e627  mov     rdi, [r13+5E0h]
0x1c001e62e  mov     dl, 1; Wait
0x1c001e630  mov     rcx, rdi; Resource
0x1c001e633  mov     [rbp+3F0h+Resource], rdi
0x1c001e637  call    cs:__imp_ExAcquireResourceSharedLite
0x1c001e63e  nop     dword ptr [rax+rax+00h]
0x1c001e643  lea     rcx, [r13+3F8h]; Resource
0x1c001e64a  call    cs:__imp_ExReleaseResourceLite
0x1c001e651  nop     dword ptr [rax+rax+00h]
0x1c001e656  xor     ebx, ebx
0x1c001e658  lea     rcx, [rdi+68h]; Object
0x1c001e65c  xor     r9d, r9d; Alertable
0x1c001e65f  mov     [rsp+4F0h+Timeout], rbx; union _ML_LSN *
0x1c001e664  xor     r8d, r8d; WaitMode
0x1c001e667  xor     edx, edx; WaitReason
0x1c001e669  call    cs:__imp_KeWaitForSingleObject
0x1c001e670  nop     dword ptr [rax+rax+00h]
0x1c001e675  mov     r12, rdi
0x1c001e678  test    r14d, r14d
0x1c001e67b  jz      short loc_1C001E695
0x1c001e67d  mov     rax, [rsi+60h]
0x1c001e681  mov     rcx, [rax+18h]
0x1c001e685  test    dword ptr [rcx+0C2Ch], 20000000h
0x1c001e68f  jnz     loc_1C00778EE
0x1c001e695  or      qword ptr [r15+10h], 800h
0x1c001e69d  cmp     cs:dword_1C012D0B4, 1
0x1c001e6a4  jz      loc_1C0077910
0x1c001e6aa  mov     eax, [rsp+4F0h+var_484]
0x1c001e6ae  xorps   xmm0, xmm0
0x1c001e6b1  and     eax, 2
0x1c001e6b4  mov     [rbp+3F0h+var_1B0], 0
0x1c001e6bf  mov     [rbp+3F0h+var_460], eax
0x1c001e6c2  mov     eax, [rsp+4F0h+var_484]
0x1c001e6c6  and     eax, 7
0x1c001e6c9  movdqa  xmmword ptr [rbp+3F0h+var_160], xmm0
0x1c001e6d1  mov     [rbp+3F0h+var_150], rbx
0x1c001e6d8  cmp     al, 6
0x1c001e6da  jnz     loc_1C0020213
0x1c001e6e0  mov     rax, [rsi+20h]
0x1c001e6e4  mov     rbx, rsi
0x1c001e6e7  cmp     rax, rsi
0x1c001e6ea  jnz     loc_1C00209E0
0x1c001e6f0  mov     rax, [rbx+48h]
0x1c001e6f4  cmp     rax, rbx
0x1c001e6f7  jnz     loc_1C0020930
0x1c001e6fd  mov     rcx, [r15+20h]
0x1c001e701  mov     dl, 1; Wait
0x1c001e703  mov     rbx, [rbx+50h]
0x1c001e707  add     rcx, 0C58h; Resource
0x1c001e70e  mov     [rsp+4F0h+var_488], 0
0x1c001e716  call    cs:__imp_ExAcquireResourceSharedLite
0x1c001e71d  nop     dword ptr [rax+rax+00h]
0x1c001e722  mov     rdi, [rbx+80h]
0x1c001e729  add     rdi, 70h ; 'p'
0x1c001e72d  mov     rbx, rdi
0x1c001e730  lea     rcx, [rbx-70h]
0x1c001e734  mov     rdx, r15; struct CmsTransactionContext *
0x1c001e737  mov     rcx, [rcx]; this
0x1c001e73a  lea     r8, [rsp+4F0h+var_488]; void *
0x1c001e73f  mov     rbx, [rbx]
0x1c001e742  call    ?ReservePageFreeBuffersWorker@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAX@Z; CmsBPlusTable::ReservePageFreeBuffersWorker(CmsTransactionContext *,void *)
0x1c001e747  cmp     rbx, rdi
0x1c001e74a  jnz     short loc_1C001E730
0x1c001e74c  mov     rcx, [r15+20h]
0x1c001e750  add     rcx, 0C58h; Resource
0x1c001e757  call    cs:__imp_ExReleaseResourceLite
0x1c001e75e  nop     dword ptr [rax+rax+00h]
0x1c001e763  mov     edx, [rsp+4F0h+var_488]
0x1c001e767  mov     eax, dword ptr [rbp+3F0h+var_1B0]
0x1c001e76d  cmp     edx, eax
0x1c001e76f  jg      loc_1C001FCC1
0x1c001e775  mov     rcx, [rsi+20h]
0x1c001e779  mov     rax, rsi
0x1c001e77c  cmp     rcx, rsi
0x1c001e77f  jnz     loc_1C0020A00
0x1c001e785  mov     rcx, [rax+48h]
0x1c001e789  cmp     rcx, rax
0x1c001e78c  jnz     loc_1C0020950
0x1c001e792  mov     rax, [rax+50h]
0x1c001e796  xor     ebx, ebx
0x1c001e798  mov     rcx, [r15+20h]
0x1c001e79c  mov     dl, 1; Wait
0x1c001e79e  add     rcx, 0C58h; Resource
0x1c001e7a5  mov     r14, [rax]
0x1c001e7a8  mov     [rsp+4F0h+var_4A0], 0
0x1c001e7b1  call    cs:__imp_ExAcquireResourceSharedLite
0x1c001e7b8  nop     dword ptr [rax+rax+00h]
0x1c001e7bd  mov     rax, [r14+50h]
0x1c001e7c1  mov     rdi, rbx
0x1c001e7c4  mov     rbx, [rax+80h]
0x1c001e7cb  mov     rax, [rbx]
0x1c001e7ce  lock inc dword ptr [rax+8]
0x1c001e7d2  cmp     rdi, rbx
0x1c001e7d5  jz      short loc_1C001E7E0
0x1c001e7d7  test    rdi, rdi
0x1c001e7da  jnz     loc_1C0077BC3
0x1c001e7e0  lea     rsi, [rbx+70h]
0x1c001e7e4  mov     [rsp+4F0h+var_4A0], rsi
0x1c001e7e9  mov     rdi, [rsp+4F0h+var_4A0]
0x1c001e7ee  mov     rcx, [r15+20h]
0x1c001e7f2  add     rdi, 0FFFFFFFFFFFFFF90h
0x1c001e7f6  add     rcx, 0C58h; Resource
0x1c001e7fd  call    cs:__imp_ExReleaseResourceLite
0x1c001e804  nop     dword ptr [rax+rax+00h]
0x1c001e809  mov     rax, [rdi]
0x1c001e80c  mov     dl, 1; Wait
0x1c001e80e  mov     rcx, [rax+50h]
0x1c001e812  add     rcx, 8; Resource
0x1c001e816  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c001e81d  nop     dword ptr [rax+rax+00h]
0x1c001e822  mov     rcx, [r15+20h]
0x1c001e826  mov     dl, 1; Wait
0x1c001e828  add     rcx, 0C58h; Resource
0x1c001e82f  call    cs:__imp_ExAcquireResourceSharedLite
0x1c001e836  nop     dword ptr [rax+rax+00h]
0x1c001e83b  mov     rax, [rsp+4F0h+var_4A0]
0x1c001e840  mov     rcx, [rax]
0x1c001e843  mov     [rsp+4F0h+var_4A0], rcx
0x1c001e848  lea     rcx, [rdi+0A0h]; Event
0x1c001e84f  call    cs:__imp_KeClearEvent
0x1c001e856  nop     dword ptr [rax+rax+00h]
0x1c001e85b  cmp     rdi, rbx
0x1c001e85e  jnz     short loc_1C001E870
0x1c001e860  mov     rax, gs:188h
0x1c001e869  mov     [rdi+90h], rax
0x1c001e870  mov     rax, [r14+50h]
0x1c001e874  mov     rcx, [rax+80h]
0x1c001e87b  cmp     rcx, rbx
0x1c001e87e  jnz     loc_1C001E7BD
0x1c001e884  mov     rax, [rdi+80h]
0x1c001e88b  cmp     rax, rbx
0x1c001e88e  jnz     loc_1C001E7BD
0x1c001e894  mov     rax, [rsp+4F0h+var_4A0]
0x1c001e899  cmp     rax, rsi
0x1c001e89c  jnz     loc_1C001E7E9
0x1c001e8a2  mov     rax, gs:188h
0x1c001e8ab  mov     r14, [rsp+4F0h+var_498]
0x1c001e8b0  mov     [rbx+98h], rax
0x1c001e8b7  mov     qword ptr [rbx+90h], 0
0x1c001e8c2  mov     rcx, [r14+20h]
0x1c001e8c6  add     rcx, 0C58h; Resource
0x1c001e8cd  call    cs:__imp_ExReleaseResourceLite
0x1c001e8d4  nop     dword ptr [rax+rax+00h]
0x1c001e8d9  mov     rcx, [rbx]
0x1c001e8dc  mov     eax, 0FFFFFFFFh
0x1c001e8e1  lock xadd [rcx+8], eax
0x1c001e8e6  cmp     eax, 1
0x1c001e8e9  jz      loc_1C0077C49
0x1c001e8ef  or      qword ptr [r14+10h], 20000000h
0x1c001e8f7  test    qword ptr [r14+10h], 400h
0x1c001e8ff  mov     rsi, [rbp+3F0h+arg_28]
0x1c001e906  jnz     loc_1C001FEB2
0x1c001e90c  xor     ecx, ecx; PerformanceFrequency
0x1c001e90e  call    cs:__imp_KeQueryPerformanceCounter
0x1c001e915  nop     dword ptr [rax+rax+00h]
0x1c001e91a  lea     rcx, [rbp+3F0h+PerformanceFrequency]; PerformanceFrequency
0x1c001e91e  mov     [rbp+3F0h+var_390], rax
0x1c001e922  call    cs:__imp_KeQueryPerformanceCounter
0x1c001e929  nop     dword ptr [rax+rax+00h]
0x1c001e92e  mov     rdx, [rsp+4F0h+var_490]
0x1c001e933  mov     rax, rdx
0x1c001e936  mov     rcx, [rdx+20h]
0x1c001e93a  cmp     rcx, rdx
0x1c001e93d  jnz     loc_1C0020A20
0x1c001e943  mov     rcx, [rax+48h]
0x1c001e947  cmp     rcx, rax
0x1c001e94a  jnz     loc_1C0020970
0x1c001e950  mov     rax, [rax+50h]
0x1c001e954  mov     r15, [rax+80h]
0x1c001e95b  lea     r13, [r15+70h]
0x1c001e95f  mov     rbx, r13
0x1c001e962  lea     rcx, [rbx-70h]
0x1c001e966  mov     rdx, r14; struct CmsTransactionContext *
0x1c001e969  mov     rcx, [rcx]; this
0x1c001e96c  lea     r8, [rbp+3F0h+var_2A0]; void *
0x1c001e973  mov     rbx, [rbx]
0x1c001e976  call    ?MergeDeleteQueueIntoPreviousGeneration@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAX@Z; CmsBPlusTable::MergeDeleteQueueIntoPreviousGeneration(CmsTransactionContext *,void *)
0x1c001e97b  cmp     rbx, r13
0x1c001e97e  jnz     short loc_1C001E962
0x1c001e980  mov     rax, [r13+0]
0x1c001e984  mov     [rbp+3F0h+var_340], rax
0x1c001e98b  mov     eax, [r14+10h]
0x1c001e98f  bt      rax, 0Ah
0x1c001e994  jb      loc_1C001FEC4
0x1c001e99a  xor     edx, edx
0x1c001e99c  lea     rcx, [r15+208h]
0x1c001e9a3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c001e9aa  nop     dword ptr [rax+rax+00h]
0x1c001e9af  cmp     qword ptr [r15+210h], 0
0x1c001e9b7  jnz     loc_1C001FD1B
  ... truncated ...
```
