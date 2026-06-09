# CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)

- ea: `0x140065c34`
- end: `0x1400660e6`
- name: `??$ParallelTuPageTableWork@AEAP6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@AEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@Z`
- size: `1202`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140064480`

## callees

- `0x1400340e0`
- `0x140053024`
- `0x1400530a0`
- `0x140054d40`
- `0x140065c34`
- `0x1400710d0`
- `0x140071100`
- `0x140072970`
- `0x1400b5884`
- `0x1400c8574`
- `0x1401e9ce0`
- `0x1401e9dc0`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140065f6f`
- `ntoskrnl!KeSetEvent` at `0x140065f6f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140066081`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140066081`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140065c7b`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140065c7b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140065e1a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140065e1a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f63f0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f63f0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006609f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006609f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140065f9f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140065f9f`
- `ntoskrnl!KeInitializeEvent` at `0x140065d37`
- `ntoskrnl!KeInitializeEvent` at `0x140065d37`

## string_xrefs

- `0x1401f640e`: `Lookaside list allocation must be double quad aligned.`

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
      v22 = qword_140262408 + 192LL * (_QWORD)v21;
      if ( *(_DWORD *)v22 < 0xD50u )
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
      v23 = 3424;
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
0x140065c34  mov     [rsp-8+arg_10], rbx
0x140065c39  mov     [rsp-8+arg_8], rdx
0x140065c3e  mov     [rsp-8+arg_0], rcx
0x140065c43  push    rbp
0x140065c44  push    rsi
0x140065c45  push    rdi
0x140065c46  push    r12
0x140065c48  push    r13
0x140065c4a  push    r14
0x140065c4c  push    r15
0x140065c4e  lea     rbp, [rsp-50h]
0x140065c53  sub     rsp, 150h
0x140065c5a  mov     rax, cs:__security_cookie
0x140065c61  xor     rax, rsp
0x140065c64  mov     [rbp+80h+var_40], rax
0x140065c68  mov     ecx, [rdx+0Ch]
0x140065c6b  mov     rsi, r9
0x140065c6e  mov     ebx, [rdx+1Ch]
0x140065c71  mov     r14, r8
0x140065c74  add     ebx, ecx
0x140065c76  mov     ecx, 0FFFFh; GroupNumber
0x140065c7b  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140065c82  nop     dword ptr [rax+rax+00h]
0x140065c87  xor     r12d, r12d
0x140065c8a  mov     edx, eax
0x140065c8c  mov     edi, eax
0x140065c8e  shr     edx, 1
0x140065c90  lea     eax, [r12+4]
0x140065c95  lea     ecx, [rax+4]
0x140065c98  lea     r15d, [r12+1]
0x140065c9d  cmp     edx, ecx
0x140065c9f  ja      short loc_140065CB3
0x140065ca1  mov     ecx, edx
0x140065ca3  shr     ecx, 1
0x140065ca5  cmp     ecx, eax
0x140065ca7  ja      short loc_140065CB3
0x140065ca9  test    ecx, ecx
0x140065cab  jz      loc_140065FEB
0x140065cb1  mov     eax, ecx
0x140065cb3  cmp     ebx, 64h ; 'd'
0x140065cb6  jnb     loc_140065FF6
0x140065cbc  mov     edi, r15d
0x140065cbf  mov     r13, [rbp+80h+arg_8]
0x140065cc6  lea     rax, [rbp+80h+arg_0]
0x140065ccd  mov     [rbp+80h+var_E0], rax
0x140065cd1  lea     rcx, [rbp+80h+var_88]; void *
0x140065cd5  xor     edx, edx; Val
0x140065cd7  mov     [rbp+80h+var_D8], r14
0x140065cdb  lea     rax, [rbp+80h+arg_8]
0x140065ce2  mov     [rbp+80h+var_C8], rsi
0x140065ce6  mov     [rbp+80h+var_D0], rax
0x140065cea  xorps   xmm0, xmm0
0x140065ced  mov     rax, [rbp+80h+arg_20]
0x140065cf4  lea     r8d, [rdx+40h]; Size
0x140065cf8  mov     [rbp+80h+var_C0], rax
0x140065cfc  mov     [rsp+180h+var_128], r13
0x140065d01  mov     [rsp+180h+var_13C], r12d
0x140065d06  movdqa  [rbp+80h+var_B0], xmm0
0x140065d0b  mov     [rbp+80h+var_A0], r12
0x140065d0f  mov     [rbp+80h+var_98], r12
0x140065d13  mov     [rbp+80h+var_90], r12
0x140065d17  call    memset
0x140065d1c  xorps   xmm0, xmm0
0x140065d1f  mov     [rsp+180h+var_140], r12d
0x140065d24  xor     eax, eax
0x140065d26  lea     rcx, [rbp+80h+Event]; Event
0x140065d2a  xor     r8d, r8d; State
0x140065d2d  mov     [rbp+80h+Event.Header.WaitListHead.Blink], rax
0x140065d31  xor     edx, edx; Type
0x140065d33  movups  xmmword ptr [rbp+80h+Event.Header], xmm0
0x140065d37  call    cs:__imp_KeInitializeEvent
0x140065d3e  nop     dword ptr [rax+rax+00h]
0x140065d43  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140065d47  cmp     edi, r15d
0x140065d4a  ja      loc_140066012
0x140065d50  lea     r14, [rbp+80h+var_B0]
0x140065d54  mov     edi, r15d
0x140065d57  mov     [rsp+180h+var_140], edi
0x140065d5b  mov     r8d, r12d
0x140065d5e  test    edi, edi
0x140065d60  jz      loc_140065F8E
0x140065d66  mov     eax, r8d
0x140065d69  lea     r10d, [rdi-1]
0x140065d6d  imul    r9, rax, 68h ; 'h'; enum _WORK_QUEUE_TYPE
0x140065d71  lea     rax, [rbp+80h+var_E0]
0x140065d75  xor     edx, edx
0x140065d77  lea     r15, [r14+r9]
0x140065d7b  mov     [r15], rax
0x140065d7e  lea     rax, [rsp+180h+var_13C]
0x140065d83  mov     [r15+8], rax
0x140065d87  lea     rax, [rsp+180h+var_140]
0x140065d8c  mov     [r15+10h], rax
0x140065d90  lea     rax, [rbp+80h+Event]
0x140065d94  mov     [r15+20h], rax
0x140065d98  mov     eax, [r13+8]
0x140065d9c  add     eax, [r13+18h]
0x140065da0  div     edi
0x140065da2  mov     ecx, eax
0x140065da4  imul    ecx, r8d
0x140065da8  mov     [r15+18h], ecx
0x140065dac  lea     ecx, [r8+1]
0x140065db0  mov     [rsp+180h+var_130], ecx
0x140065db4  imul    ecx, eax
0x140065db7  mov     [r14+r9+1Ch], ecx
0x140065dbc  cmp     r8d, r10d
0x140065dbf  jnz     short loc_140065DCA
0x140065dc1  mov     dword ptr [r14+r9+1Ch], 0FFFFFFFFh
0x140065dca  cmp     edi, 1
0x140065dcd  ja      loc_140066053
0x140065dd3  mov     rax, [r15]
0x140065dd6  mov     ecx, [r15+1Ch]
0x140065dda  mov     [rsp+180h+var_138], ecx
0x140065dde  mov     ecx, [r15+18h]
0x140065de2  mov     [rsp+180h+var_134], ecx
0x140065de6  mov     rcx, [rax+20h]
0x140065dea  mov     [rsp+180h+var_110], rcx
0x140065def  mov     rcx, [rax+18h]
0x140065df3  mov     [rsp+180h+var_108], rcx
0x140065df8  mov     rcx, [rax+10h]
0x140065dfc  mov     [rbp+80h+var_100], rcx
0x140065e00  mov     rcx, [rax+8]
0x140065e04  mov     rax, [rax]
0x140065e07  mov     [rsp+180h+var_118], rcx
0x140065e0c  xor     ecx, ecx; ProcNumber
0x140065e0e  mov     rax, [rax]
0x140065e11  mov     [rsp+180h+var_120], rax
0x140065e16  mov     r13, [rax+8]
0x140065e1a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140065e21  nop     dword ptr [rax+rax+00h]
0x140065e26  xor     edx, edx; struct std::nothrow_t *
0x140065e28  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140065e2e  lea     rbx, [rdx+rdx*2]
0x140065e32  shl     rbx, 6
0x140065e36  add     rbx, cs:qword_140262408
0x140065e3d  cmp     dword ptr [rbx], 0D50h
0x140065e43  jnb     short loc_140065E52
0x140065e45  mov     rbx, r12
0x140065e48  mov     ecx, 0D60h
0x140065e4d  jmp     loc_1400660BF
0x140065e52  cmp     [rbx+8], r12b
0x140065e56  jnz     loc_140066073
0x140065e5c  mov     rcx, [rbx+58h]
0x140065e60  mov     rax, rcx
0x140065e63  sar     rax, 20h
0x140065e67  cmp     ecx, eax
0x140065e69  jle     loc_1400660B3
0x140065e6f  nop
0x140065e70  or      ecx, 0FFFFFFFFh
0x140065e73  lock xadd [rbx+58h], ecx
0x140065e78  nop
0x140065e79  dec     ecx
0x140065e7b  mov     eax, [rbx+5Ch]
0x140065e7e  cmp     ecx, eax
0x140065e80  jge     loc_140066093
0x140065e86  mov     rsi, r12
0x140065e89  nop
0x140065e8a  lock inc dword ptr [rbx+58h]
0x140065e8e  nop
0x140065e8f  test    rsi, rsi
0x140065e92  jz      loc_1400660B3
0x140065e98  mov     [rsi], rbx
0x140065e9b  add     rsi, 10h
0x140065e9f  jz      short loc_140065EAD
0x140065ea1  mov     eax, 8000h
0x140065ea6  jmp     short loc_140065EC9
0x140065ea8  test    rsi, rsi
0x140065eab  jnz     short loc_140065E98
0x140065ead  lea     rcx, [r13+0A0h]; this
0x140065eb4  call    ?AllocateFromPool@CmsReservedPool@@QEAAPEAXXZ; CmsReservedPool::AllocateFromPool(void)
0x140065eb9  mov     rcx, rax; void *
0x140065ebc  mov     rsi, rax
0x140065ebf  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x140065ec4  mov     eax, 10008000h
0x140065ec9  mov     rdx, [rbp+80h+var_100]
0x140065ecd  mov     rcx, rax
0x140065ed0  mov     r9d, [rsp+180h+var_138]
0x140065ed5  mov     r12, rax
0x140065ed8  mov     r8d, [rsp+180h+var_134]
0x140065edd  mov     [rsi], rax
0x140065ee0  mov     rax, [rsp+180h+var_120]
0x140065ee5  mov     [rsi+8], r13
0x140065ee9  mov     bl, [rsi+0DCh]
0x140065eef  or      rcx, [rax]
0x140065ef2  mov     [rsi], rcx
0x140065ef5  mov     cl, [rax+0DCh]
0x140065efb  mov     rax, [rsp+180h+var_118]
0x140065f00  mov     [rsi+0DCh], cl
0x140065f06  mov     rcx, [rsp+180h+var_110]
0x140065f0b  mov     rdx, [rdx]
0x140065f0e  mov     rax, [rax]
0x140065f11  mov     rcx, [rcx]
0x140065f14  mov     [rsp+180h+var_158], rcx
0x140065f19  mov     rcx, [rsp+180h+var_108]
0x140065f1e  mov     rcx, [rcx]
0x140065f21  mov     [rsp+180h+Timeout], rcx
0x140065f26  mov     rcx, rsi
0x140065f29  call    _guard_dispatch_icall
0x140065f2e  xor     r9d, r9d; unsigned __int8
0x140065f31  xor     r8d, r8d; struct _SmsLsn *
0x140065f34  xor     edx, edx; unsigned __int8
0x140065f36  mov     rcx, rsi; this
0x140065f39  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140065f3e  mov     rcx, rsi; this
0x140065f41  mov     [rsi+0DCh], bl
0x140065f47  mov     [rsi], r12
0x140065f4a  call    ?Release@CmsTransactionContext@@QEAAXXZ; CmsTransactionContext::Release(void)
0x140065f4f  mov     rax, [r15+10h]
0x140065f53  or      ecx, 0FFFFFFFFh
0x140065f56  nop
0x140065f57  lock xadd [rax], ecx
0x140065f5b  lea     eax, [rcx-1]
0x140065f5e  xor     r12d, r12d
0x140065f61  nop
0x140065f62  test    eax, eax
0x140065f64  jnz     short loc_140065F7B
0x140065f66  mov     rcx, [r15+20h]; Event
0x140065f6a  xor     r8d, r8d; Wait
0x140065f6d  xor     edx, edx; Increment
0x140065f6f  call    cs:__imp_KeSetEvent
0x140065f76  nop     dword ptr [rax+rax+00h]
0x140065f7b  mov     r13, [rsp+180h+var_128]
0x140065f80  mov     r8d, [rsp+180h+var_130]
0x140065f85  cmp     r8d, edi
0x140065f88  jb      loc_140065D66
0x140065f8e  xor     r9d, r9d; Alertable
0x140065f91  mov     [rsp+180h+Timeout], r12; Timeout
0x140065f96  xor     r8d, r8d; WaitMode
0x140065f99  lea     rcx, [rbp+80h+Event]; Object
0x140065f9d  xor     edx, edx; WaitReason
0x140065f9f  call    cs:__imp_KeWaitForSingleObject
0x140065fa6  nop     dword ptr [rax+rax+00h]
0x140065fab  test    r14, r14
0x140065fae  jnz     short loc_140065FD8
0x140065fb0  mov     rcx, [rbp+80h+var_40]
0x140065fb4  xor     rcx, rsp; StackCookie
0x140065fb7  call    __security_check_cookie
0x140065fbc  mov     rbx, [rsp+180h+arg_10]
0x140065fc4  add     rsp, 150h
0x140065fcb  pop     r15
0x140065fcd  pop     r14
0x140065fcf  pop     r13
0x140065fd1  pop     r12
0x140065fd3  pop     rdi
0x140065fd4  pop     rsi
0x140065fd5  pop     rbp
0x140065fd6  retn
0x140065fd8  lea     rax, [rbp+80h+var_B0]
0x140065fdc  cmp     r14, rax
0x140065fdf  jz      short loc_140065FB0
0x140065fe1  mov     rcx, r14; void *
0x140065fe4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140065fe9  jmp     short loc_140065FB0
0x140065feb  mov     eax, r15d
0x140065fee  mov     ecx, r15d
0x140065ff1  jmp     loc_140065CB3
0x140065ff6  cmp     ebx, 5DCh
0x140065ffc  ja      loc_140065CBF
0x140066002  cmp     ebx, 3E8h
0x140066008  mov     edi, eax
0x14006600a  cmova   edi, ecx
0x14006600d  jmp     loc_140065CBF
0x140066012  mov     esi, edi
0x140066014  mov     eax, 68h ; 'h'
0x140066019  mul     rsi
0x14006601c  mov     rbx, rax
0x14006601f  cmovb   rbx, rcx
0x140066023  mov     rcx, rbx; unsigned __int64
0x140066026  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14006602b  mov     r14, rax
0x14006602e  test    rax, rax
0x140066031  jz      loc_140065D50
0x140066037  mov     r8, rbx; Size
0x14006603a  xor     edx, edx; Val
0x14006603c  mov     rcx, rax; void *
0x14006603f  call    memset
0x140066044  mov     edx, esi
0x140066046  mov     rcx, r14
0x140066049  call    ??$__builtin_array_init_helper@UWorker@?1???$ParallelWork@V_lambda_1_@?1???$ParallelTuPageTableWork@P6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@$$QEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@CmsHashTable@@QEAAJK$$QEAV_lambda_1_@?1???$ParallelTuPageTableWork@P6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAV2@$$QEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV6@AEAPEAU7@@Z@@Z@@@YAXPEAUWorker@?1???$ParallelWork@V_lambda_1_@?1???$ParallelTuPageTableWork@P6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@$$QEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@CmsHashTable@@QEAAJK$$QEAV_lambda_1_@?1???$ParallelTuPageTableWork@P6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAV1@$$QEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@Z@_K@Z; __builtin_array_init_helper<`CmsHashTable::ParallelWork<`CmsBPlusTable::ParallelTuPageTableWork<void (*)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_>(ulong,`CmsBPlusTable::ParallelTuPageTableWork<void (*)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_ &&)'::`2'::Worker>(`CmsHashTable::ParallelWork<`CmsBPlusTable::ParallelTuPageTableWork<void (*)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_>(ulong,`CmsBPlusTable::ParallelTuPageTableWork<void (*)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_ &&)'::`2'::Worker *,unsigned __int64)
0x14006604e  jmp     loc_140065D57
0x140066053  lea     rcx, [r15+28h]; struct _MS_WORK_QUEUE_ITEM *
0x140066057  mov     r8, r15; void *
0x14006605a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$ParallelWork@V_lambda_1_@?1???$ParallelTuPageTableWork@AEAP6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@AEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@CmsHashTable@@QEAAJK$$QEAV1?1???$ParallelTuPageTableWork@AEAP6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAV2@AEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@Z@SA@PEAX@Z; void (*)(void *)
0x140066061  call    ?MsInitializeAndTryQueueWorkItem@@YAEPEAU_MS_WORK_QUEUE_ITEM@@P6AXPEAX@Z1W4_WORK_QUEUE_TYPE@@@Z; MsInitializeAndTryQueueWorkItem(_MS_WORK_QUEUE_ITEM *,void (*)(void *),void *,_WORK_QUEUE_TYPE)
0x140066066  test    al, al
0x140066068  jnz     loc_140065F80
0x14006606e  jmp     loc_140065DD3
0x140066073  lea     rcx, [rbx+40h]; Lookaside
0x140066077  cmp     [rbx+9], r12b
0x14006607b  jz      loc_1401F63F0
0x140066081  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140066088  nop     dword ptr [rax+rax+00h]
0x14006608d  nop
0x14006608e  jmp     loc_1401F63FC
0x140066093  test    ecx, ecx
0x140066095  js      loc_140065E86
0x14006609b  lea     rcx, [rbx+40h]; ListHead
0x14006609f  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400660a6  nop     dword ptr [rax+rax+00h]
0x1400660ab  mov     rsi, rax
0x1400660ae  jmp     loc_140065E8F
  ... truncated ...
```
