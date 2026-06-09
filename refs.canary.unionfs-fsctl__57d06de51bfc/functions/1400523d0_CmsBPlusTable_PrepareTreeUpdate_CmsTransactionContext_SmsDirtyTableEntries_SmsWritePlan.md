# CmsBPlusTable::PrepareTreeUpdate(CmsTransactionContext *,SmsDirtyTableEntries *,SmsWritePlan *)

- ea: `0x1400523d0`
- end: `0x14005301e`
- name: `?PrepareTreeUpdate@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAUSmsDirtyTableEntries@@PEAUSmsWritePlan@@@Z`
- size: `3150`
- prototype: `void __fastcall(struct CmsTransactionContext *, struct SmsDirtyTableEntries *, struct SmsWritePlan *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14013ff9c`

## callees

- `0x140013ff0`
- `0x1400145f4`
- `0x1400340e0`
- `0x1400523d0`
- `0x140053024`
- `0x1400530a0`
- `0x140054d40`
- `0x140056b20`
- `0x140071100`
- `0x140082090`
- `0x1400b5884`
- `0x1400b5e44`
- `0x1400c8574`
- `0x14013ef24`
- `0x14013f150`
- `0x1401e9ce0`
- `0x1401e9dc0`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x140052e08`
- `ntoskrnl!IoGetActivityIdThread` at `0x140052e08`
- `ntoskrnl!KeSetEvent` at `0x1400525b3`
- `ntoskrnl!KeSetEvent` at `0x140052975`
- `ntoskrnl!KeSetEvent` at `0x1400525b3`
- `ntoskrnl!KeSetEvent` at `0x140052975`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140052f1e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140052f1e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140052e1c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140052e1c`
- `ntoskrnl!ExAllocatePool2` at `0x140052835`
- `ntoskrnl!ExAllocatePool2` at `0x140052ea3`
- `ntoskrnl!ExAllocatePool2` at `0x1401f4369`
- `ntoskrnl!ExAllocatePool2` at `0x1401f4482`
- `ntoskrnl!ExAllocatePool2` at `0x140052835`
- `ntoskrnl!ExAllocatePool2` at `0x140052ea3`
- `ntoskrnl!ExAllocatePool2` at `0x1401f4369`
- `ntoskrnl!ExAllocatePool2` at `0x1401f4482`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140052659`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140052659`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400527f8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400527f8`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140052e5e`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140052e5e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f432e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f432e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140052f3c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140052f3c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400529b5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052c50`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400529b5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052c50`
- `ntoskrnl!KeInitializeEvent` at `0x140052709`
- `ntoskrnl!KeInitializeEvent` at `0x140052b91`
- `ntoskrnl!KeInitializeEvent` at `0x140052709`
- `ntoskrnl!KeInitializeEvent` at `0x140052b91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052f57`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f43ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052f57`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f43ed`

## string_xrefs

- `0x1401f434c`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
void __fastcall CmsBPlusTable::PrepareTreeUpdate(
        struct CmsTransactionContext *a1,
        struct SmsDirtyTableEntries **a2,
        struct SmsWritePlan *a3)
{
  struct CmsTransactionContext *v3; // r14
  __int64 i; // rbx
  unsigned __int8 *v5; // rsi
  char *v6; // rdx
  struct SmsWritePlan *v7; // rdi
  __int64 v8; // rcx
  _QWORD **v9; // rdx
  _QWORD *v10; // r8
  _QWORD *v11; // r11
  _QWORD *j; // r9
  _QWORD *k; // rdx
  _QWORD *m; // rax
  __int64 v15; // rax
  unsigned __int8 v16; // dl
  struct SmsWritePlan *v17; // rcx
  unsigned int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned int v21; // edi
  ULONG ActiveProcessorCount; // r15d
  int v23; // ecx
  int v24; // eax
  __int64 v25; // rdi
  __int128 *p_P; // r13
  int v27; // eax
  int v28; // edx
  int v29; // r10d
  ULONG v30; // r8d
  __int128 *v31; // r9
  struct CmsTransactionContext *v32; // rdx
  __int64 v33; // rcx
  char *v34; // r12
  char *v35; // r9
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 *v41; // rax
  __int64 v42; // rdi
  __int64 v43; // rdx
  __int64 v44; // rax
  PSLIST_ENTRY v45; // r14
  int v46; // ecx
  __int64 v47; // rdi
  struct _SLIST_ENTRY *v48; // r14
  __int64 v49; // rax
  __int64 v50; // r10
  _QWORD *v51; // rdx
  __int64 v52; // r9
  __int64 v53; // r8
  char v54; // di
  void (__fastcall *v55)(struct _SLIST_ENTRY *, _QWORD, __int64, __int64, _QWORD); // rax
  int v56; // edx
  int v57; // r10d
  unsigned __int8 *v58; // r9
  __int64 v59; // rax
  int v60; // r8d
  __int64 v61; // rdx
  int v62; // eax
  __int64 v63; // rdx
  unsigned __int8 v64; // al
  _QWORD *v65; // r13
  unsigned __int64 v66; // rsi
  unsigned int v67; // r15d
  enum _WORK_QUEUE_TYPE v68; // r9d
  __int64 v69; // rcx
  _OWORD *v70; // r12
  __int64 v71; // r14
  _QWORD *v72; // rdx
  _OWORD *v73; // rdi
  struct CmsTransactionContext *Tx; // rax
  CmsTransactionContext *v75; // rbx
  char *v76; // rsi
  _QWORD *v77; // r9
  _QWORD *v78; // r11
  _QWORD *v79; // rbx
  _QWORD *v80; // r10
  bool v81; // zf
  unsigned int v82; // edi
  unsigned int v83; // r14d
  __int64 v84; // rsi
  char *v85; // rbx
  unsigned int v86; // esi
  __int128 *ActivityIdThread; // r14
  __int128 v88; // xmm0
  size_t v89; // rdi
  __int128 *Pool2; // rax
  struct _NPAGED_LOOKASIDE_LIST *v91; // rcx
  struct _SLIST_ENTRY *v92; // rax
  __int64 v93; // rbx
  unsigned int v94; // eax
  __int64 v95; // rbx
  unsigned int v96; // eax
  __int64 v97; // rax
  __int64 v98; // rsi
  enum _WORK_QUEUE_TYPE v99; // r9d
  size_t v100; // rdi
  _OWORD *v101; // rax
  _DWORD v102[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct SmsWritePlan *v103[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct CmsTransactionContext *v104; // [rsp+50h] [rbp-B0h]
  ULONG v105; // [rsp+58h] [rbp-A8h]
  int v106; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v108; // [rsp+78h] [rbp-88h]
  __int64 v109; // [rsp+80h] [rbp-80h]
  struct CmsTransactionContext *v110; // [rsp+88h] [rbp-78h] BYREF
  int v111; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v112; // [rsp+94h] [rbp-6Ch]
  unsigned int v113; // [rsp+98h] [rbp-68h]
  __int64 v114; // [rsp+A0h] [rbp-60h]
  _QWORD v115[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v116; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v117[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct CmsTransactionContext *v118; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v119; // [rsp+D8h] [rbp-28h]
  _QWORD *v120; // [rsp+E0h] [rbp-20h]
  _QWORD v121[5]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 P; // [rsp+110h] [rbp+10h] BYREF
  __int64 v123; // [rsp+120h] [rbp+20h]
  __int64 v124; // [rsp+128h] [rbp+28h]
  __int64 v125; // [rsp+130h] [rbp+30h]
  __int128 v126; // [rsp+138h] [rbp+38h]
  __int128 v127; // [rsp+148h] [rbp+48h]
  __int128 v128; // [rsp+158h] [rbp+58h]
  __int128 v129; // [rsp+168h] [rbp+68h]
  _OWORD v130[7]; // [rsp+180h] [rbp+80h] BYREF

  v103[0] = a3;
  *(_QWORD *)a1 |= 0x1000uLL;
  v3 = a1;
  v104 = a1;
  if ( !a2 )
    goto LABEL_17;
  while ( a2 )
  {
    LODWORD(i) = 0;
    while ( (unsigned int)i < 8 )
    {
      v5 = (unsigned __int8 *)&a2[12 * (unsigned int)i + 1];
      if ( *(_QWORD *)v5 )
        goto LABEL_8;
      LODWORD(i) = i + 1;
    }
    a2 = (struct SmsDirtyTableEntries **)*a2;
  }
  v5 = 0;
  LODWORD(i) = -1;
LABEL_8:
  if ( !v5 )
    goto LABEL_17;
  while ( 2 )
  {
    if ( (v5[48] & 1) == 0 )
      goto LABEL_10;
    v19 = *(_QWORD *)v5;
    if ( *(_QWORD *)(v19 + 32) != v19 )
      goto LABEL_69;
    v20 = *(_QWORD *)(v19 + 40) + 16LL;
    v118 = v3;
    v116 = v20;
    v21 = *(_DWORD *)(v20 + 12) + *(_DWORD *)(v20 + 28);
    ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
    if ( ActiveProcessorCount >> 1 > 8 )
    {
      v23 = 8;
      goto LABEL_57;
    }
    v23 = ActiveProcessorCount >> 2;
    if ( ActiveProcessorCount >> 2 > 4 )
    {
LABEL_57:
      v24 = 4;
      goto LABEL_43;
    }
    if ( v23 )
    {
      v24 = ActiveProcessorCount >> 2;
    }
    else
    {
      v24 = 1;
      v23 = 1;
    }
LABEL_43:
    if ( v21 >= 0x64 )
    {
      if ( v21 <= 0x5DC )
      {
        ActiveProcessorCount = v24;
        if ( v21 > 0x3E8 )
          ActiveProcessorCount = v23;
      }
    }
    else
    {
      ActiveProcessorCount = 1;
    }
    v25 = v116;
    v121[0] = &v118;
    v114 = v116;
    v121[1] = CmsBPlusTable::BuildWritePlanListsParallel;
    v111 = 0;
    v121[2] = &v116;
    P = 0;
    v121[3] = v103;
    v123 = 0;
    v124 = 0;
    v125 = 0;
    v126 = 0;
    v102[0] = 0;
    v127 = 0;
    v128 = 0;
    v129 = 0;
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    if ( ActiveProcessorCount > 1 )
    {
      v89 = 104LL * ActiveProcessorCount;
      if ( !is_mul_ok(ActiveProcessorCount, 0x68u) )
        v89 = -1;
      Pool2 = (__int128 *)ExAllocatePool2(66, v89, 1766871885);
      p_P = Pool2;
      if ( Pool2 )
      {
        memset(Pool2, 0, v89);
        _____builtin_array_init_helper_UWorker__1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable____QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__CmsHashTable__QEAAJK__QEAV_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV2___QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV6_AEAPEAU7__Z__Z___YAXPEAUWorker__1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable____QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__CmsHashTable__QEAAJK__QEAV_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV1___QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__Z__K_Z(
          p_P,
          ActiveProcessorCount);
        v25 = v114;
        v27 = ActiveProcessorCount;
        v28 = ActiveProcessorCount;
        goto LABEL_47;
      }
      v25 = v114;
    }
    p_P = &P;
    ActiveProcessorCount = 1;
    v27 = 1;
    v28 = 1;
LABEL_47:
    v102[0] = v28;
    v29 = v27 - 1;
    v30 = 0;
    v31 = p_P;
    v106 = v27 - 1;
    v32 = (struct CmsTransactionContext *)((char *)p_P + 28);
    v110 = (struct CmsTransactionContext *)((char *)p_P + 28);
    do
    {
      v33 = 104LL * v30;
      v34 = (char *)v31 + v33;
      v35 = (char *)v32 + v33;
      HIDWORD(v37) = 0;
      *(_QWORD *)v34 = v121;
      *((_QWORD *)v34 + 1) = &v111;
      *((_QWORD *)v34 + 2) = v102;
      *((_QWORD *)v34 + 4) = &Event;
      LODWORD(v37) = (*(_DWORD *)(v25 + 24) + *(_DWORD *)(v25 + 8)) % ActiveProcessorCount;
      v36 = (*(_DWORD *)(v25 + 24) + *(_DWORD *)(v25 + 8)) / ActiveProcessorCount;
      *((_DWORD *)v34 + 6) = v30 * v36;
      v105 = v30 + 1;
      v38 = v36 * (v30 + 1);
      *(_DWORD *)v35 = v38;
      if ( v30 == v29 )
        *(_DWORD *)v35 = -1;
      if ( ActiveProcessorCount <= 1 )
        goto LABEL_51;
      ActivityIdThread = (__int128 *)IoGetActivityIdThread(v38, v37);
      if ( ActivityIdThread && KeGetCurrentIrql() < 2u )
        v88 = *ActivityIdThread;
      else
        v88 = 0;
      *(_OWORD *)(v34 + 40) = v88;
      *((_QWORD *)v34 + 12) = v34;
      *((_QWORD *)v34 + 11) = __lambda_invoker_cdecl___lambda_1___1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_A6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAUSmsWritePlan___ZAEAPEAU3__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable__A6AX01KKPEAUSmsWritePlan___ZAEAPEAU5__Z__CmsHashTable__QEAAJK__QEAV1_1____ParallelTuPageTableWork_A6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAUSmsWritePlan___ZAEAPEAU3__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV2_A6AX01KKPEAUSmsWritePlan___ZAEAPEAU5__Z__Z_SA_PEAX_Z;
      *((_QWORD *)v34 + 10) = v34 + 40;
      *((_QWORD *)v34 + 9) = MspWorkerRoutine;
      *((_QWORD *)v34 + 7) = 0;
      if ( !(unsigned __int8)ExTryQueueWorkItem(v34 + 56, 0) )
      {
LABEL_51:
        v39 = *(_QWORD *)v34;
        v112 = *((_DWORD *)v34 + 7);
        v113 = *((_DWORD *)v34 + 6);
        v120 = *(_QWORD **)(v39 + 24);
        v117[0] = *(_QWORD *)(v39 + 16);
        v40 = *(_QWORD *)(v39 + 8);
        v41 = *(__int64 **)v39;
        v115[0] = v40;
        v119 = *v41;
        v109 = *(_QWORD *)(v119 + 8);
        v42 = qword_140262408 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
        if ( *(_DWORD *)v42 < 0xD50u )
        {
          v42 = 0;
          v43 = 3424;
LABEL_53:
          v44 = ExAllocatePool2(66, v43, 1766871885);
          v45 = (PSLIST_ENTRY)v44;
          if ( (v44 & 0xF) != 0 )
            MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
          if ( !v44 )
            goto LABEL_63;
          CmsTransactionContext::InitializeTransactionMemoryBuffer((void *)(v44 + 16));
LABEL_130:
          v45->Next = (struct _SLIST_ENTRY *)v42;
          v48 = v45 + 1;
          if ( v48 )
          {
            v47 = v109;
            v49 = 0x8000;
            v48->Next = (struct _SLIST_ENTRY *)0x8000;
LABEL_64:
            v50 = v119;
            v51 = (_QWORD *)v117[0];
            v52 = v112;
            v53 = v113;
            *((_QWORD *)&v48->Next + 1) = v47;
            v54 = *((_BYTE *)&v48[13].Next + 12);
            v109 = v49;
            v48->Next = (struct _SLIST_ENTRY *)(*(_QWORD *)v50 | v49);
            v55 = (void (__fastcall *)(struct _SLIST_ENTRY *, _QWORD, __int64, __int64, _QWORD))v115[0];
            *((_BYTE *)&v48[13].Next + 12) = *(_BYTE *)(v50 + 220);
            v55(v48, *v51, v53, v52, *v120);
            CmsTransactionContext::Commit((CmsTransactionContext *)v48, 0, 0, 0);
            v48->Next = (struct _SLIST_ENTRY *)v109;
            *((_BYTE *)&v48[13].Next + 12) = v54;
            CmsTransactionContext::Release((CmsTransactionContext *)v48);
            if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)v34 + 2), 0xFFFFFFFF) == 1 )
              KeSetEvent(*((PRKEVENT *)v34 + 4), 0, 0);
            goto LABEL_66;
          }
LABEL_63:
          v47 = v109;
          v48 = (struct _SLIST_ENTRY *)CmsReservedPool::AllocateFromPool((CmsReservedPool *)(v109 + 160));
          CmsTransactionContext::InitializeTransactionMemoryBuffer(v48);
          v49 = 268468224;
          v48->Next = (struct _SLIST_ENTRY *)268468224;
          goto LABEL_64;
        }
        if ( !*(_BYTE *)(v42 + 8) )
        {
          if ( (int)*(_QWORD *)(v42 + 88) > (int)HIDWORD(*(_QWORD *)(v42 + 88)) )
          {
            v46 = _InterlockedDecrement((volatile signed __int32 *)(v42 + 88));
            if ( v46 >= *(_DWORD *)(v42 + 92) && v46 >= 0 )
            {
              v45 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v42 + 64));
              goto LABEL_129;
            }
            _InterlockedIncrement((volatile signed __int32 *)(v42 + 88));
          }
LABEL_62:
          v43 = *(unsigned int *)(v42 + 4);
          goto LABEL_53;
        }
        v91 = (struct _NPAGED_LOOKASIDE_LIST *)(v42 + 64);
        if ( *(_BYTE *)(v42 + 9) )
          v92 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v91);
        else
          v92 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v91);
        v45 = v92;
        CmsTransactionContext::InitializeTransactionMemoryBuffer(&v92->Next + 1);
LABEL_129:
        if ( v45 )
          goto LABEL_130;
        goto LABEL_62;
      }
LABEL_66:
      v30 = v105;
      v31 = p_P;
      v25 = v114;
      v32 = v110;
      v29 = v106;
    }
    while ( v105 < ActiveProcessorCount );
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( p_P && p_P != &P )
      ExFreePoolWithTag(p_P, 0);
    v3 = v104;
LABEL_69:
    if ( v5[89] && (v5[48] & 8) != 0 )
    {
      v56 = 0;
      v57 = 1;
      v58 = v5;
      if ( (*(_DWORD *)v3 & 0x400LL) != 0 && (*(_BYTE *)(*(_QWORD *)v5 + 14LL) & 0x38) == 0x18 )
      {
        v63 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 1) + 3336LL) + 16LL);
        v64 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v63 + 32) + 200LL) + 88LL);
        if ( v64 <= *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v63 + 40) + 200LL) + 88LL) )
          v64 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v63 + 40) + 200LL) + 88LL);
        v56 = v64 + 1;
      }
      while ( 1 )
      {
        v59 = *(_QWORD *)(*(_QWORD *)v58 + 112LL);
        if ( *(_BYTE *)(v59 + 11) )
          break;
        v58 = *(unsigned __int8 **)(**(_QWORD **)(v59 + 40) + 200LL);
        v57 += v58[88] + 1;
      }
      v60 = v57 + v56;
      v61 = 24LL * (v57 + v56);
      *((_QWORD *)v5 + 10) = *(_QWORD *)((char *)v103[0] + v61 + 128);
      *(_QWORD *)((char *)v103[0] + v61 + 128) = v5;
      ++*(_DWORD *)((char *)v103[0] + v61 + 140);
      v62 = *((_DWORD *)v103[0] + 222);
      if ( v62 <= v60 )
        v62 = v60;
      *((_DWORD *)v103[0] + 222) = v62;
    }
LABEL_10:
    v6 = (char *)&v5[-96 * (int)i - 8];
LABEL_11:
    if ( v6 )
    {
      for ( i = (unsigned int)(i + 1); ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= 8 )
        {
          v6 = *(char **)v6;
          LODWORD(i) = -1;
          goto LABEL_11;
        }
        v5 = (unsigned __int8 *)&v6[96 * i + 8];
        if ( *(_QWORD *)v5 )
          break;
      }
      if ( v5 )
        continue;
    }
    break;
  }
LABEL_17:
  v7 = v103[0];
  if ( *((_DWORD *)v103[0] + 28) >= 0x64u && (v97 = ExAllocatePool2(66, 96, 1766871885), (v98 = v97) != 0) )
  {
    *(_BYTE *)(v97 + 9) = 0;
    *(_DWORD *)(v97 + 10) = 0;
    *(_WORD *)(v97 + 14) = 0;
    *(_DWORD *)(v97 + 28) = 0;
    memset((void *)(v97 + 32), 0, 0x40u);
    *(_BYTE *)(v98 + 8) = 1;
    *(_QWORD *)v98 = (char *)v7 + 64;
    *(_DWORD *)(v98 + 24) = 0;
    *(_QWORD *)(v98 + 16) = v7;
    *(_BYTE *)(v98 + 9) = (*(_DWORD *)v3 & 0x400LL) != 0;
    *(_BYTE *)(v98 + 10) = (*(_DWORD *)v3 & 0x800LL) != 0;
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
    v8 = *(_QWORD *)v3;
    *(_QWORD *)&Event.Header.Lock = (char *)v7 + 64;
    BYTE1(Event.Header.WaitListHead.Flink) = (v8 & 0x400) != 0;
    LOBYTE(Event.Header.WaitListHead.Flink) = 0;
    BYTE2(Event.Header.WaitListHead.Flink) = (v8 & 0x800) != 0;
    v108 = 0;
    Event.Header.WaitListHead.Blink = (struct _LIST_ENTRY *)v7;
    if ( *((_DWORD *)v7 + 28) <= (unsigned int)dword_140262184 )
    {
      v9 = (_QWORD **)*((_QWORD *)v7 + 4);
      v10 = (_QWORD *)((char *)v7 + 32);
      if ( v9 != (_QWORD **)((char *)v7 + 32) && *v9 != v10 )
      {
        *((_QWORD *)v7 + 5) = v9;
        v11 = v9;
        for ( j = *v9; j != v10; j = (_QWORD *)*j )
        {
          if ( (__int64)*(v9 - 5) - *(j - 5) > 0 )
          {
            v11[1] = j;
            v11 = j;
            *v9 = 0;
          }
          v9 = (_QWORD **)j;
        }
        if ( *((_QWORD **)v7 + 5) == v11 )
        {
          *((_QWORD *)v7 + 5) = v9;
        }
        else
        {
          *v9 = 0;
          v11[1] = 0;
          for ( k = (_QWORD *)*((_QWORD *)v7 + 5); k[1]; k = (_QWORD *)*((_QWORD *)v7 + 5) )
          {
            v76 = (char *)v7 + 32;
            do
            {
              v77 = (_QWORD *)k[1];
              v78 = (_QWORD *)v77[1];
              if ( (__int64)(*(k - 5) - *(v77 - 5)) > 0 )
              {
                v79 = (_QWORD *)k[1];
                v77 = (_QWORD *)*v77;
              }
              else
              {
                v79 = k;
                k = (_QWORD *)*k;
              }
              v80 = v79;
              v81 = k == 0;
              if ( k )
              {
                do
                {
                  if ( !v77 )
                    break;
                  if ( (__int64)(*(k - 5) - *(v77 - 5)) > 0 )
                  {
                    *v80 = v77;
                    v80 = v77;
                    v77 = (_QWORD *)*v77;
                  }
                  else
                  {
                    *v80 = k;
                    v80 = k;
                    k = (_QWORD *)*k;
                  }
                }
                while ( k );
                v81 = k == 0;
              }
              if ( v81 )
                k = v77;
              *v80 = k;
              *((_QWORD *)v76 + 1) = v79;
              v79[1] = v78;
              if ( !v78 )
                break;
              v76 = (char *)v79;
              k = v78;
            }
            while ( v78[1] );
          }
          *v10 = k;
          for ( m = (_QWORD *)((char *)v7 + 32); k; k = (_QWORD *)*k )
          {
            k[1] = m;
            m = k;
          }
          *m = v10;
          *((_QWORD *)v7 + 5) = m;
        }
      }
    }
    v15 = *((_QWORD *)v7 + 4);
    *((_QWORD *)v7 + 126) = v15;
    *((_QWORD *)v7 + 129) = v15;
    v81 = *((_DWORD *)v7 + 28) == 0;
    *((_DWORD *)v7 + 256) = 0;
    if ( !v81 && (*(_DWORD *)(*(_QWORD *)v7 + 3460LL) & 0x400000) == 0 )
    {
      if ( LOBYTE(Event.Header.WaitListHead.Flink) )
      {
        Tx = CmsTransactionContext::MakeTx(*(struct CmsVolume **)v7);
        v75 = Tx;
        if ( Tx )
        {
          if ( BYTE1(Event.Header.WaitListHead.Flink) )
            *(_QWORD *)Tx |= 0x20000C00uLL;
          if ( BYTE2(Event.Header.WaitListHead.Flink) )
            *(_QWORD *)Tx |= 0x20000800uLL;
          CmsBPlusTable::WriteBindableUpdate(Tx, v7, 0, 0);
          CmsTransactionContext::Commit(v75, 0, 0, 0);
          CmsTransactionContext::Release(v75);
          _InterlockedIncrement(&dword_1402625C0);
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)&DbgCounts + v108 + 54);
        }
      }
      else
      {
        _InterlockedIncrement(&dword_1402625C8);
      }
    }
    KeSetEvent(*(PRKEVENT *)&Event.Header.Lock, 0, 0);
    if ( LOBYTE(Event.Header.WaitListHead.Flink) )
      ExFreePoolWithTag(&Event, 0);
  }
  v17 = v103[0];
  if ( *((int *)v103[0] + 222) >= 0 )
  {
    v82 = 0;
    do
    {
      v83 = *((_DWORD *)v17 + 6 * v82 + 34);
      v84 = 24LL * v82;
      if ( v83 )
      {
        v93 = *((_QWORD *)v17 + 3 * v82 + 15);
        v110 = v104;
        v94 = CmsBPlusTable::DeterminePageTableWorkerCount(v83, v16);
        Event.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)CmsBPlusTable::ChecksumWritePlanPagesParallel;
        *(_QWORD *)&Event.Header.Lock = &v110;
        Event.Header.WaitListHead.Blink = (struct _LIST_ENTRY *)v103;
        ___ParallelListWork__0FI_USmsPage__V_lambda_1___1____ParallelTuListWork__0FI_USmsPage__A6AXPEAVCmsTransactionContext__PEAU1_1PEAUSmsWritePlan___ZAEAPEAU3__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011PEAUSmsWritePlan___ZAEAPEAU5__Z___YAJKKPEAUSmsPage____QEAV_lambda_1___1____ParallelTuListWork__0FI_USmsPage__A6AXPEAVCmsTransactionContext__PEAU1_1PEAUSmsWritePlan___ZAEAPEAU3__CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100PEAUSmsWritePlan___ZAEAPEAU4__Z__Z(
          v94,
          v83,
          v93,
          &Event);
        v17 = v103[0];
      }
      v3 = v104;
      v85 = (char *)v17 + v84;
      v86 = *(_DWORD *)((char *)v17 + v84 + 140);
      if ( v86 )
      {
        v95 = *((_QWORD *)v85 + 16);
        v115[0] = v104;
        v96 = CmsBPlusTable::DeterminePageTableWorkerCount(v86, v16);
        v117[1] = CmsBPlusTable::ChecksumWritePlanRootsParallel;
        v117[0] = v115;
        ___ParallelListWork__0FA_USmsDirtyTableEntry__V_lambda_1___1____ParallelTuListWork__0FA_USmsDirtyTableEntry__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011_Z_Z___YAJKKPEAUSmsDirtyTableEntry____QEAV_lambda_1___1____ParallelTuListWork__0FA_USmsDirtyTableEntry__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100_Z_Z__Z(
          v96,
          v86,
          v95,
          v117);
        v17 = v103[0];
      }
      if ( v82 )
        --v82;
      else
        v82 = *((_DWORD *)v17 + 222);
    }
    while ( v82 );
  }
  v18 = *((_DWORD *)v17 + 250);
  if ( v18 )
  {
    v65 = (_QWORD *)*((_QWORD *)v17 + 123);
    v115[0] = &v110;
    v110 = v3;
    v115[1] = CmsBPlusTable::UnlinkAllOldPagesParallel;
    v66 = CmsBPlusTable::DeterminePageTableWorkerCount(v18, v16);
    memset(v130, 0, sizeof(v130));
    v106 = 0;
    v102[0] = 0;
    v67 = 0;
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    if ( (unsigned int)v66 <= 1 )
      goto LABEL_84;
    v100 = 112 * v66;
    if ( !is_mul_ok(v66, 0x70u) )
      v100 = -1;
    v101 = (_OWORD *)ExAllocatePool2(66, v100, 1766871885);
    v70 = v101;
    if ( v101 )
    {
      memset(v101, 0, v100);
      _____builtin_array_init_helper_UWorker__1____ParallelListWork__0A_U_LIST_ENTRY__V_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011_Z_Z___YAJKKPEAU_LIST_ENTRY____QEAV_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100_Z_Z__Z___YAXPEAUWorker__1____ParallelListWork__0A_U_LIST_ENTRY__V_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011_Z_Z___YAJKKPEAU_LIST_ENTRY____QEAV_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100_Z_Z__Z__K_Z(
        v70,
        v66);
      v69 = 1;
    }
    else
    {
LABEL_84:
      v69 = 1;
      v70 = v130;
      LODWORD(v66) = 1;
    }
    v102[0] = v66;
    if ( v18 / (unsigned int)v66 > 1 )
      v69 = v18 / (unsigned int)v66;
    v105 = v69;
    v71 = 0;
    do
    {
      v72 = v65;
      if ( ++v67 == (_DWORD)v66 )
        v69 = v18;
      if ( (_DWORD)v69 )
      {
        do
        {
          v65 = (_QWORD *)*v65;
          --v18;
          v81 = (_DWORD)v69 == 1;
          v69 = (unsigned int)(v69 - 1);
        }
        while ( !v81 );
      }
      v73 = &v70[7 * v71];
      *(_QWORD *)v73 = v115;
      *((_QWORD *)v73 + 1) = &v106;
      *((_QWORD *)v73 + 2) = v102;
      *((_QWORD *)v73 + 5) = &Event;
      *((_QWORD *)v73 + 3) = v72;
      *((_QWORD *)v73 + 4) = v65;
      if ( (unsigned int)v66 <= 1
        || !MsInitializeAndTryQueueWorkItem(
              (struct _MS_WORK_QUEUE_ITEM *)(v73 + 3),
              __lambda_invoker_cdecl___lambda_1___1____ParallelListWork__0A_U_LIST_ENTRY__V_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011_Z_Z___YAJKKPEAU_LIST_ENTRY____QEAV1_1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100_Z_Z__Z_SA_PEAX_Z,
              &v70[7 * v71],
              v68) )
      {
        __R_lambda_1___1____ParallelListWork__0A_U_LIST_ENTRY__V_lambda_1___1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAU1_KA6AX011_Z_Z___YAJKKPEAU_LIST_ENTRY____QEAV0_1____ParallelTuListWork__0A_U_LIST_ENTRY__A6AXPEAVCmsTransactionContext__PEAU1_1_Z__V_CmsBPlusTable__CAXPEAVCmsTransactionContext__0KA6AX100_Z_Z__Z_QEBA_PEAX_Z(
          v69,
          &v70[7 * v71]);
      }
      v69 = v105;
      ++v71;
    }
    while ( v67 < (unsigned int)v66 );
    v3 = v104;
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( v70 && v70 != v130 )
      ExFreePoolWithTag(v70, 0);
  }
  *(_QWORD *)v3 &= ~0x1000uLL;
}

```

## disassembly

```asm
0x1400523d0  mov     [rsp-8+arg_18], rbx
0x1400523d5  push    rbp
0x1400523d6  push    rsi
0x1400523d7  push    rdi
0x1400523d8  push    r12
0x1400523da  push    r13
0x1400523dc  push    r14
0x1400523de  push    r15
0x1400523e0  lea     rbp, [rsp-100h]
0x1400523e8  sub     rsp, 200h
0x1400523ef  mov     rax, cs:__security_cookie
0x1400523f6  xor     rax, rsp
0x1400523f9  mov     [rbp+130h+var_40], rax
0x140052400  mov     [rsp+230h+var_1F0], r8
0x140052405  xor     r13d, r13d
0x140052408  or      qword ptr [rcx], 1000h
0x14005240f  mov     r14, rcx
0x140052412  mov     [rsp+230h+var_1E0], rcx
0x140052417  mov     r12d, 1
0x14005241d  mov     r11, 0FFFFFFFFFFFFFFFFh
0x140052424  test    rdx, rdx
0x140052427  jz      loc_1400524AC
0x14005242d  test    rdx, rdx
0x140052430  jz      short loc_140052458
0x140052432  mov     ebx, r13d
0x140052435  cmp     ebx, 8
0x140052438  jnb     loc_140052627
0x14005243e  mov     eax, ebx
0x140052440  lea     rsi, [rax+rax*2]
0x140052444  shl     rsi, 5
0x140052448  add     rsi, 8
0x14005244c  add     rsi, rdx
0x14005244f  cmp     [rsi], r13
0x140052452  jnz     short loc_14005245E
0x140052454  inc     ebx
0x140052456  jmp     short loc_140052435
0x140052458  mov     rsi, r13
0x14005245b  mov     ebx, r11d
0x14005245e  test    rsi, rsi
0x140052461  jz      short loc_1400524AC
0x140052463  test    byte ptr [rsi+30h], 1
0x140052467  jnz     loc_14005262F
0x14005246d  lea     eax, [rbx+rbx*2]
0x140052470  shl     eax, 5
0x140052473  add     eax, 8
0x140052476  cdqe
0x140052478  sub     rsi, rax
0x14005247b  mov     rdx, rsi
0x14005247e  test    rdx, rdx
0x140052481  jz      short loc_1400524AC
0x140052483  inc     ebx
0x140052485  cmp     ebx, 8
0x140052488  jnb     loc_14005261C
0x14005248e  lea     rsi, [rbx+rbx*2]
0x140052492  shl     rsi, 5
0x140052496  add     rsi, 8
0x14005249a  add     rsi, rdx
0x14005249d  cmp     qword ptr [rsi], 0
0x1400524a1  jnz     short loc_1400524A7
0x1400524a3  inc     ebx
0x1400524a5  jmp     short loc_140052485
0x1400524a7  test    rsi, rsi
0x1400524aa  jnz     short loc_140052463
0x1400524ac  mov     rdi, [rsp+230h+var_1F0]
0x1400524b1  cmp     dword ptr [rdi+70h], 64h ; 'd'
0x1400524b5  jnb     loc_1401F4359
0x1400524bb  mov     rcx, [r14]
0x1400524be  lea     rax, [rdi+40h]
0x1400524c2  mov     [rsp+230h+Event], rax
0x1400524c7  mov     rax, rcx
0x1400524ca  shr     rax, 0Ah
0x1400524ce  and     al, 1
0x1400524d0  shr     rcx, 0Bh
0x1400524d4  and     cl, 1
0x1400524d7  mov     byte ptr [rsp+230h+Event+9], al
0x1400524db  mov     eax, cs:dword_140262184
0x1400524e1  mov     byte ptr [rsp+230h+Event+8], 0
0x1400524e6  mov     byte ptr [rsp+230h+Event+0Ah], cl
0x1400524ea  mov     [rsp+230h+var_1B8], r13d
0x1400524ef  mov     [rsp+230h+var_1C0], rdi
0x1400524f4  cmp     [rdi+70h], eax
0x1400524f7  ja      loc_140052586
0x1400524fd  mov     rdx, [rdi+20h]
0x140052501  lea     r8, [rdi+20h]
0x140052505  cmp     rdx, r8
0x140052508  jz      loc_140052586
0x14005250e  cmp     [rdx], r8
0x140052511  jz      short loc_140052586
0x140052513  mov     [r8+8], rdx
0x140052517  mov     r11, rdx
0x14005251a  mov     r9, [rdx]
0x14005251d  cmp     r9, r8
0x140052520  jz      short loc_140052544
0x140052522  mov     rcx, [rdx-28h]
0x140052526  mov     r10, r9
0x140052529  sub     rcx, [r9-28h]
0x14005252d  test    rcx, rcx
0x140052530  jg      loc_140052B01
0x140052536  mov     rax, [r9]
0x140052539  mov     rdx, r10
0x14005253c  mov     r9, rax
0x14005253f  cmp     rax, r8
0x140052542  jnz     short loc_140052522
0x140052544  cmp     [r8+8], r11
0x140052548  jz      loc_140052DCF
0x14005254e  mov     [rdx], r13
0x140052551  mov     [r11+8], r13
0x140052555  mov     rdx, [r8+8]
0x140052559  cmp     qword ptr [rdx+8], 0
0x14005255e  jnz     loc_140052CD4
0x140052564  mov     [r8], rdx
0x140052567  mov     rax, r8
0x14005256a  test    rdx, rdx
0x14005256d  jz      short loc_14005257F
0x14005256f  nop
0x140052570  mov     [rdx+8], rax
0x140052574  mov     rax, rdx
0x140052577  mov     rdx, [rdx]
0x14005257a  test    rdx, rdx
0x14005257d  jnz     short loc_140052570
0x14005257f  mov     [rax], r8
0x140052582  mov     [r8+8], rax
0x140052586  mov     rax, [rdi+20h]
0x14005258a  mov     [rdi+3F0h], rax
0x140052591  mov     [rdi+408h], rax
0x140052598  cmp     dword ptr [rdi+70h], 0
0x14005259c  mov     [rdi+400h], r13d
0x1400525a3  jnz     loc_140052C8B
0x1400525a9  mov     rcx, [rsp+230h+Event]; Event
0x1400525ae  xor     r8d, r8d; Wait
0x1400525b1  xor     edx, edx; Increment
0x1400525b3  call    cs:__imp_KeSetEvent
0x1400525ba  nop     dword ptr [rax+rax+00h]
0x1400525bf  cmp     byte ptr [rsp+230h+Event+8], 0
0x1400525c4  jnz     loc_140052F50
0x1400525ca  mov     rcx, [rsp+230h+var_1F0]
0x1400525cf  cmp     dword ptr [rcx+378h], 0
0x1400525d6  jge     loc_140052D6E
0x1400525dc  mov     ebx, [rcx+3E8h]
0x1400525e2  test    ebx, ebx
0x1400525e4  jnz     loc_140052B10
0x1400525ea  and     qword ptr [r14], 0FFFFFFFFFFFFEFFFh
0x1400525f1  mov     rcx, [rbp+130h+var_40]
0x1400525f8  xor     rcx, rsp; StackCookie
0x1400525fb  call    __security_check_cookie
0x140052600  mov     rbx, [rsp+230h+arg_18]
0x140052608  add     rsp, 200h
0x14005260f  pop     r15
0x140052611  pop     r14
0x140052613  pop     r13
0x140052615  pop     r12
0x140052617  pop     rdi
0x140052618  pop     rsi
0x140052619  pop     rbp
0x14005261a  retn
0x14005261c  mov     rdx, [rdx]
0x14005261f  mov     ebx, r11d
0x140052622  jmp     loc_14005247E
0x140052627  mov     rdx, [rdx]
0x14005262a  jmp     loc_14005242D
0x14005262f  mov     rax, [rsi]
0x140052632  cmp     [rax+20h], rax
0x140052636  jnz     loc_1400529DF
0x14005263c  mov     rax, [rax+28h]
0x140052640  add     rax, 10h
0x140052644  mov     [rbp+130h+var_160], r14
0x140052648  mov     [rbp+130h+var_178], rax
0x14005264c  mov     ecx, [rax+0Ch]
0x14005264f  mov     edi, [rax+1Ch]
0x140052652  add     edi, ecx
0x140052654  mov     ecx, 0FFFFh; GroupNumber
0x140052659  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140052660  nop     dword ptr [rax+rax+00h]
0x140052665  mov     ecx, eax
0x140052667  mov     r15d, eax
0x14005266a  shr     ecx, 1
0x14005266c  cmp     ecx, 8
0x14005266f  ja      loc_14005285F
0x140052675  shr     ecx, 1
0x140052677  cmp     ecx, 4
0x14005267a  ja      loc_140052864
0x140052680  test    ecx, ecx
0x140052682  jz      loc_140052EC0
0x140052688  mov     eax, ecx
0x14005268a  cmp     edi, 64h ; 'd'
0x14005268d  jnb     loc_140052ECB
0x140052693  mov     r15d, r12d
0x140052696  mov     rdi, [rbp+130h+var_178]
0x14005269a  lea     rax, [rbp+130h+var_160]
0x14005269e  xorps   xmm0, xmm0
0x1400526a1  mov     [rbp+130h+var_148], rax
0x1400526a5  lea     rax, ?BuildWritePlanListsParallel@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAUSmsWritePlan@@@Z; CmsBPlusTable::BuildWritePlanListsParallel(CmsTransactionContext *,CmsHashTable *,ulong,ulong,SmsWritePlan *)
0x1400526ac  mov     [rbp+130h+var_190], rdi
0x1400526b0  mov     [rbp+130h+var_140], rax
0x1400526b4  lea     rcx, [rsp+230h+Event]; Event
0x1400526b9  lea     rax, [rbp+130h+var_178]
0x1400526bd  mov     [rbp+130h+var_1A0], r13d
0x1400526c1  mov     [rbp+130h+var_138], rax
0x1400526c5  xor     r8d, r8d; State
0x1400526c8  lea     rax, [rsp+230h+var_1F0]
0x1400526cd  movdqa  [rbp+130h+P], xmm0
0x1400526d2  mov     [rbp+130h+var_130], rax
0x1400526d6  xor     edx, edx; Type
0x1400526d8  xor     eax, eax
0x1400526da  mov     [rbp+130h+var_110], r13
0x1400526de  mov     [rsp+230h+var_1C0], rax
0x1400526e3  mov     [rbp+130h+var_108], 0
0x1400526eb  mov     [rbp+130h+var_100], r13
0x1400526ef  movups  [rbp+130h+var_F8], xmm0
0x1400526f3  mov     [rsp+230h+var_200], r13d
0x1400526f8  movups  [rbp+130h+var_E8], xmm0
0x1400526fc  movups  [rbp+130h+var_D8], xmm0
0x140052700  movups  [rbp+130h+var_C8], xmm0
0x140052704  movups  xmmword ptr [rsp+230h+Event], xmm0
0x140052709  call    cs:__imp_KeInitializeEvent
0x140052710  nop     dword ptr [rax+rax+00h]
0x140052715  cmp     r15d, 1
0x140052719  ja      loc_140052E7C
0x14005271f  lea     r13, [rbp+130h+P]
0x140052723  mov     r15d, r12d
0x140052726  mov     eax, r12d
0x140052729  mov     edx, r12d
0x14005272c  mov     rcx, r13
0x14005272f  mov     [rsp+230h+var_200], edx
0x140052733  lea     r10d, [rax-1]
0x140052737  xor     r8d, r8d
0x14005273a  mov     r9, r13
0x14005273d  mov     [rsp+230h+var_1D4], r10d
0x140052742  lea     rdx, [rcx+1Ch]
0x140052746  mov     [rbp+130h+var_1A8], rdx
0x14005274a  mov     eax, r8d
0x14005274d  imul    rcx, rax, 68h ; 'h'
0x140052751  lea     r12, [rcx+r9]
0x140052755  lea     r9, [rdx+rcx]
0x140052759  xor     edx, edx
0x14005275b  lea     rax, [rbp+130h+var_148]
0x14005275f  mov     [r12], rax
0x140052763  lea     rax, [rbp+130h+var_1A0]
0x140052767  mov     [r12+8], rax
0x14005276c  lea     rax, [rsp+230h+var_200]
0x140052771  mov     [r12+10h], rax
0x140052776  lea     rax, [rsp+230h+Event]
0x14005277b  mov     [r12+20h], rax
0x140052780  mov     eax, [rdi+8]
0x140052783  add     eax, [rdi+18h]
0x140052786  div     r15d
0x140052789  mov     ecx, eax
0x14005278b  imul    ecx, r8d
0x14005278f  mov     [r12+18h], ecx
0x140052794  lea     ecx, [r8+1]
0x140052798  mov     [rsp+230h+var_1D8], ecx
0x14005279c  imul    ecx, eax
0x14005279f  mov     [r9], ecx
0x1400527a2  cmp     r8d, r10d
0x1400527a5  jnz     short loc_1400527AE
0x1400527a7  mov     dword ptr [r9], 0FFFFFFFFh
0x1400527ae  cmp     r15d, 1
0x1400527b2  ja      loc_140052E03
0x1400527b8  mov     rax, [r12]
0x1400527bc  mov     ecx, [r12+1Ch]
0x1400527c1  mov     [rbp+130h+var_19C], ecx
0x1400527c4  mov     ecx, [r12+18h]
0x1400527c9  mov     [rbp+130h+var_198], ecx
0x1400527cc  mov     rcx, [rax+18h]
0x1400527d0  mov     [rbp+130h+var_150], rcx
0x1400527d4  mov     rcx, [rax+10h]
0x1400527d8  mov     [rbp+130h+var_170], rcx
0x1400527dc  mov     rcx, [rax+8]
0x1400527e0  mov     rax, [rax]
0x1400527e3  mov     [rbp+130h+var_188], rcx
0x1400527e7  xor     ecx, ecx; ProcNumber
0x1400527e9  mov     rax, [rax]
0x1400527ec  mov     [rbp+130h+var_158], rax
0x1400527f0  mov     rax, [rax+8]
0x1400527f4  mov     [rbp+130h+var_1B0], rax
0x1400527f8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400527ff  nop     dword ptr [rax+rax+00h]
0x140052804  xor     edx, edx
0x140052806  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14005280c  lea     rdi, [rdx+rdx*2]
0x140052810  shl     rdi, 6
0x140052814  add     rdi, cs:qword_140262408
0x14005281b  cmp     dword ptr [rdi], 0D50h
0x140052821  jnb     short loc_14005286E
0x140052823  xor     edi, edi
0x140052825  mov     edx, 0D60h
0x14005282a  mov     ecx, 42h ; 'B'
0x14005282f  mov     r8d, 6950534Dh
0x140052835  call    cs:__imp_ExAllocatePool2
0x14005283c  nop     dword ptr [rax+rax+00h]
0x140052841  mov     r14, rax
0x140052844  test    al, 0Fh
0x140052846  jnz     loc_1401F434C
0x14005284c  test    rax, rax
0x14005284f  jz      short loc_1400528AE
0x140052851  lea     rcx, [rax+10h]; void *
0x140052855  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x14005285a  jmp     loc_140052DE1
0x14005285f  mov     ecx, 8
0x140052864  mov     eax, 4
  ... truncated ...
```
