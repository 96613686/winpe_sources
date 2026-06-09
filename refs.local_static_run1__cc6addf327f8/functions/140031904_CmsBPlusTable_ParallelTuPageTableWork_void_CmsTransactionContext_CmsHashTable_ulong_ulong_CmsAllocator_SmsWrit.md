# CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)

- ea: `0x140031904`
- end: `0x140031db6`
- name: `??$ParallelTuPageTableWork@AEAP6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@AEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@Z`
- size: `1202`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140030130`

## callees

- `0x140014750`
- `0x140031904`
- `0x140047288`
- `0x140047300`
- `0x140047400`
- `0x140049050`
- `0x140087870`
- `0x140088930`
- `0x1400b26e8`
- `0x1400ceda0`
- `0x1401f3fb0`
- `0x1401f4090`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140031c3f`
- `ntoskrnl!KeSetEvent` at `0x140031c3f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031d51`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031d51`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14003194b`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14003194b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140031aea`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140031aea`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fb9b6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fb9b6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031d6f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031d6f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140031c6f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140031c6f`
- `ntoskrnl!KeInitializeEvent` at `0x140031a07`
- `ntoskrnl!KeInitializeEvent` at `0x140031a07`

## string_xrefs

- `0x1401fb9d4`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
void __fastcall CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v7; // ebx
  ULONG ActiveProcessorCount; // edi
  int v9; // eax
  int v10; // ecx
  __int64 v11; // r13
  __int128 *v12; // r14
  ULONG v13; // r8d
  __int64 v14; // r9
  char *v15; // r15
  unsigned int v16; // eax
  __int64 v17; // rax
  void (__fastcall **v18)(struct _SLIST_ENTRY *, _QWORD, __int64, __int64, _QWORD, _QWORD); // rcx
  __int64 *v19; // rax
  __int64 v20; // r13
  const struct std::nothrow_t *v21; // rdx
  __int64 v22; // rbx
  unsigned __int64 v23; // rcx
  int v24; // ecx
  PSLIST_ENTRY v25; // rsi
  struct _SLIST_ENTRY *v26; // rsi
  __int64 v27; // rax
  _QWORD *v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r9
  __int64 v31; // r12
  __int64 v32; // r8
  __int64 v33; // rax
  char v34; // bl
  void (__fastcall **v35)(struct _SLIST_ENTRY *, _QWORD, __int64, __int64, _QWORD, _QWORD); // rax
  unsigned __int64 v36; // rbx
  __int128 *v37; // rax
  struct _NPAGED_LOOKASIDE_LIST *v38; // rcx
  struct _SLIST_ENTRY *v39; // rax
  struct _SLIST_ENTRY *v40; // rax
  ULONG v41; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v43; // [rsp+48h] [rbp-B8h]
  unsigned int v44; // [rsp+4Ch] [rbp-B4h]
  ULONG v45; // [rsp+50h] [rbp-B0h]
  __int64 v46; // [rsp+58h] [rbp-A8h]
  __int64 v47; // [rsp+60h] [rbp-A0h]
  void (__fastcall **v48)(struct _SLIST_ENTRY *, _QWORD, __int64, __int64, _QWORD, _QWORD); // [rsp+68h] [rbp-98h]
  _QWORD *v49; // [rsp+70h] [rbp-90h]
  _QWORD *v50; // [rsp+78h] [rbp-88h]
  _QWORD *v51; // [rsp+80h] [rbp-80h]
  struct _KEVENT Event; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v53[6]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v54; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v55; // [rsp+E0h] [rbp-20h]
  __int64 v56; // [rsp+E8h] [rbp-18h]
  __int64 v57; // [rsp+F0h] [rbp-10h]
  _BYTE v58[64]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v59; // [rsp+190h] [rbp+90h] BYREF
  __int64 v60; // [rsp+198h] [rbp+98h] BYREF

  v60 = a2;
  v59 = a1;
  v7 = *(_DWORD *)(a2 + 12) + *(_DWORD *)(a2 + 28);
  ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  v9 = 4;
  v10 = 8;
  if ( ActiveProcessorCount >> 1 <= 8 )
  {
    v10 = ActiveProcessorCount >> 2;
    if ( ActiveProcessorCount >> 2 <= 4 )
    {
      if ( v10 )
      {
        v9 = ActiveProcessorCount >> 2;
      }
      else
      {
        v9 = 1;
        v10 = 1;
      }
    }
  }
  if ( v7 >= 0x64 )
  {
    if ( v7 <= 0x5DC )
    {
      ActiveProcessorCount = v9;
      if ( v7 > 0x3E8 )
        ActiveProcessorCount = v10;
    }
  }
  else
  {
    ActiveProcessorCount = 1;
  }
  v11 = v60;
  v53[0] = &v59;
  v53[1] = a3;
  v53[3] = a4;
  v53[2] = &v60;
  v53[4] = a5;
  v46 = v60;
  v42 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  memset(v58, 0, sizeof(v58));
  v41 = 0;
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  if ( ActiveProcessorCount <= 1 )
    goto LABEL_8;
  v36 = 104LL * ActiveProcessorCount;
  if ( !is_mul_ok(ActiveProcessorCount, 0x68u) )
    v36 = -1;
  v37 = (__int128 *)operator new(
                      v36,
                      (const struct std::nothrow_t *)((ActiveProcessorCount * (unsigned __int128)0x68uLL) >> 64));
  v12 = v37;
  if ( v37 )
  {
    memset(v37, 0, v36);
    _____builtin_array_init_helper_UWorker__1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable____QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__CmsHashTable__QEAAJK__QEAV_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV2___QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV6_AEAPEAU7__Z__Z___YAXPEAUWorker__1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable____QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__CmsHashTable__QEAAJK__QEAV_lambda_1___1____ParallelTuPageTableWork_P6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV1___QEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__Z__K_Z(
      v12,
      ActiveProcessorCount);
  }
  else
  {
LABEL_8:
    v12 = &v54;
    ActiveProcessorCount = 1;
  }
  v41 = ActiveProcessorCount;
  v13 = 0;
  do
  {
    v14 = 104LL * v13;
    v15 = (char *)v12 + v14;
    *(_QWORD *)v15 = v53;
    *((_QWORD *)v15 + 1) = &v42;
    *((_QWORD *)v15 + 2) = &v41;
    *((_QWORD *)v15 + 4) = &Event;
    v16 = (*(_DWORD *)(v11 + 24) + *(_DWORD *)(v11 + 8)) / ActiveProcessorCount;
    *((_DWORD *)v15 + 6) = v13 * v16;
    v45 = v13 + 1;
    *(_DWORD *)((char *)v12 + v14 + 28) = v16 * (v13 + 1);
    if ( v13 == ActiveProcessorCount - 1 )
      *(_DWORD *)((char *)v12 + v14 + 28) = -1;
    if ( ActiveProcessorCount <= 1
      || !MsInitializeAndTryQueueWorkItem(
            (struct _MS_WORK_QUEUE_ITEM *)(v15 + 40),
            __lambda_invoker_cdecl___lambda_1___1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_AEAP6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable__AEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__CmsHashTable__QEAAJK__QEAV1_1____ParallelTuPageTableWork_AEAP6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV2_AEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__Z_SA_PEAX_Z,
            (char *)v12 + v14,
            (enum _WORK_QUEUE_TYPE)v14) )
    {
      v17 = *(_QWORD *)v15;
      v43 = *((_DWORD *)v15 + 7);
      v44 = *((_DWORD *)v15 + 6);
      v49 = *(_QWORD **)(v17 + 32);
      v50 = *(_QWORD **)(v17 + 24);
      v51 = *(_QWORD **)(v17 + 16);
      v18 = *(void (__fastcall ***)(struct _SLIST_ENTRY *, _QWORD, __int64, __int64, _QWORD, _QWORD))(v17 + 8);
      v19 = *(__int64 **)v17;
      v48 = v18;
      v47 = *v19;
      v20 = *(_QWORD *)(v47 + 8);
      v21 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
      v22 = qword_140269408 + 192LL * (_QWORD)v21;
      if ( *(_DWORD *)v22 < 0xDD0u )
      {
        v22 = 0;
        goto LABEL_15;
      }
      if ( *(_BYTE *)(v22 + 8) )
      {
        v38 = (struct _NPAGED_LOOKASIDE_LIST *)(v22 + 64);
        if ( *(_BYTE *)(v22 + 9) )
          v39 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v38);
        else
          v39 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v38);
        v25 = v39;
        CmsTransactionContext::InitializeTransactionMemoryBuffer(&v39->Next + 1);
      }
      else
      {
        if ( (int)*(_QWORD *)(v22 + 88) <= (int)HIDWORD(*(_QWORD *)(v22 + 88)) )
          goto LABEL_47;
        v24 = _InterlockedDecrement((volatile signed __int32 *)(v22 + 88));
        if ( v24 < *(_DWORD *)(v22 + 92) || v24 < 0 )
        {
          v25 = 0;
          _InterlockedIncrement((volatile signed __int32 *)(v22 + 88));
        }
        else
        {
          v25 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v22 + 64));
        }
      }
      if ( v25 )
        goto LABEL_21;
LABEL_47:
      if ( v22 )
      {
        v23 = *(unsigned int *)(v22 + 4);
        goto LABEL_49;
      }
LABEL_15:
      v23 = 3552;
LABEL_49:
      v40 = (struct _SLIST_ENTRY *)operator new(v23, v21);
      v25 = v40;
      if ( ((unsigned __int8)v40 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !v40 )
        goto LABEL_23;
      CmsTransactionContext::InitializeTransactionMemoryBuffer(&v40[1]);
LABEL_21:
      v25->Next = (struct _SLIST_ENTRY *)v22;
      v26 = v25 + 1;
      if ( v26 )
      {
        v27 = 0x8000;
LABEL_24:
        v28 = v51;
        v29 = v27;
        v30 = v43;
        v31 = v27;
        v32 = v44;
        v26->Next = (struct _SLIST_ENTRY *)v27;
        v33 = v47;
        *((_QWORD *)&v26->Next + 1) = v20;
        v34 = *((_BYTE *)&v26[13].Next + 12);
        v26->Next = (struct _SLIST_ENTRY *)(*(_QWORD *)v33 | v29);
        LOBYTE(v29) = *(_BYTE *)(v33 + 220);
        v35 = v48;
        *((_BYTE *)&v26[13].Next + 12) = v29;
        (*v35)(v26, *v28, v32, v30, *v50, *v49);
        CmsTransactionContext::Commit((CmsTransactionContext *)v26, 0, 0, 0);
        *((_BYTE *)&v26[13].Next + 12) = v34;
        v26->Next = (struct _SLIST_ENTRY *)v31;
        CmsTransactionContext::Release((CmsTransactionContext *)v26);
        if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)v15 + 2), 0xFFFFFFFF) == 1 )
          KeSetEvent(*((PRKEVENT *)v15 + 4), 0, 0);
        v11 = v46;
        goto LABEL_27;
      }
LABEL_23:
      v26 = (struct _SLIST_ENTRY *)CmsReservedPool::AllocateFromPool((CmsReservedPool *)(v20 + 160));
      CmsTransactionContext::InitializeTransactionMemoryBuffer(v26);
      v27 = 268468224;
      goto LABEL_24;
    }
LABEL_27:
    v13 = v45;
  }
  while ( v45 < ActiveProcessorCount );
  KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  if ( v12 )
  {
    if ( v12 != &v54 )
      operator delete(v12);
  }
}

```

## disassembly

```asm
0x140031904  mov     [rsp-8+arg_10], rbx
0x140031909  mov     [rsp-8+arg_8], rdx
0x14003190e  mov     [rsp-8+arg_0], rcx
0x140031913  push    rbp
0x140031914  push    rsi
0x140031915  push    rdi
0x140031916  push    r12
0x140031918  push    r13
0x14003191a  push    r14
0x14003191c  push    r15
0x14003191e  lea     rbp, [rsp-50h]
0x140031923  sub     rsp, 150h
0x14003192a  mov     rax, cs:__security_cookie
0x140031931  xor     rax, rsp
0x140031934  mov     [rbp+80h+var_40], rax
0x140031938  mov     ecx, [rdx+0Ch]
0x14003193b  mov     rsi, r9
0x14003193e  mov     ebx, [rdx+1Ch]
0x140031941  mov     r14, r8
0x140031944  add     ebx, ecx
0x140031946  mov     ecx, 0FFFFh; GroupNumber
0x14003194b  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140031952  nop     dword ptr [rax+rax+00h]
0x140031957  xor     r12d, r12d
0x14003195a  mov     edx, eax
0x14003195c  mov     edi, eax
0x14003195e  shr     edx, 1
0x140031960  lea     eax, [r12+4]
0x140031965  lea     ecx, [rax+4]
0x140031968  lea     r15d, [r12+1]
0x14003196d  cmp     edx, ecx
0x14003196f  ja      short loc_140031983
0x140031971  mov     ecx, edx
0x140031973  shr     ecx, 1
0x140031975  cmp     ecx, eax
0x140031977  ja      short loc_140031983
0x140031979  test    ecx, ecx
0x14003197b  jz      loc_140031CBB
0x140031981  mov     eax, ecx
0x140031983  cmp     ebx, 64h ; 'd'
0x140031986  jnb     loc_140031CC6
0x14003198c  mov     edi, r15d
0x14003198f  mov     r13, [rbp+80h+arg_8]
0x140031996  lea     rax, [rbp+80h+arg_0]
0x14003199d  mov     [rbp+80h+var_E0], rax
0x1400319a1  lea     rcx, [rbp+80h+var_88]; void *
0x1400319a5  xor     edx, edx; Val
0x1400319a7  mov     [rbp+80h+var_D8], r14
0x1400319ab  lea     rax, [rbp+80h+arg_8]
0x1400319b2  mov     [rbp+80h+var_C8], rsi
0x1400319b6  mov     [rbp+80h+var_D0], rax
0x1400319ba  xorps   xmm0, xmm0
0x1400319bd  mov     rax, [rbp+80h+arg_20]
0x1400319c4  lea     r8d, [rdx+40h]; Size
0x1400319c8  mov     [rbp+80h+var_C0], rax
0x1400319cc  mov     [rsp+180h+var_128], r13
0x1400319d1  mov     [rsp+180h+var_13C], r12d
0x1400319d6  movdqa  [rbp+80h+var_B0], xmm0
0x1400319db  mov     [rbp+80h+var_A0], r12
0x1400319df  mov     [rbp+80h+var_98], r12
0x1400319e3  mov     [rbp+80h+var_90], r12
0x1400319e7  call    memset
0x1400319ec  xorps   xmm0, xmm0
0x1400319ef  mov     [rsp+180h+var_140], r12d
0x1400319f4  xor     eax, eax
0x1400319f6  lea     rcx, [rbp+80h+Event]; Event
0x1400319fa  xor     r8d, r8d; State
0x1400319fd  mov     [rbp+80h+Event.Header.WaitListHead.Blink], rax
0x140031a01  xor     edx, edx; Type
0x140031a03  movups  xmmword ptr [rbp+80h+Event.Header], xmm0
0x140031a07  call    cs:__imp_KeInitializeEvent
0x140031a0e  nop     dword ptr [rax+rax+00h]
0x140031a13  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140031a17  cmp     edi, r15d
0x140031a1a  ja      loc_140031CE2
0x140031a20  lea     r14, [rbp+80h+var_B0]
0x140031a24  mov     edi, r15d
0x140031a27  mov     [rsp+180h+var_140], edi
0x140031a2b  mov     r8d, r12d
0x140031a2e  test    edi, edi
0x140031a30  jz      loc_140031C5E
0x140031a36  mov     eax, r8d
0x140031a39  lea     r10d, [rdi-1]
0x140031a3d  imul    r9, rax, 68h ; 'h'; enum _WORK_QUEUE_TYPE
0x140031a41  lea     rax, [rbp+80h+var_E0]
0x140031a45  xor     edx, edx
0x140031a47  lea     r15, [r14+r9]
0x140031a4b  mov     [r15], rax
0x140031a4e  lea     rax, [rsp+180h+var_13C]
0x140031a53  mov     [r15+8], rax
0x140031a57  lea     rax, [rsp+180h+var_140]
0x140031a5c  mov     [r15+10h], rax
0x140031a60  lea     rax, [rbp+80h+Event]
0x140031a64  mov     [r15+20h], rax
0x140031a68  mov     eax, [r13+8]
0x140031a6c  add     eax, [r13+18h]
0x140031a70  div     edi
0x140031a72  mov     ecx, eax
0x140031a74  imul    ecx, r8d
0x140031a78  mov     [r15+18h], ecx
0x140031a7c  lea     ecx, [r8+1]
0x140031a80  mov     [rsp+180h+var_130], ecx
0x140031a84  imul    ecx, eax
0x140031a87  mov     [r14+r9+1Ch], ecx
0x140031a8c  cmp     r8d, r10d
0x140031a8f  jnz     short loc_140031A9A
0x140031a91  mov     dword ptr [r14+r9+1Ch], 0FFFFFFFFh
0x140031a9a  cmp     edi, 1
0x140031a9d  ja      loc_140031D23
0x140031aa3  mov     rax, [r15]
0x140031aa6  mov     ecx, [r15+1Ch]
0x140031aaa  mov     [rsp+180h+var_138], ecx
0x140031aae  mov     ecx, [r15+18h]
0x140031ab2  mov     [rsp+180h+var_134], ecx
0x140031ab6  mov     rcx, [rax+20h]
0x140031aba  mov     [rsp+180h+var_110], rcx
0x140031abf  mov     rcx, [rax+18h]
0x140031ac3  mov     [rsp+180h+var_108], rcx
0x140031ac8  mov     rcx, [rax+10h]
0x140031acc  mov     [rbp+80h+var_100], rcx
0x140031ad0  mov     rcx, [rax+8]
0x140031ad4  mov     rax, [rax]
0x140031ad7  mov     [rsp+180h+var_118], rcx
0x140031adc  xor     ecx, ecx; ProcNumber
0x140031ade  mov     rax, [rax]
0x140031ae1  mov     [rsp+180h+var_120], rax
0x140031ae6  mov     r13, [rax+8]
0x140031aea  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140031af1  nop     dword ptr [rax+rax+00h]
0x140031af6  xor     edx, edx; struct std::nothrow_t *
0x140031af8  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140031afe  lea     rbx, [rdx+rdx*2]
0x140031b02  shl     rbx, 6
0x140031b06  add     rbx, cs:qword_140269408
0x140031b0d  cmp     dword ptr [rbx], 0DD0h
0x140031b13  jnb     short loc_140031B22
0x140031b15  mov     rbx, r12
0x140031b18  mov     ecx, 0DE0h
0x140031b1d  jmp     loc_140031D8F
0x140031b22  cmp     [rbx+8], r12b
0x140031b26  jnz     loc_140031D43
0x140031b2c  mov     rcx, [rbx+58h]
0x140031b30  mov     rax, rcx
0x140031b33  sar     rax, 20h
0x140031b37  cmp     ecx, eax
0x140031b39  jle     loc_140031D83
0x140031b3f  nop
0x140031b40  or      ecx, 0FFFFFFFFh
0x140031b43  lock xadd [rbx+58h], ecx
0x140031b48  nop
0x140031b49  dec     ecx
0x140031b4b  mov     eax, [rbx+5Ch]
0x140031b4e  cmp     ecx, eax
0x140031b50  jge     loc_140031D63
0x140031b56  mov     rsi, r12
0x140031b59  nop
0x140031b5a  lock inc dword ptr [rbx+58h]
0x140031b5e  nop
0x140031b5f  test    rsi, rsi
0x140031b62  jz      loc_140031D83
0x140031b68  mov     [rsi], rbx
0x140031b6b  add     rsi, 10h
0x140031b6f  jz      short loc_140031B7D
0x140031b71  mov     eax, 8000h
0x140031b76  jmp     short loc_140031B99
0x140031b78  test    rsi, rsi
0x140031b7b  jnz     short loc_140031B68
0x140031b7d  lea     rcx, [r13+0A0h]; this
0x140031b84  call    ?AllocateFromPool@CmsReservedPool@@QEAAPEAXXZ; CmsReservedPool::AllocateFromPool(void)
0x140031b89  mov     rcx, rax; void *
0x140031b8c  mov     rsi, rax
0x140031b8f  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x140031b94  mov     eax, 10008000h
0x140031b99  mov     rdx, [rbp+80h+var_100]
0x140031b9d  mov     rcx, rax
0x140031ba0  mov     r9d, [rsp+180h+var_138]
0x140031ba5  mov     r12, rax
0x140031ba8  mov     r8d, [rsp+180h+var_134]
0x140031bad  mov     [rsi], rax
0x140031bb0  mov     rax, [rsp+180h+var_120]
0x140031bb5  mov     [rsi+8], r13
0x140031bb9  mov     bl, [rsi+0DCh]
0x140031bbf  or      rcx, [rax]
0x140031bc2  mov     [rsi], rcx
0x140031bc5  mov     cl, [rax+0DCh]
0x140031bcb  mov     rax, [rsp+180h+var_118]
0x140031bd0  mov     [rsi+0DCh], cl
0x140031bd6  mov     rcx, [rsp+180h+var_110]
0x140031bdb  mov     rdx, [rdx]
0x140031bde  mov     rax, [rax]
0x140031be1  mov     rcx, [rcx]
0x140031be4  mov     [rsp+180h+var_158], rcx
0x140031be9  mov     rcx, [rsp+180h+var_108]
0x140031bee  mov     rcx, [rcx]
0x140031bf1  mov     [rsp+180h+Timeout], rcx
0x140031bf6  mov     rcx, rsi
0x140031bf9  call    _guard_dispatch_icall
0x140031bfe  xor     r9d, r9d; unsigned __int8
0x140031c01  xor     r8d, r8d; struct _SmsLsn *
0x140031c04  xor     edx, edx; unsigned __int8
0x140031c06  mov     rcx, rsi; this
0x140031c09  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140031c0e  mov     rcx, rsi; this
0x140031c11  mov     [rsi+0DCh], bl
0x140031c17  mov     [rsi], r12
0x140031c1a  call    ?Release@CmsTransactionContext@@QEAAXXZ; CmsTransactionContext::Release(void)
0x140031c1f  mov     rax, [r15+10h]
0x140031c23  or      ecx, 0FFFFFFFFh
0x140031c26  nop
0x140031c27  lock xadd [rax], ecx
0x140031c2b  lea     eax, [rcx-1]
0x140031c2e  xor     r12d, r12d
0x140031c31  nop
0x140031c32  test    eax, eax
0x140031c34  jnz     short loc_140031C4B
0x140031c36  mov     rcx, [r15+20h]; Event
0x140031c3a  xor     r8d, r8d; Wait
0x140031c3d  xor     edx, edx; Increment
0x140031c3f  call    cs:__imp_KeSetEvent
0x140031c46  nop     dword ptr [rax+rax+00h]
0x140031c4b  mov     r13, [rsp+180h+var_128]
0x140031c50  mov     r8d, [rsp+180h+var_130]
0x140031c55  cmp     r8d, edi
0x140031c58  jb      loc_140031A36
0x140031c5e  xor     r9d, r9d; Alertable
0x140031c61  mov     [rsp+180h+Timeout], r12; Timeout
0x140031c66  xor     r8d, r8d; WaitMode
0x140031c69  lea     rcx, [rbp+80h+Event]; Object
0x140031c6d  xor     edx, edx; WaitReason
0x140031c6f  call    cs:__imp_KeWaitForSingleObject
0x140031c76  nop     dword ptr [rax+rax+00h]
0x140031c7b  test    r14, r14
0x140031c7e  jnz     short loc_140031CA8
0x140031c80  mov     rcx, [rbp+80h+var_40]
0x140031c84  xor     rcx, rsp; StackCookie
0x140031c87  call    __security_check_cookie
0x140031c8c  mov     rbx, [rsp+180h+arg_10]
0x140031c94  add     rsp, 150h
0x140031c9b  pop     r15
0x140031c9d  pop     r14
0x140031c9f  pop     r13
0x140031ca1  pop     r12
0x140031ca3  pop     rdi
0x140031ca4  pop     rsi
0x140031ca5  pop     rbp
0x140031ca6  retn
0x140031ca8  lea     rax, [rbp+80h+var_B0]
0x140031cac  cmp     r14, rax
0x140031caf  jz      short loc_140031C80
0x140031cb1  mov     rcx, r14; void *
0x140031cb4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140031cb9  jmp     short loc_140031C80
0x140031cbb  mov     eax, r15d
0x140031cbe  mov     ecx, r15d
0x140031cc1  jmp     loc_140031983
0x140031cc6  cmp     ebx, 5DCh
0x140031ccc  ja      loc_14003198F
0x140031cd2  cmp     ebx, 3E8h
0x140031cd8  mov     edi, eax
0x140031cda  cmova   edi, ecx
0x140031cdd  jmp     loc_14003198F
0x140031ce2  mov     esi, edi
0x140031ce4  mov     eax, 68h ; 'h'
0x140031ce9  mul     rsi
0x140031cec  mov     rbx, rax
0x140031cef  cmovb   rbx, rcx
0x140031cf3  mov     rcx, rbx; unsigned __int64
0x140031cf6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140031cfb  mov     r14, rax
0x140031cfe  test    rax, rax
0x140031d01  jz      loc_140031A20
0x140031d07  mov     r8, rbx; Size
0x140031d0a  xor     edx, edx; Val
0x140031d0c  mov     rcx, rax; void *
0x140031d0f  call    memset
0x140031d14  mov     edx, esi
0x140031d16  mov     rcx, r14
0x140031d19  call    ??$__builtin_array_init_helper@UWorker@?1???$ParallelWork@V_lambda_1_@?1???$ParallelTuPageTableWork@P6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@$$QEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@CmsHashTable@@QEAAJK$$QEAV_lambda_1_@?1???$ParallelTuPageTableWork@P6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAV2@$$QEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV6@AEAPEAU7@@Z@@Z@@@YAXPEAUWorker@?1???$ParallelWork@V_lambda_1_@?1???$ParallelTuPageTableWork@P6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@$$QEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@CmsHashTable@@QEAAJK$$QEAV_lambda_1_@?1???$ParallelTuPageTableWork@P6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAV1@$$QEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@Z@_K@Z; __builtin_array_init_helper<`CmsHashTable::ParallelWork<`CmsBPlusTable::ParallelTuPageTableWork<void (*)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_>(ulong,`CmsBPlusTable::ParallelTuPageTableWork<void (*)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_ &&)'::`2'::Worker>(`CmsHashTable::ParallelWork<`CmsBPlusTable::ParallelTuPageTableWork<void (*)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_>(ulong,`CmsBPlusTable::ParallelTuPageTableWork<void (*)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_ &&)'::`2'::Worker *,unsigned __int64)
0x140031d1e  jmp     loc_140031A27
0x140031d23  lea     rcx, [r15+28h]; struct _MS_WORK_QUEUE_ITEM *
0x140031d27  mov     r8, r15; void *
0x140031d2a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$ParallelWork@V_lambda_1_@?1???$ParallelTuPageTableWork@AEAP6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@AEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@CmsHashTable@@QEAAJK$$QEAV1?1???$ParallelTuPageTableWork@AEAP6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAV2@AEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@Z@SA@PEAX@Z; void (*)(void *)
0x140031d31  call    ?MsInitializeAndTryQueueWorkItem@@YAEPEAU_MS_WORK_QUEUE_ITEM@@P6AXPEAX@Z1W4_WORK_QUEUE_TYPE@@@Z; MsInitializeAndTryQueueWorkItem(_MS_WORK_QUEUE_ITEM *,void (*)(void *),void *,_WORK_QUEUE_TYPE)
0x140031d36  test    al, al
0x140031d38  jnz     loc_140031C50
0x140031d3e  jmp     loc_140031AA3
0x140031d43  lea     rcx, [rbx+40h]; Lookaside
0x140031d47  cmp     [rbx+9], r12b
0x140031d4b  jz      loc_1401FB9B6
0x140031d51  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140031d58  nop     dword ptr [rax+rax+00h]
0x140031d5d  nop
0x140031d5e  jmp     loc_1401FB9C2
0x140031d63  test    ecx, ecx
0x140031d65  js      loc_140031B56
0x140031d6b  lea     rcx, [rbx+40h]; ListHead
0x140031d6f  call    cs:__imp_ExpInterlockedPopEntrySList
0x140031d76  nop     dword ptr [rax+rax+00h]
0x140031d7b  mov     rsi, rax
0x140031d7e  jmp     loc_140031B5F
  ... truncated ...
```
