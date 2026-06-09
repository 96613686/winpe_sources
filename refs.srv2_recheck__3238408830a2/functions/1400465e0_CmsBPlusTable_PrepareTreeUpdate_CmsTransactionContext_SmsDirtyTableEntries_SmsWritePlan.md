# CmsBPlusTable::PrepareTreeUpdate(CmsTransactionContext *,SmsDirtyTableEntries *,SmsWritePlan *)

- ea: `0x1400465e0`
- end: `0x140047281`
- name: `?PrepareTreeUpdate@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAUSmsDirtyTableEntries@@PEAUSmsWritePlan@@@Z`
- size: `3233`
- prototype: `void __fastcall(struct CmsTransactionContext *, struct SmsDirtyTableEntries *, struct SmsWritePlan *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140147c6c`

## callees

- `0x140014750`
- `0x140046508`
- `0x1400465e0`
- `0x140047288`
- `0x140047300`
- `0x140047400`
- `0x140047730`
- `0x140047b2c`
- `0x1400774f0`
- `0x140080270`
- `0x140087870`
- `0x140096e60`
- `0x1400b26e8`
- `0x1400ceda0`
- `0x1400d4208`
- `0x140146a7c`
- `0x140146ad4`
- `0x1401f3fb0`
- `0x1401f4090`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x140047077`
- `ntoskrnl!IoGetActivityIdThread` at `0x140047077`
- `ntoskrnl!KeSetEvent` at `0x1400467c3`
- `ntoskrnl!KeSetEvent` at `0x140046ff7`
- `ntoskrnl!KeSetEvent` at `0x1400467c3`
- `ntoskrnl!KeSetEvent` at `0x140046ff7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046fca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046fca`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047197`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047197`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004708b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004708b`
- `ntoskrnl!ExAllocatePool2` at `0x140046a4b`
- `ntoskrnl!ExAllocatePool2` at `0x140047112`
- `ntoskrnl!ExAllocatePool2` at `0x1401fcd63`
- `ntoskrnl!ExAllocatePool2` at `0x1401fce7c`
- `ntoskrnl!ExAllocatePool2` at `0x140046a4b`
- `ntoskrnl!ExAllocatePool2` at `0x140047112`
- `ntoskrnl!ExAllocatePool2` at `0x1401fcd63`
- `ntoskrnl!ExAllocatePool2` at `0x1401fce7c`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140046869`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140046869`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140046a0e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140046a0e`
- `ntoskrnl!ExTryQueueWorkItem` at `0x1400470cd`
- `ntoskrnl!ExTryQueueWorkItem` at `0x1400470cd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fcd0a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fcd0a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140047027`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140047027`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fcd2f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fcd2f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400471b5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400471b5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046add`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046d80`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046add`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046d80`
- `ntoskrnl!KeInitializeEvent` at `0x140046919`
- `ntoskrnl!KeInitializeEvent` at `0x140046cb5`
- `ntoskrnl!KeInitializeEvent` at `0x140046919`
- `ntoskrnl!KeInitializeEvent` at `0x140046cb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046bc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046daa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400471ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047202`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401fcde7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046bc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046daa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400471ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047202`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401fcde7`

## string_xrefs

- `0x1401fcd46`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
void __fastcall CmsBPlusTable::PrepareTreeUpdate(
        struct CmsTransactionContext *a1,
        struct SmsDirtyTableEntries **a2,
        struct SmsWritePlan *a3,
        unsigned __int8 *a4)
{
  struct CmsTransactionContext *v4; // r14
  __int64 i; // rbx
  unsigned __int8 *v6; // rsi
  char *v7; // rdx
  struct SmsWritePlan *v8; // rdi
  __int64 v9; // rcx
  _QWORD **v10; // rdx
  _QWORD *v11; // r8
  _QWORD *v12; // r11
  _QWORD *j; // r9
  _QWORD *k; // rdx
  _QWORD *m; // rax
  __int64 v16; // rax
  char *v17; // rdx
  struct SmsWritePlan *v18; // rcx
  unsigned int v19; // ebx
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v22; // edi
  ULONG ActiveProcessorCount; // r15d
  int v24; // ecx
  int v25; // eax
  __int64 v26; // r14
  __int64 v27; // r9
  __int128 *v28; // rdi
  int v29; // eax
  ULONG v30; // r8d
  int v31; // edx
  int v32; // r10d
  __int128 *v33; // r9
  struct CmsTransactionContext *v34; // rdx
  __int64 v35; // rcx
  char *v36; // r12
  char *v37; // r9
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  _QWORD **v43; // rax
  __int64 v44; // r13
  __int64 v45; // rdi
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // rax
  PSLIST_ENTRY v49; // r14
  int v50; // ecx
  int v51; // edx
  int v52; // r10d
  __int64 v53; // rax
  int v54; // r8d
  __int64 v55; // rdx
  int v56; // eax
  __int64 v57; // rdx
  unsigned __int8 v58; // al
  _QWORD *v59; // r13
  unsigned __int64 v60; // rsi
  unsigned int v61; // r15d
  __int64 v62; // r9
  __int64 v63; // rcx
  _OWORD *v64; // r12
  __int64 v65; // r14
  _QWORD *v66; // rdx
  _OWORD *v67; // rdi
  struct CmsTransactionContext *Tx; // rax
  CmsTransactionContext *v69; // rbx
  char *v70; // rsi
  _QWORD *v71; // r9
  _QWORD *v72; // r11
  _QWORD *v73; // rbx
  _QWORD *v74; // r10
  bool v75; // zf
  unsigned int v76; // ebx
  __int64 v77; // rdi
  struct _SLIST_ENTRY *v78; // r14
  __int64 v79; // r13
  _QWORD *v80; // r10
  char v81; // di
  _QWORD *v82; // rdx
  __int64 v83; // r9
  __int64 v84; // r8
  void (__fastcall *v85)(struct _SLIST_ENTRY *, _QWORD, __int64, __int64, _QWORD); // rax
  __int64 v86; // rdi
  struct _SLIST_ENTRY *Next; // rdi
  struct _SLIST_ENTRY *v88; // r14
  struct _NPAGED_LOOKASIDE_LIST *v89; // rcx
  __int128 *ActivityIdThread; // r14
  __int128 v91; // xmm0
  size_t v92; // r14
  void *Pool2; // rax
  struct _NPAGED_LOOKASIDE_LIST *v94; // rcx
  struct _SLIST_ENTRY *v95; // rax
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rsi
  enum _WORK_QUEUE_TYPE v99; // r9d
  size_t v100; // rdi
  _OWORD *v101; // rax
  _DWORD v102[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct SmsWritePlan *v103; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v104; // [rsp+50h] [rbp-B0h]
  int v105; // [rsp+54h] [rbp-ACh] BYREF
  struct CmsTransactionContext *v106; // [rsp+58h] [rbp-A8h]
  struct _KEVENT Event; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v108; // [rsp+78h] [rbp-88h]
  int v109; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v110; // [rsp+84h] [rbp-7Ch]
  unsigned int v111; // [rsp+88h] [rbp-78h]
  __int64 v112; // [rsp+90h] [rbp-70h]
  struct CmsTransactionContext *v113; // [rsp+98h] [rbp-68h] BYREF
  __int64 v114; // [rsp+A0h] [rbp-60h] BYREF
  __int128 *v115; // [rsp+A8h] [rbp-58h]
  PVOID P; // [rsp+B0h] [rbp-50h]
  _QWORD v117[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct CmsTransactionContext *v118; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v119; // [rsp+D0h] [rbp-30h]
  _QWORD *v120; // [rsp+D8h] [rbp-28h]
  _QWORD *v121; // [rsp+E0h] [rbp-20h]
  _QWORD v122[5]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v123; // [rsp+110h] [rbp+10h] BYREF
  __int64 v124; // [rsp+120h] [rbp+20h]
  __int64 v125; // [rsp+128h] [rbp+28h]
  __int64 v126; // [rsp+130h] [rbp+30h]
  __int128 v127; // [rsp+138h] [rbp+38h]
  __int128 v128; // [rsp+148h] [rbp+48h]
  __int128 v129; // [rsp+158h] [rbp+58h]
  __int128 v130; // [rsp+168h] [rbp+68h]
  _OWORD v131[7]; // [rsp+180h] [rbp+80h] BYREF

  v103 = a3;
  *(_QWORD *)a1 |= 0x1000uLL;
  v4 = a1;
  v106 = a1;
  if ( !a2 )
    goto LABEL_17;
  while ( a2 )
  {
    LODWORD(i) = 0;
    while ( (unsigned int)i < 8 )
    {
      v6 = (unsigned __int8 *)&a2[12 * (unsigned int)i + 1];
      if ( *(_QWORD *)v6 )
        goto LABEL_8;
      LODWORD(i) = i + 1;
    }
    a2 = (struct SmsDirtyTableEntries **)*a2;
  }
  v6 = 0;
  LODWORD(i) = -1;
LABEL_8:
  if ( !v6 )
    goto LABEL_17;
  while ( 2 )
  {
    if ( (v6[48] & 1) == 0 )
      goto LABEL_10;
    v20 = *(_QWORD *)v6;
    if ( *(_QWORD *)(v20 + 32) != v20 )
      goto LABEL_65;
    v21 = *(_QWORD *)(v20 + 40) + 16LL;
    v118 = v4;
    v114 = v21;
    v22 = *(_DWORD *)(v21 + 12) + *(_DWORD *)(v21 + 28);
    ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
    if ( ActiveProcessorCount >> 1 > 8 )
    {
      v24 = 8;
      goto LABEL_57;
    }
    v24 = ActiveProcessorCount >> 2;
    if ( ActiveProcessorCount >> 2 > 4 )
    {
LABEL_57:
      v25 = 4;
      goto LABEL_43;
    }
    if ( v24 )
    {
      v25 = ActiveProcessorCount >> 2;
    }
    else
    {
      v25 = 1;
      v24 = 1;
    }
LABEL_43:
    if ( v22 >= 0x64 )
    {
      if ( v22 <= 0x5DC )
      {
        ActiveProcessorCount = v25;
        if ( v22 > 0x3E8 )
          ActiveProcessorCount = v24;
      }
    }
    else
    {
      ActiveProcessorCount = 1;
    }
    v26 = v114;
    v122[0] = &v118;
    v112 = v114;
    v122[1] = CmsBPlusTable::BuildWritePlanListsParallel;
    v109 = 0;
    v122[2] = &v114;
    v123 = 0;
    v122[3] = &v103;
    v124 = 0;
    v125 = 0;
    v126 = 0;
    v127 = 0;
    v102[0] = 0;
    v128 = 0;
    v129 = 0;
    v130 = 0;
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    if ( ActiveProcessorCount > 1 )
    {
      v92 = 104LL * ActiveProcessorCount;
      if ( !is_mul_ok(ActiveProcessorCount, 0x68u) )
        v92 = -1;
      Pool2 = (void *)ExAllocatePool2(66, v92, 1766871885, v27);
      P = Pool2;
      v28 = (__int128 *)Pool2;
      if ( Pool2 )
      {
        memset(Pool2, 0, v92);
        _____builtin_array_init_helper_UWorker__1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable____QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__CmsHashTable__QEAAJK__QEAV_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV2___QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV6_AEAPEAU7__Z__Z___YAXPEAUWorker__1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable____QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__CmsHashTable__QEAAJK__QEAV_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV1___QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__Z__K_Z(
          v28,
          ActiveProcessorCount);
        v26 = v112;
        v29 = ActiveProcessorCount;
        v30 = 0;
        v31 = ActiveProcessorCount;
        goto LABEL_47;
      }
      v26 = v112;
    }
    v28 = &v123;
    ActiveProcessorCount = 1;
    P = &v123;
    v29 = 1;
    v30 = 0;
    v31 = 1;
LABEL_47:
    v102[0] = v31;
    v32 = v29 - 1;
    v115 = v28;
    v33 = v28;
    v105 = v29 - 1;
    v34 = (struct CmsTransactionContext *)((char *)v28 + 28);
    v113 = (struct CmsTransactionContext *)((char *)v28 + 28);
    do
    {
      v35 = 104LL * v30;
      v36 = (char *)v33 + v35;
      v37 = (char *)v34 + v35;
      HIDWORD(v39) = 0;
      *(_QWORD *)v36 = v122;
      *((_QWORD *)v36 + 1) = &v109;
      *((_QWORD *)v36 + 2) = v102;
      *((_QWORD *)v36 + 4) = &Event;
      LODWORD(v39) = (*(_DWORD *)(v26 + 8) + *(_DWORD *)(v26 + 24)) % ActiveProcessorCount;
      v38 = (*(_DWORD *)(v26 + 8) + *(_DWORD *)(v26 + 24)) / ActiveProcessorCount;
      *((_DWORD *)v36 + 6) = v30 * v38;
      v104 = v30 + 1;
      v40 = v38 * (v30 + 1);
      *(_DWORD *)v37 = v40;
      if ( v30 == v32 )
        *(_DWORD *)v37 = -1;
      if ( ActiveProcessorCount <= 1 )
        goto LABEL_51;
      ActivityIdThread = (__int128 *)IoGetActivityIdThread(v40, v39);
      if ( ActivityIdThread && KeGetCurrentIrql() < 2u )
        v91 = *ActivityIdThread;
      else
        v91 = 0;
      *(_OWORD *)(v36 + 40) = v91;
      *((_QWORD *)v36 + 12) = v36;
      *((_QWORD *)v36 + 11) = __lambda_invoker_cdecl___lambda_1___1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_A6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAUSmsWritePlan___ZAEAPEAU3__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable__A6AX01KKPEAUSmsWritePlan___ZAEAPEAU5__Z__CmsHashTable__QEAAJK__QEAV1_1____ParallelTuPageTableWork_A6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAUSmsWritePlan___ZAEAPEAU3__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV2_A6AX01KKPEAUSmsWritePlan___ZAEAPEAU5__Z__Z_SA_PEAX_Z;
      *((_QWORD *)v36 + 10) = v36 + 40;
      *((_QWORD *)v36 + 9) = MspWorkerRoutine;
      *((_QWORD *)v36 + 7) = 0;
      if ( !(unsigned __int8)ExTryQueueWorkItem(v36 + 56, 0) )
      {
LABEL_51:
        v41 = *(_QWORD *)v36;
        v110 = *((_DWORD *)v36 + 7);
        v111 = *((_DWORD *)v36 + 6);
        v120 = *(_QWORD **)(v41 + 24);
        v121 = *(_QWORD **)(v41 + 16);
        v42 = *(_QWORD *)(v41 + 8);
        v43 = *(_QWORD ***)v41;
        v117[0] = v42;
        v119 = *v43;
        v44 = v119[1];
        v45 = qword_140269408 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
        if ( *(_DWORD *)v45 < 0xDD0u )
        {
          v45 = 0;
          v47 = 3552;
LABEL_53:
          v48 = ExAllocatePool2(66, v47, 1766871885, v46);
          v49 = (PSLIST_ENTRY)v48;
          if ( (v48 & 0xF) != 0 )
            MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
          if ( !v48 )
            goto LABEL_125;
          CmsTransactionContext::InitializeTransactionMemoryBuffer((void *)(v48 + 16));
LABEL_138:
          v49->Next = (struct _SLIST_ENTRY *)v45;
          v78 = v49 + 1;
          if ( v78 )
          {
            *((_QWORD *)&v78->Next + 1) = v44;
            v79 = 0x8000;
            v78->Next = (struct _SLIST_ENTRY *)0x8000;
LABEL_126:
            v80 = v119;
            v81 = *((_BYTE *)&v78[13].Next + 12);
            v82 = v121;
            v83 = v110;
            v84 = v111;
            v85 = (void (__fastcall *)(struct _SLIST_ENTRY *, _QWORD, __int64, __int64, _QWORD))v117[0];
            v78->Next = (struct _SLIST_ENTRY *)(*v119 | v79);
            *((_BYTE *)&v78[13].Next + 12) = *((_BYTE *)v80 + 220);
            v85(v78, *v82, v84, v83, *v120);
            CmsTransactionContext::Commit((CmsTransactionContext *)v78, 0, 0, 0);
            *((_BYTE *)&v78[13].Next + 12) = v81;
            v86 = *((_QWORD *)&v78->Next + 1);
            v78->Next = (struct _SLIST_ENTRY *)v79;
            CmsTransactionContext::~CmsTransactionContext((CmsTransactionContext *)v78);
            if ( (v79 & 0x10000000) != 0 )
            {
              CmsReservedPool::FreeToPool((CmsReservedPool *)(v86 + 160), v78);
              goto LABEL_131;
            }
            Next = v78[-1].Next;
            v88 = v78 - 1;
            if ( Next )
            {
              if ( *((_BYTE *)&Next->Next + 8) )
              {
                v89 = (struct _NPAGED_LOOKASIDE_LIST *)&Next[4];
                if ( *((_BYTE *)&Next->Next + 9) )
                  ExFreeToNPagedLookasideList(v89, v88);
                else
                  ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v89, v88);
LABEL_131:
                if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)v36 + 2), 0xFFFFFFFF) == 1 )
                  KeSetEvent(*((PRKEVENT *)v36 + 4), 0, 0);
                goto LABEL_133;
              }
              v96 = *((_QWORD *)&Next[5].Next + 1);
              if ( (int)v96 < SLODWORD(Next[5].Next) || SHIDWORD(v96) >= (int)v96 )
              {
                ExpInterlockedPushEntrySList((PSLIST_HEADER)&Next[4], v88);
                _InterlockedIncrement((volatile signed __int32 *)&Next[5].Next + 2);
                goto LABEL_131;
              }
            }
            ExFreePoolWithTag(v88, 0);
            goto LABEL_131;
          }
LABEL_125:
          v78 = (struct _SLIST_ENTRY *)CmsReservedPool::AllocateFromPool((CmsReservedPool *)(v44 + 160));
          CmsTransactionContext::InitializeTransactionMemoryBuffer(v78);
          *((_QWORD *)&v78->Next + 1) = v44;
          v79 = 268468224;
          v78->Next = (struct _SLIST_ENTRY *)268468224;
          goto LABEL_126;
        }
        if ( !*(_BYTE *)(v45 + 8) )
        {
          if ( (int)*(_QWORD *)(v45 + 88) > (int)HIDWORD(*(_QWORD *)(v45 + 88)) )
          {
            v50 = _InterlockedDecrement((volatile signed __int32 *)(v45 + 88));
            if ( v50 >= *(_DWORD *)(v45 + 92) && v50 >= 0 )
            {
              v49 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v45 + 64));
              goto LABEL_137;
            }
            _InterlockedIncrement((volatile signed __int32 *)(v45 + 88));
          }
LABEL_62:
          v47 = *(unsigned int *)(v45 + 4);
          goto LABEL_53;
        }
        v94 = (struct _NPAGED_LOOKASIDE_LIST *)(v45 + 64);
        if ( *(_BYTE *)(v45 + 9) )
          v95 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v94);
        else
          v95 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v94);
        v49 = v95;
        CmsTransactionContext::InitializeTransactionMemoryBuffer(&v95->Next + 1);
LABEL_137:
        if ( v49 )
          goto LABEL_138;
        goto LABEL_62;
      }
LABEL_133:
      v30 = v104;
      v26 = v112;
      v34 = v113;
      v32 = v105;
      v33 = v115;
    }
    while ( v104 < ActiveProcessorCount );
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( P && P != &v123 )
      ExFreePoolWithTag(P, 0);
    v4 = v106;
LABEL_65:
    if ( v6[89] && (v6[48] & 8) != 0 )
    {
      v51 = 0;
      v52 = 1;
      a4 = v6;
      if ( (*(_DWORD *)v4 & 0x400LL) != 0 && (*(_BYTE *)(*(_QWORD *)v6 + 14LL) & 0x38) == 0x18 )
      {
        v57 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v4 + 1) + 3272LL) + 16LL);
        v58 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v57 + 32) + 200LL) + 88LL);
        if ( v58 <= *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v57 + 40) + 200LL) + 88LL) )
          v58 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v57 + 40) + 200LL) + 88LL);
        v51 = v58 + 1;
      }
      while ( 1 )
      {
        v53 = *(_QWORD *)(*(_QWORD *)a4 + 112LL);
        if ( *(_BYTE *)(v53 + 11) )
          break;
        a4 = *(unsigned __int8 **)(**(_QWORD **)(v53 + 40) + 200LL);
        v52 += a4[88] + 1;
      }
      v54 = v52 + v51;
      v55 = 24LL * (v52 + v51);
      *((_QWORD *)v6 + 10) = *(_QWORD *)((char *)v103 + v55 + 128);
      *(_QWORD *)((char *)v103 + v55 + 128) = v6;
      ++*(_DWORD *)((char *)v103 + v55 + 140);
      v56 = *((_DWORD *)v103 + 222);
      if ( v56 <= v54 )
        v56 = v54;
      *((_DWORD *)v103 + 222) = v56;
    }
LABEL_10:
    v7 = (char *)&v6[-96 * (int)i - 8];
LABEL_11:
    if ( v7 )
    {
      for ( i = (unsigned int)(i + 1); ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= 8 )
        {
          v7 = *(char **)v7;
          LODWORD(i) = -1;
          goto LABEL_11;
        }
        v6 = (unsigned __int8 *)&v7[96 * i + 8];
        if ( *(_QWORD *)v6 )
          break;
      }
      if ( v6 )
        continue;
    }
    break;
  }
LABEL_17:
  v8 = v103;
  if ( *((_DWORD *)v103 + 28) >= 0x64u && (v97 = ExAllocatePool2(66, 96, 1766871885, a4), (v98 = v97) != 0) )
  {
    *(_BYTE *)(v97 + 9) = 0;
    *(_DWORD *)(v97 + 10) = 0;
    *(_WORD *)(v97 + 14) = 0;
    *(_DWORD *)(v97 + 28) = 0;
    memset((void *)(v97 + 32), 0, 0x40u);
    *(_BYTE *)(v98 + 8) = 1;
    *(_QWORD *)v98 = (char *)v8 + 64;
    *(_DWORD *)(v98 + 24) = 0;
    *(_QWORD *)(v98 + 16) = v8;
    *(_BYTE *)(v98 + 9) = (*(_DWORD *)v4 & 0x400LL) != 0;
    *(_BYTE *)(v98 + 10) = (*(_DWORD *)v4 & 0x800LL) != 0;
    if ( !MsInitializeAndTryQueueWorkItem(
            (struct _MS_WORK_QUEUE_ITEM *)(v98 + 32),
            (void (*)(void *))SortWritePlanWorker,
            (void *)v98,
            v99) )
    {
      ExFreePoolWithTag((PVOID)v98, 0);
      goto LABEL_18;
    }
  }
  else
  {
LABEL_18:
    v9 = *(_QWORD *)v4;
    *(_QWORD *)&Event.Header.Lock = (char *)v8 + 64;
    BYTE1(Event.Header.WaitListHead.Flink) = (v9 & 0x400) != 0;
    LOBYTE(Event.Header.WaitListHead.Flink) = 0;
    BYTE2(Event.Header.WaitListHead.Flink) = (v9 & 0x800) != 0;
    v108 = 0;
    Event.Header.WaitListHead.Blink = (struct _LIST_ENTRY *)v8;
    if ( *((_DWORD *)v8 + 28) <= (unsigned int)dword_140269184 )
    {
      v10 = (_QWORD **)*((_QWORD *)v8 + 4);
      v11 = (_QWORD *)((char *)v8 + 32);
      if ( v10 != (_QWORD **)((char *)v8 + 32) && *v10 != v11 )
      {
        *((_QWORD *)v8 + 5) = v10;
        v12 = v10;
        for ( j = *v10; j != v11; j = (_QWORD *)*j )
        {
          if ( (__int64)*(v10 - 5) - *(j - 5) > 0 )
          {
            v12[1] = j;
            v12 = j;
            *v10 = 0;
          }
          v10 = (_QWORD **)j;
        }
        if ( *((_QWORD **)v8 + 5) == v12 )
        {
          *((_QWORD *)v8 + 5) = v10;
        }
        else
        {
          *v10 = 0;
          v12[1] = 0;
          for ( k = (_QWORD *)*((_QWORD *)v8 + 5); k[1]; k = (_QWORD *)*((_QWORD *)v8 + 5) )
          {
            v70 = (char *)v8 + 32;
            do
            {
              v71 = (_QWORD *)k[1];
              v72 = (_QWORD *)v71[1];
              if ( (__int64)(*(k - 5) - *(v71 - 5)) > 0 )
              {
                v73 = (_QWORD *)k[1];
                v71 = (_QWORD *)*v71;
              }
              else
              {
                v73 = k;
                k = (_QWORD *)*k;
              }
              v74 = v73;
              v75 = k == 0;
              if ( k )
              {
                do
                {
                  if ( !v71 )
                    break;
                  if ( (__int64)(*(k - 5) - *(v71 - 5)) > 0 )
                  {
                    *v74 = v71;
                    v74 = v71;
                    v71 = (_QWORD *)*v71;
                  }
                  else
                  {
                    *v74 = k;
                    v74 = k;
                    k = (_QWORD *)*k;
                  }
                }
                while ( k );
                v75 = k == 0;
              }
              if ( v75 )
                k = v71;
              *v74 = k;
              *((_QWORD *)v70 + 1) = v73;
              v73[1] = v72;
              if ( !v72 )
                break;
              v70 = (char *)v73;
              k = v72;
            }
            while ( v72[1] );
          }
          *v11 = k;
          for ( m = (_QWORD *)((char *)v8 + 32); k; k = (_QWORD *)*k )
          {
            k[1] = m;
            m = k;
          }
          *m = v11;
          *((_QWORD *)v8 + 5) = m;
        }
      }
    }
    v16 = *((_QWORD *)v8 + 4);
    *((_QWORD *)v8 + 126) = v16;
    *((_QWORD *)v8 + 129) = v16;
    v75 = *((_DWORD *)v8 + 28) == 0;
    *((_DWORD *)v8 + 256) = 0;
    if ( !v75 && (*(_DWORD *)(*(_QWORD *)v8 + 3396LL) & 0x400000) == 0 )
    {
      if ( LOBYTE(Event.Header.WaitListHead.Flink) )
      {
        Tx = CmsTransactionContext::MakeTx(*(struct CmsVolume **)v8);
        v69 = Tx;
        if ( Tx )
        {
          if ( BYTE1(Event.Header.WaitListHead.Flink) )
            *(_QWORD *)Tx |= 0x20000C00uLL;
          if ( BYTE2(Event.Header.WaitListHead.Flink) )
            *(_QWORD *)Tx |= 0x20000800uLL;
          CmsBPlusTable::WriteBindableUpdate(Tx, v8, 0, 0);
          CmsTransactionContext::Commit(v69, 0, 0, 0);
          CmsTransactionContext::Release(v69);
          _InterlockedIncrement(&dword_1402695C0);
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)&DbgCounts + v108 + 54);
        }
      }
      else
      {
        _InterlockedIncrement(&dword_1402695C8);
      }
    }
    KeSetEvent(*(PRKEVENT *)&Event.Header.Lock, 0, 0);
    if ( LOBYTE(Event.Header.WaitListHead.Flink) )
      ExFreePoolWithTag(&Event, 0);
  }
  v18 = v103;
  if ( *((int *)v103 + 222) >= 0 )
  {
    v76 = 0;
    do
    {
      v77 = 24LL * v76;
      if ( *(_DWORD *)((char *)v18 + v77 + 136) )
      {
        CmsBPlusTable::ParallelTuListWork<88,SmsPage,void (&)(CmsTransactionContext *,SmsPage *,SmsPage *,SmsWritePlan *),SmsWritePlan * &>(
          v4,
          *((_QWORD *)v18 + 3 * v76 + 15));
        v18 = v103;
      }
      v17 = (char *)v18 + v77;
      if ( *(_DWORD *)((char *)v18 + v77 + 140) )
      {
        CmsBPlusTable::ParallelTuListWork<80,SmsDirtyTableEntry,void (&)(CmsTransactionContext *,SmsDirtyTableEntry *,SmsDirtyTableEntry *),>(
          v4,
          *((_QWORD *)v17 + 16));
        v18 = v103;
      }
      if ( v76 )
        --v76;
      else
        v76 = *((_DWORD *)v18 + 222);
    }
    while ( v76 );
  }
  v19 = *((_DWORD *)v18 + 250);
  if ( v19 )
  {
    v59 = (_QWORD *)*((_QWORD *)v18 + 123);
    v117[0] = &v113;
    v113 = v4;
    v117[1] = CmsBPlusTable::UnlinkAllOldPagesParallel;
    v60 = CmsBPlusTable::DeterminePageTableWorkerCount(v19, (unsigned __int8)v17);
    memset(v131, 0, sizeof(v131));
    v105 = 0;
    v102[0] = 0;
    v61 = 0;
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    if ( (unsigned int)v60 <= 1 )
      goto LABEL_80;
    v100 = 112 * v60;
    if ( !is_mul_ok(v60, 0x70u) )
      v100 = -1;
    v101 = (_OWORD *)ExAllocatePool2(66, v100, 1766871885, v62);
    v64 = v101;
    if ( v101 )
    {
      memset(v101, 0, v100);
      _____builtin_array_init_helper_UWorker__1____ParallelListWork__0A_U_LIST_ENTRY__V_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011_Z_Z___YAJKKPEAU_LIST_ENTRY____QEAV_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100_Z_Z__Z___YAXPEAUWorker__1____ParallelListWork__0A_U_LIST_ENTRY__V_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011_Z_Z___YAJKKPEAU_LIST_ENTRY____QEAV_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100_Z_Z__Z__K_Z(
        v64,
        v60);
      v63 = 1;
    }
    else
    {
LABEL_80:
      v63 = 1;
      v64 = v131;
      LODWORD(v60) = 1;
    }
    v102[0] = v60;
    if ( v19 / (unsigned int)v60 > 1 )
      v63 = v19 / (unsigned int)v60;
    v104 = v63;
    v65 = 0;
    do
    {
      v66 = v59;
      if ( ++v61 == (_DWORD)v60 )
        v63 = v19;
      if ( (_DWORD)v63 )
      {
        do
        {
          v59 = (_QWORD *)*v59;
          --v19;
          v75 = (_DWORD)v63 == 1;
          v63 = (unsigned int)(v63 - 1);
        }
        while ( !v75 );
      }
      v67 = &v64[7 * v65];
      *(_QWORD *)v67 = v117;
      *((_QWORD *)v67 + 1) = &v105;
      *((_QWORD *)v67 + 2) = v102;
      *((_QWORD *)v67 + 5) = &Event;
      *((_QWORD *)v67 + 3) = v66;
      *((_QWORD *)v67 + 4) = v59;
      if ( (unsigned int)v60 <= 1
        || !MsInitializeAndTryQueueWorkItem(
              (struct _MS_WORK_QUEUE_ITEM *)(v67 + 3),
              __lambda_invoker_cdecl___lambda_1___1____ParallelListWork__0A_U_LIST_ENTRY__V_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011_Z_Z___YAJKKPEAU_LIST_ENTRY____QEAV1_1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100_Z_Z__Z_SA_PEAX_Z,
              &v64[7 * v65],
              (enum _WORK_QUEUE_TYPE)v62) )
      {
        __R_lambda_1___1____ParallelListWork__0A_U_LIST_ENTRY__V_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011_Z_Z___YAJKKPEAU_LIST_ENTRY____QEAV0_1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100_Z_Z__Z_QEBA_PEAX_Z(
          v63,
          &v64[7 * v65]);
      }
      v63 = v104;
      ++v65;
    }
    while ( v61 < (unsigned int)v60 );
    v4 = v106;
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( v64 && v64 != v131 )
      ExFreePoolWithTag(v64, 0);
  }
  *(_QWORD *)v4 &= ~0x1000uLL;
}

```

## disassembly

```asm
0x1400465e0  mov     [rsp-8+arg_18], rbx
0x1400465e5  push    rbp
0x1400465e6  push    rsi
0x1400465e7  push    rdi
0x1400465e8  push    r12
0x1400465ea  push    r13
0x1400465ec  push    r14
0x1400465ee  push    r15
0x1400465f0  lea     rbp, [rsp-100h]
0x1400465f8  sub     rsp, 200h
0x1400465ff  mov     rax, cs:__security_cookie
0x140046606  xor     rax, rsp
0x140046609  mov     [rbp+130h+var_40], rax
0x140046610  mov     [rsp+230h+var_1F0], r8
0x140046615  xor     r12d, r12d
0x140046618  or      qword ptr [rcx], 1000h
0x14004661f  mov     r14, rcx
0x140046622  mov     [rsp+230h+var_1D8], rcx
0x140046627  mov     r13d, 1
0x14004662d  mov     r11, 0FFFFFFFFFFFFFFFFh
0x140046634  test    rdx, rdx
0x140046637  jz      loc_1400466BC
0x14004663d  test    rdx, rdx
0x140046640  jz      short loc_140046668
0x140046642  mov     ebx, r12d
0x140046645  cmp     ebx, 8
0x140046648  jnb     loc_140046837
0x14004664e  mov     eax, ebx
0x140046650  lea     rsi, [rax+rax*2]
0x140046654  shl     rsi, 5
0x140046658  add     rsi, 8
0x14004665c  add     rsi, rdx
0x14004665f  cmp     [rsi], r12
0x140046662  jnz     short loc_14004666E
0x140046664  inc     ebx
0x140046666  jmp     short loc_140046645
0x140046668  mov     rsi, r12
0x14004666b  mov     ebx, r11d
0x14004666e  test    rsi, rsi
0x140046671  jz      short loc_1400466BC
0x140046673  test    byte ptr [rsi+30h], 1
0x140046677  jnz     loc_14004683F
0x14004667d  lea     eax, [rbx+rbx*2]
0x140046680  shl     eax, 5
0x140046683  add     eax, 8
0x140046686  cdqe
0x140046688  sub     rsi, rax
0x14004668b  mov     rdx, rsi
0x14004668e  test    rdx, rdx
0x140046691  jz      short loc_1400466BC
0x140046693  inc     ebx
0x140046695  cmp     ebx, 8
0x140046698  jnb     loc_14004682C
0x14004669e  lea     rsi, [rbx+rbx*2]
0x1400466a2  shl     rsi, 5
0x1400466a6  add     rsi, 8
0x1400466aa  add     rsi, rdx
0x1400466ad  cmp     qword ptr [rsi], 0
0x1400466b1  jnz     short loc_1400466B7
0x1400466b3  inc     ebx
0x1400466b5  jmp     short loc_140046695
0x1400466b7  test    rsi, rsi
0x1400466ba  jnz     short loc_140046673
0x1400466bc  mov     rdi, [rsp+230h+var_1F0]
0x1400466c1  cmp     dword ptr [rdi+70h], 64h ; 'd'
0x1400466c5  jnb     loc_1401FCD53
0x1400466cb  mov     rcx, [r14]
0x1400466ce  lea     rax, [rdi+40h]
0x1400466d2  mov     [rsp+230h+Event], rax
0x1400466d7  mov     rax, rcx
0x1400466da  shr     rax, 0Ah
0x1400466de  and     al, 1
0x1400466e0  shr     rcx, 0Bh
0x1400466e4  and     cl, 1
0x1400466e7  mov     byte ptr [rsp+230h+Event+9], al
0x1400466eb  mov     eax, cs:dword_140269184
0x1400466f1  mov     byte ptr [rsp+230h+Event+8], 0
0x1400466f6  mov     byte ptr [rsp+230h+Event+0Ah], cl
0x1400466fa  mov     [rsp+230h+var_1B8], r12d
0x1400466ff  mov     [rsp+230h+var_1C0], rdi
0x140046704  cmp     [rdi+70h], eax
0x140046707  ja      loc_140046796
0x14004670d  mov     rdx, [rdi+20h]
0x140046711  lea     r8, [rdi+20h]
0x140046715  cmp     rdx, r8
0x140046718  jz      loc_140046796
0x14004671e  cmp     [rdx], r8
0x140046721  jz      short loc_140046796
0x140046723  mov     [r8+8], rdx
0x140046727  mov     r11, rdx
0x14004672a  mov     r9, [rdx]
0x14004672d  cmp     r9, r8
0x140046730  jz      short loc_140046754
0x140046732  mov     rcx, [rdx-28h]
0x140046736  mov     r10, r9
0x140046739  sub     rcx, [r9-28h]
0x14004673d  test    rcx, rcx
0x140046740  jg      loc_140046C27
0x140046746  mov     rax, [r9]
0x140046749  mov     rdx, r10
0x14004674c  mov     r9, rax
0x14004674f  cmp     rax, r8
0x140046752  jnz     short loc_140046732
0x140046754  cmp     [r8+8], r11
0x140046758  jz      loc_140046EEC
0x14004675e  mov     [rdx], r12
0x140046761  mov     [r11+8], r12
0x140046765  mov     rdx, [r8+8]
0x140046769  cmp     qword ptr [rdx+8], 0
0x14004676e  jnz     loc_140046E04
0x140046774  mov     [r8], rdx
0x140046777  mov     rax, r8
0x14004677a  test    rdx, rdx
0x14004677d  jz      short loc_14004678F
0x14004677f  nop
0x140046780  mov     [rdx+8], rax
0x140046784  mov     rax, rdx
0x140046787  mov     rdx, [rdx]
0x14004678a  test    rdx, rdx
0x14004678d  jnz     short loc_140046780
0x14004678f  mov     [rax], r8
0x140046792  mov     [r8+8], rax
0x140046796  mov     rax, [rdi+20h]
0x14004679a  mov     [rdi+3F0h], rax
0x1400467a1  mov     [rdi+408h], rax
0x1400467a8  cmp     dword ptr [rdi+70h], 0
0x1400467ac  mov     [rdi+400h], r12d
0x1400467b3  jnz     loc_140046DBB
0x1400467b9  mov     rcx, [rsp+230h+Event]; Event
0x1400467be  xor     r8d, r8d; Wait
0x1400467c1  xor     edx, edx; Increment
0x1400467c3  call    cs:__imp_KeSetEvent
0x1400467ca  nop     dword ptr [rax+rax+00h]
0x1400467cf  cmp     byte ptr [rsp+230h+Event+8], 0
0x1400467d4  jnz     loc_1400471FB
0x1400467da  mov     rcx, [rsp+230h+var_1F0]
0x1400467df  cmp     dword ptr [rcx+378h], 0
0x1400467e6  jge     loc_140046E9E
0x1400467ec  mov     ebx, [rcx+3E8h]
0x1400467f2  test    ebx, ebx
0x1400467f4  jnz     loc_140046C36
0x1400467fa  and     qword ptr [r14], 0FFFFFFFFFFFFEFFFh
0x140046801  mov     rcx, [rbp+130h+var_40]
0x140046808  xor     rcx, rsp; StackCookie
0x14004680b  call    __security_check_cookie
0x140046810  mov     rbx, [rsp+230h+arg_18]
0x140046818  add     rsp, 200h
0x14004681f  pop     r15
0x140046821  pop     r14
0x140046823  pop     r13
0x140046825  pop     r12
0x140046827  pop     rdi
0x140046828  pop     rsi
0x140046829  pop     rbp
0x14004682a  retn
0x14004682c  mov     rdx, [rdx]
0x14004682f  mov     ebx, r11d
0x140046832  jmp     loc_14004668E
0x140046837  mov     rdx, [rdx]
0x14004683a  jmp     loc_14004663D
0x14004683f  mov     rax, [rsi]
0x140046842  cmp     [rax+20h], rax
0x140046846  jnz     loc_140046B08
0x14004684c  mov     rax, [rax+28h]
0x140046850  add     rax, 10h
0x140046854  mov     [rbp+130h+var_168], r14
0x140046858  mov     [rbp+130h+var_190], rax
0x14004685c  mov     ecx, [rax+0Ch]
0x14004685f  mov     edi, [rax+1Ch]
0x140046862  add     edi, ecx
0x140046864  mov     ecx, 0FFFFh; GroupNumber
0x140046869  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140046870  nop     dword ptr [rax+rax+00h]
0x140046875  mov     ecx, eax
0x140046877  mov     r15d, eax
0x14004687a  shr     ecx, 1
0x14004687c  cmp     ecx, 8
0x14004687f  ja      loc_140046A79
0x140046885  shr     ecx, 1
0x140046887  cmp     ecx, 4
0x14004688a  ja      loc_140046A7E
0x140046890  test    ecx, ecx
0x140046892  jz      loc_140047136
0x140046898  mov     eax, ecx
0x14004689a  cmp     edi, 64h ; 'd'
0x14004689d  jnb     loc_140047141
0x1400468a3  mov     r15d, r13d
0x1400468a6  mov     r14, [rbp+130h+var_190]
0x1400468aa  lea     rax, [rbp+130h+var_168]
0x1400468ae  xorps   xmm0, xmm0
0x1400468b1  mov     [rbp+130h+var_148], rax
0x1400468b5  lea     rax, ?BuildWritePlanListsParallel@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAUSmsWritePlan@@@Z; CmsBPlusTable::BuildWritePlanListsParallel(CmsTransactionContext *,CmsHashTable *,ulong,ulong,SmsWritePlan *)
0x1400468bc  mov     [rbp+130h+var_1A0], r14
0x1400468c0  mov     [rbp+130h+var_140], rax
0x1400468c4  lea     rcx, [rsp+230h+Event]; Event
0x1400468c9  lea     rax, [rbp+130h+var_190]
0x1400468cd  mov     [rbp+130h+var_1B0], r12d
0x1400468d1  mov     [rbp+130h+var_138], rax
0x1400468d5  xor     r8d, r8d; State
0x1400468d8  lea     rax, [rsp+230h+var_1F0]
0x1400468dd  movdqa  [rbp+130h+var_120], xmm0
0x1400468e2  mov     [rbp+130h+var_130], rax
0x1400468e6  xor     edx, edx; Type
0x1400468e8  xor     eax, eax
0x1400468ea  mov     [rbp+130h+var_110], r12
0x1400468ee  mov     [rsp+230h+var_1C0], rax
0x1400468f3  mov     [rbp+130h+var_108], 0
0x1400468fb  mov     [rbp+130h+var_100], r12
0x1400468ff  movups  [rbp+130h+var_F8], xmm0
0x140046903  mov     [rsp+230h+var_200], r12d
0x140046908  movups  [rbp+130h+var_E8], xmm0
0x14004690c  movups  [rbp+130h+var_D8], xmm0
0x140046910  movups  [rbp+130h+var_C8], xmm0
0x140046914  movups  xmmword ptr [rsp+230h+Event], xmm0
0x140046919  call    cs:__imp_KeInitializeEvent
0x140046920  nop     dword ptr [rax+rax+00h]
0x140046925  cmp     r15d, 1
0x140046929  ja      loc_1400470EB
0x14004692f  lea     rdi, [rbp+130h+var_120]
0x140046933  mov     r15d, r13d
0x140046936  mov     [rbp+130h+P], rdi
0x14004693a  mov     eax, r13d
0x14004693d  mov     r8d, r12d
0x140046940  mov     edx, r13d
0x140046943  mov     rcx, rdi
0x140046946  mov     [rsp+230h+var_200], edx
0x14004694a  lea     r10d, [rax-1]
0x14004694e  mov     [rbp+130h+var_188], rdi
0x140046952  mov     r9, rdi
0x140046955  mov     [rsp+230h+var_1DC], r10d
0x14004695a  lea     rdx, [rcx+1Ch]
0x14004695e  mov     [rbp+130h+var_198], rdx
0x140046962  mov     eax, r8d
0x140046965  imul    rcx, rax, 68h ; 'h'
0x140046969  lea     r12, [rcx+r9]
0x14004696d  lea     r9, [rcx+rdx]
0x140046971  xor     edx, edx
0x140046973  lea     rax, [rbp+130h+var_148]
0x140046977  mov     [r12], rax
0x14004697b  lea     rax, [rbp+130h+var_1B0]
0x14004697f  mov     [r12+8], rax
0x140046984  lea     rax, [rsp+230h+var_200]
0x140046989  mov     [r12+10h], rax
0x14004698e  lea     rax, [rsp+230h+Event]
0x140046993  mov     [r12+20h], rax
0x140046998  mov     eax, [r14+18h]
0x14004699c  add     eax, [r14+8]
0x1400469a0  div     r15d
0x1400469a3  mov     ecx, eax
0x1400469a5  imul    ecx, r8d
0x1400469a9  mov     [r12+18h], ecx
0x1400469ae  lea     ecx, [r8+1]
0x1400469b2  mov     [rsp+230h+var_1E0], ecx
0x1400469b6  imul    ecx, eax
0x1400469b9  mov     [r9], ecx
0x1400469bc  cmp     r8d, r10d
0x1400469bf  jnz     short loc_1400469C8
0x1400469c1  mov     dword ptr [r9], 0FFFFFFFFh
0x1400469c8  cmp     r15d, 1
0x1400469cc  ja      loc_140047072
0x1400469d2  mov     rax, [r12]
0x1400469d6  mov     ecx, [r12+1Ch]
0x1400469db  mov     [rbp+130h+var_1AC], ecx
0x1400469de  mov     ecx, [r12+18h]
0x1400469e3  mov     [rbp+130h+var_1A8], ecx
0x1400469e6  mov     rcx, [rax+18h]
0x1400469ea  mov     [rbp+130h+var_158], rcx
0x1400469ee  mov     rcx, [rax+10h]
0x1400469f2  mov     [rbp+130h+var_150], rcx
0x1400469f6  mov     rcx, [rax+8]
0x1400469fa  mov     rax, [rax]
0x1400469fd  mov     [rbp+130h+var_178], rcx
0x140046a01  xor     ecx, ecx; ProcNumber
0x140046a03  mov     rax, [rax]
0x140046a06  mov     [rbp+130h+var_160], rax
0x140046a0a  mov     r13, [rax+8]
0x140046a0e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140046a15  nop     dword ptr [rax+rax+00h]
0x140046a1a  xor     edx, edx
0x140046a1c  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140046a22  lea     rdi, [rdx+rdx*2]
0x140046a26  shl     rdi, 6
0x140046a2a  add     rdi, cs:qword_140269408
0x140046a31  cmp     dword ptr [rdi], 0DD0h
0x140046a37  jnb     short loc_140046A88
0x140046a39  xor     edi, edi
0x140046a3b  mov     edx, 0DE0h
0x140046a40  mov     ecx, 42h ; 'B'
0x140046a45  mov     r8d, 6950534Dh
0x140046a4b  call    cs:__imp_ExAllocatePool2
0x140046a52  nop     dword ptr [rax+rax+00h]
0x140046a57  mov     r14, rax
0x140046a5a  test    al, 0Fh
0x140046a5c  jnz     loc_1401FCD46
0x140046a62  test    rax, rax
0x140046a65  jz      loc_140046EF5
0x140046a6b  lea     rcx, [rax+10h]; void *
0x140046a6f  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x140046a74  jmp     loc_14004704F
0x140046a79  mov     ecx, 8
  ... truncated ...
```
