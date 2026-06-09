# VIDMM_GLOBAL::ReclaimOneAllocation(VIDMM_PAGING_QUEUE *,VIDMM_ALLOC *,unsigned __int64 *,_D3DDDI_RECLAIM_RESULT *)

- ea: `0x1400efba8`
- end: `0x1400f03f1`
- name: `?ReclaimOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_ALLOC@@PEA_KPEAW4_D3DDDI_RECLAIM_RESULT@@@Z`
- size: `2121`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_QUEUE *@<rdx>, struct VIDMM_ALLOC *@<r8>, unsigned __int64 *@<r9>, enum _D3DDDI_RECLAIM_RESULT *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f129c`

## callees

- `0x140004268`
- `0x14001e960`
- `0x14002bcc0`
- `0x14002bddc`
- `0x14002d8cc`
- `0x14002dab4`
- `0x14002eba4`
- `0x140030854`
- `0x140031434`
- `0x14003196c`
- `0x140034678`
- `0x140036d98`
- `0x140058f50`
- `0x140059030`
- `0x140059380`
- `0x1400b85e0`
- `0x1400b86a4`
- `0x1400ea904`
- `0x1400ee6e4`
- `0x1400efba8`
- `0x1400f4524`
- `0x1400f4b80`
- `0x1400f5f60`
- `0x140115f00`
- `0x140119e10`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400f0106`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f01e0`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f0106`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f01e0`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f0124`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f0200`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f0124`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f0200`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400efd9a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400eff45`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f030a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400efd9a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400eff45`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f030a`
- `watchdog!WdLogSingleEntry1` at `0x1400efdc1`
- `watchdog!WdLogSingleEntry1` at `0x1400efeb3`
- `watchdog!WdLogSingleEntry1` at `0x1400effb5`
- `watchdog!WdLogSingleEntry1` at `0x1400f0167`
- `watchdog!WdLogSingleEntry1` at `0x1400f024f`
- `watchdog!WdLogSingleEntry1` at `0x1400f02b0`
- `watchdog!WdLogSingleEntry1` at `0x1400efdc1`
- `watchdog!WdLogSingleEntry1` at `0x1400efeb3`
- `watchdog!WdLogSingleEntry1` at `0x1400effb5`
- `watchdog!WdLogSingleEntry1` at `0x1400f0167`
- `watchdog!WdLogSingleEntry1` at `0x1400f024f`
- `watchdog!WdLogSingleEntry1` at `0x1400f02b0`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400efbcf`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400efd53`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400eff35`
- `dxgkrnl!DxgkVidMmAllowFailOnOfferReclaimErrors` at `0x1400efde8`
- `dxgkrnl!DxgkVidMmAllowFailOnOfferReclaimErrors` at `0x1400efde8`

## string_xrefs

- `0x1400effc6`: `Allocation 0x%p was marked as decommittable, but the caller did not provide a result output`
- `0x1400f017c`: `Failed to recommit the backing store for local alloc %p during Reclaim`
- `0x1400f0260`: `Failed to recommit global alloc 0x%p backing store`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::ReclaimOneAllocation(
        VIDMM_GLOBAL *this,
        struct VIDMM_PAGING_QUEUE *a2,
        __int64 **a3,
        unsigned __int64 *a4,
        enum _D3DDDI_RECLAIM_RESULT *a5)
{
  enum _D3DDDI_RECLAIM_RESULT *v5; // r13
  __int64 *v8; // rax
  __int64 v9; // rdi
  int v10; // ecx
  int v12; // ebx
  unsigned __int8 v13; // al
  int v14; // ebx
  __int64 v15; // rcx
  int v16; // r8d
  struct VIDMM_LOCAL_ALLOC *v17; // r12
  int v18; // r9d
  __int64 v19; // r13
  enum _D3DDDI_RECLAIM_RESULT *v20; // rax
  enum _D3DDDI_RECLAIM_RESULT *v21; // rdi
  __int64 v22; // rax
  struct VIDMM_PROCESS *v23; // rdx
  int v24; // edx
  int v25; // r8d
  enum _D3DDDI_RECLAIM_RESULT *v26; // r13
  enum _D3DDDI_RECLAIM_RESULT *v27; // r14
  struct VIDMM_PAGING_QUEUE *v28; // rdi
  enum _D3DDDI_RECLAIM_RESULT *v29; // rbx
  _QWORD *v30; // rax
  int v31; // ecx
  int v32; // r8d
  enum _D3DDDI_RECLAIM_RESULT *i; // rax
  __int64 v34; // rcx
  __int64 v35; // rbx
  int v36; // ecx
  int v37; // r8d
  __int64 v38; // r12
  __int64 v39; // rcx
  int v40; // ecx
  int v41; // r8d
  _QWORD *v42; // rax
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v44; // [rsp+50h] [rbp-B0h] BYREF
  char v45; // [rsp+51h] [rbp-AFh]
  int v46; // [rsp+54h] [rbp-ACh]
  enum _D3DDDI_RECLAIM_RESULT *v47; // [rsp+58h] [rbp-A8h]
  __int64 v48; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v49; // [rsp+68h] [rbp-98h] BYREF
  int v50; // [rsp+70h] [rbp-90h]
  struct VIDMM_PAGING_QUEUE *v51; // [rsp+78h] [rbp-88h]
  enum _D3DDDI_RECLAIM_RESULT *v52; // [rsp+80h] [rbp-80h]
  __int64 v53; // [rsp+88h] [rbp-78h]
  DXGFASTMUTEX *v54; // [rsp+90h] [rbp-70h]
  unsigned __int64 *v55; // [rsp+98h] [rbp-68h]
  struct _KAPC_STATE ApcState[2]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = a5;
  v55 = a4;
  v51 = a2;
  v52 = a5;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(this) + 24) = a3;
    WdLogGlobalForLineNumber = 7365;
  }
  v8 = *a3;
  v49 = 0;
  v9 = *v8;
  v10 = *(_DWORD *)(*v8 + 32) & 0x40;
  if ( v10 && !a5 )
  {
    WdLogSingleEntry1(1, a3);
    WdLogGlobalForLineNumber = 7379;
    DxgkLogInternalTriageEvent(
      v31,
      0x40000,
      v32,
      (unsigned int)L"Allocation 0x%p was marked as decommittable, but the caller did not provide a result output",
      (__int64)a3,
      0,
      0,
      0);
    VidSchMarkDeviceAsError(a3[1][4], 20);
    return 3221225485LL;
  }
  if ( (*((_BYTE *)this + 37225) & 0x20) != 0 )
    return 0;
  v12 = *((_DWORD *)this + 786);
  v48 = *(_QWORD *)v9;
  if ( !v10 || (v13 = 1, (v12 & 0x10000) == 0) )
    v13 = 0;
  v14 = v12 & 8;
  v44 = v13;
  if ( v13 )
  {
    VIDMM_GLOBAL::ForceDecommitOffer(this, (struct VIDMM_ALLOC *)a3);
  }
  else if ( v14 )
  {
    VIDMM_GLOBAL::ForceDiscardOffer(this, (struct VIDMM_ALLOC *)a3);
  }
  v45 = 0;
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
    (DXGAUTOPUSHLOCKEXCLUSIVE *)ApcState,
    (VIDMM_GLOBAL *)((char *)this + 36408));
  if ( *(_QWORD *)(v9 + 272) )
    VIDMM_GLOBAL::RemoveAllocationFromOfferList(this, (struct VIDMM_GLOBAL_ALLOC *)v9);
  if ( *(_QWORD *)(v9 + 288) )
  {
    VIDMM_GLOBAL::RemoveAllocationFromDecommitList(this, (struct VIDMM_GLOBAL_ALLOC *)v9);
    v45 = 1;
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)ApcState);
  v54 = (DXGFASTMUTEX *)(v9 + 136);
  DXGFASTMUTEX::Acquire((DXGFASTMUTEX *)(v9 + 136));
  v15 = *((unsigned __int16 *)a3[12] + 4);
  *((_WORD *)a3[12] + 4) = 0;
  v16 = (__int16)v15;
  v46 = (__int16)v15;
  if ( (_WORD)v15 )
  {
    LODWORD(v17) = 0;
    v18 = *(_DWORD *)(v9 + 32) & 0x20;
    v50 = v18;
    if ( v45 )
    {
      v15 = *(_QWORD *)(*(_QWORD *)(v9 + 48) + 8LL);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v15 + 80) + 440LL), -*(_QWORD *)(v48 + 16));
    }
    if ( !v18 )
    {
      if ( !v44 && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 48) + 8LL) + 160LL) & 4) == 0 )
      {
        v44 = 1;
        LODWORD(v17) = VIDMM_GLOBAL::CommitGlobalBackingStore(
                         this,
                         (struct VIDMM_GLOBAL_ALLOC *)v9,
                         *(struct VIDMM_PROCESS **)(*((_QWORD *)v51 + 12) + 8LL),
                         0,
                         &v44);
        if ( (int)v17 >= 0 )
        {
          v15 = v9 + 112;
          for ( i = *(enum _D3DDDI_RECLAIM_RESULT **)(v9 + 112); ; i = *(enum _D3DDDI_RECLAIM_RESULT **)v47 )
          {
            v47 = i;
            if ( i == (enum _D3DDDI_RECLAIM_RESULT *)v15 )
            {
              v16 = v46;
              v18 = v50;
              *(_BYTE *)(v9 + 42) = 0;
              goto LABEL_19;
            }
            v17 = (struct VIDMM_LOCAL_ALLOC *)(i - 12);
            v34 = *((_QWORD *)i - 5);
            memset(ApcState, 0, 48);
            v53 = (__int64)(i - 12);
            KeStackAttachProcess(*(PRKPROCESS *)(v34 + 16), ApcState);
            LODWORD(v17) = VIDMM_GLOBAL::CommitLocalBackingStore(this, v17);
            KeUnstackDetachProcess(ApcState);
            if ( (int)v17 < 0 )
              break;
            v15 = v9 + 112;
          }
          v35 = v53;
          WdLogSingleEntry1(1, v53);
          WdLogGlobalForLineNumber = 7520;
          DxgkLogInternalTriageEvent(
            v36,
            0x40000,
            v37,
            (unsigned int)L"Failed to recommit the backing store for local alloc %p during Reclaim",
            v35,
            0,
            0,
            0);
          v38 = *((_QWORD *)v47 + 1);
          if ( v38 != v9 + 112 )
          {
            do
            {
              v39 = *(_QWORD *)(v38 - 40);
              memset(ApcState, 0, 48);
              KeStackAttachProcess(*(PRKPROCESS *)(v39 + 16), ApcState);
              VIDMM_GLOBAL::UncommitLocalBackingStore(this, (struct VIDMM_LOCAL_ALLOC *)(v38 - 48), 1);
              KeUnstackDetachProcess(ApcState);
              v38 = *(_QWORD *)(v38 + 8);
            }
            while ( v38 != v9 + 112 );
            v5 = v52;
          }
          VIDMM_GLOBAL::UncommitGlobalBackingStore(this, (struct VIDMM_GLOBAL_ALLOC *)v9, 0);
        }
      }
      LODWORD(v17) = 0;
      *((_WORD *)a3[12] + 4) = 3;
      *v5 = D3DDDI_RECLAIM_RESULT_NOT_COMMITTED;
      _InterlockedAdd(&dword_1400877EC, 1u);
      WdLogSingleEntry1(6, v9);
      WdLogGlobalForLineNumber = 7570;
      DxgkLogInternalTriageEvent(
        v40,
        262145,
        v41,
        (unsigned int)L"Failed to recommit global alloc 0x%p backing store",
        v9,
        0,
        0,
        0);
      goto LABEL_33;
    }
LABEL_19:
    *(_DWORD *)(v9 + 32) &= ~0x40u;
    if ( !a5 )
    {
      *(_BYTE *)(v9 + 42) = 0;
LABEL_25:
      if ( (byte_140087201 & 1) != 0 )
        McTemplateK0puu_EtwWriteTransfer(
          v15,
          (unsigned int)EventReclaimAllocation,
          v16,
          (_DWORD)a3,
          *(_BYTE *)(v9 + 304),
          v16);
      if ( v14 )
      {
        LODWORD(v19) = v46;
      }
      else
      {
        v19 = v46;
        if ( v46 != 3 && (v46 != 2 || (*(_DWORD *)(v9 + 24) & 0x4000000) == 0) && *(_DWORD *)(v9 + 72) )
        {
          if ( g_IsInternalReleaseOrDbg )
          {
            v30 = (_QWORD *)WdLogNewEntry5_WdTrace(v15);
            v30[3] = a3;
            v30[4] = 0;
            v30[5] = v19;
            v30[6] = ((unsigned __int64)*(unsigned int *)(v9 + 24) >> 26) & 1;
            v30[7] = 1;
            WdLogGlobalForLineNumber = 7778;
          }
          goto LABEL_33;
        }
      }
      if ( g_IsInternalReleaseOrDbg )
      {
        v42 = (_QWORD *)WdLogNewEntry5_WdTrace(v15);
        v42[3] = a3;
        v42[4] = v14 != 0;
        v42[5] = (int)v19;
        v42[6] = ((unsigned __int64)*(unsigned int *)(v9 + 24) >> 26) & 1;
        v42[7] = 0;
        WdLogGlobalForLineNumber = 7725;
      }
      v20 = (enum _D3DDDI_RECLAIM_RESULT *)(v9 + 112);
      v21 = *(enum _D3DDDI_RECLAIM_RESULT **)(v9 + 112);
      v52 = v20;
      while ( 1 )
      {
        v47 = v21;
        if ( v21 == v20 )
          break;
        v26 = v21 - 4;
        v27 = (enum _D3DDDI_RECLAIM_RESULT *)*((_QWORD *)v21 - 2);
        if ( v27 != v21 - 4 )
        {
          v28 = v51;
          do
          {
            v29 = v27 - 10;
            if ( (*(v27 - 2) & 1) == 0 && VIDMM_ALLOC::HasAnyResidencyReferences((VIDMM_ALLOC *)(v27 - 10)) )
            {
              memset(ApcState, 0, 0x58u);
              LODWORD(ApcState[0].ApcListHead[0].Flink) = 210;
              ApcState[0].ApcListHead[1].Flink = (struct _LIST_ENTRY *)(v27 - 10);
              LODWORD(v17) = VIDMM_GLOBAL::QueueDeferredCommand(
                               this,
                               v28,
                               (struct _VIDMM_DEFERRED_COMMAND *)ApcState,
                               0,
                               &v49);
              if ( (v29[7] & 0x20) != 0 )
              {
                *((_QWORD *)v29 + 102) = v49;
                *((_QWORD *)v29 + 99) = v28;
              }
            }
            v27 = *(enum _D3DDDI_RECLAIM_RESULT **)v27;
          }
          while ( v27 != v26 );
          v21 = v47;
          v20 = v52;
        }
        v21 = *(enum _D3DDDI_RECLAIM_RESULT **)v21;
      }
LABEL_33:
      DXGFASTMUTEX::Release(v54);
      if ( (_DWORD)v17 == 259 )
      {
        if ( v55 )
        {
          *v55 = v49;
        }
        else
        {
          VIDMM_GLOBAL::WaitForFence(this, *((struct _VIDSCH_SYNC_OBJECT **)v51 + 11), v49);
          LODWORD(v17) = 0;
        }
      }
      return (unsigned int)v17;
    }
    if ( v16 == 1 )
    {
      *a5 = D3DDDI_RECLAIM_RESULT_OK;
    }
    else
    {
      if ( v16 == 3 )
        *a5 = D3DDDI_RECLAIM_RESULT_DISCARDED;
      if ( v18
        && (*(_DWORD *)(v48 + 64) & 1) == 0
        && *(_BYTE *)(v9 + 42)
        && !*(_BYTE *)(v9 + 43)
        && (*(_DWORD *)(v9 + 32) & 8) != 0 )
      {
        if ( !v14 )
          goto LABEL_25;
        v22 = *(_QWORD *)(v9 + 48);
        if ( v22 )
        {
          v23 = *(struct VIDMM_PROCESS **)(v22 + 8);
          if ( v23 )
          {
            VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)ApcState, v23, 1);
            v17 = (struct VIDMM_LOCAL_ALLOC *)(*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v9 + 232) + 40LL))(
                                                *(_QWORD *)(v9 + 232),
                                                *(_QWORD *)(v9 + 240),
                                                *(_QWORD *)(*(_QWORD *)(v9 + 48) + 16LL),
                                                *(_QWORD *)(v48 + 16));
            VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)ApcState);
            if ( (int)v17 < 0 )
            {
              *(_BYTE *)(v9 + 42) = 0;
              WdLogSingleEntry1(4, v17);
              LODWORD(v17) = 0;
              WdLogGlobalForLineNumber = 7643;
            }
            else
            {
              *a5 = D3DDDI_RECLAIM_RESULT_OK;
              *(_QWORD *)(v9 + 312) = 0;
              WdLogSingleEntry1(4, v9);
              WdLogGlobalForLineNumber = 7638;
            }
            if ( (byte_140087201 & 1) != 0 )
              McTemplateK0pqqt_EtwWriteTransfer(v15, v24, v25, v9, v43, *(_QWORD *)(v48 + 16) >> 12, 1);
            *(_DWORD *)(v9 + 32) &= ~8u;
            v16 = v46;
          }
        }
        goto LABEL_82;
      }
    }
    if ( !v14 )
      goto LABEL_25;
LABEL_82:
    *a5 = D3DDDI_RECLAIM_RESULT_DISCARDED;
    goto LABEL_25;
  }
  WdLogSingleEntry1(2, a3);
  WdLogGlobalForLineNumber = 7443;
  if ( a5 )
    *a5 = D3DDDI_RECLAIM_RESULT_DISCARDED;
  DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v9 + 136));
  return DxgkVidMmAllowFailOnOfferReclaimErrors() != 0 ? 0xC000000D : 0;
}

```

## disassembly

```asm
0x1400efba8  push    rbp
0x1400efbaa  push    rbx
0x1400efbab  push    rsi
0x1400efbac  push    rdi
0x1400efbad  push    r12
0x1400efbaf  push    r13
0x1400efbb1  push    r14
0x1400efbb3  push    r15
0x1400efbb5  lea     rbp, [rsp-18h]
0x1400efbba  sub     rsp, 118h
0x1400efbc1  mov     rax, cs:__security_cookie
0x1400efbc8  xor     rax, rsp
0x1400efbcb  mov     [rbp+50h+var_50], rax
0x1400efbcf  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400efbd6  xor     r12d, r12d
0x1400efbd9  mov     r13, [rbp+50h+arg_20]
0x1400efbe0  mov     r14, r8
0x1400efbe3  mov     [rbp+50h+var_B8], r9
0x1400efbe7  mov     r15, rcx
0x1400efbea  mov     [rsp+150h+var_D8], rdx
0x1400efbef  mov     [rbp+50h+var_D0], r13
0x1400efbf3  cmp     [rax], r12b
0x1400efbf6  jnz     loc_1400EFD9A
0x1400efbfc  mov     rax, [r14]
0x1400efbff  mov     [rsp+150h+var_E8], r12
0x1400efc04  mov     rdi, [rax]
0x1400efc07  mov     ecx, [rdi+20h]
0x1400efc0a  and     ecx, 40h
0x1400efc0d  jnz     loc_1400EFFA5
0x1400efc13  test    byte ptr [r15+9169h], 20h
0x1400efc1b  jz      short loc_1400EFC40
0x1400efc1d  xor     eax, eax
0x1400efc1f  mov     rcx, [rbp+50h+var_50]
0x1400efc23  xor     rcx, rsp; StackCookie
0x1400efc26  call    __security_check_cookie
0x1400efc2b  add     rsp, 118h
0x1400efc32  pop     r15
0x1400efc34  pop     r14
0x1400efc36  pop     r13
0x1400efc38  pop     r12
0x1400efc3a  pop     rdi
0x1400efc3b  pop     rsi
0x1400efc3c  pop     rbx
0x1400efc3d  pop     rbp
0x1400efc3e  retn
0x1400efc40  mov     rax, [rdi]
0x1400efc43  mov     esi, 1
0x1400efc48  mov     ebx, [r15+0C48h]
0x1400efc4f  mov     [rsp+150h+var_F0], rax
0x1400efc54  test    ecx, ecx
0x1400efc56  jnz     loc_1400F000E
0x1400efc5c  mov     al, r12b
0x1400efc5f  and     ebx, 8
0x1400efc62  mov     [rsp+150h+var_100], al
0x1400efc66  test    al, al
0x1400efc68  jnz     loc_1400F0020
0x1400efc6e  test    ebx, ebx
0x1400efc70  jnz     loc_1400F0030
0x1400efc76  lea     rdx, [r15+8E38h]; struct DXGPUSHLOCK *
0x1400efc7d  mov     [rsp+150h+var_FF], r12b
0x1400efc82  lea     rcx, [rbp+50h+ApcState]; this
0x1400efc86  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1400efc8b  cmp     [rdi+110h], r12
0x1400efc92  jz      short loc_1400EFC9F
0x1400efc94  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400efc97  mov     rcx, r15; this
0x1400efc9a  call    ?RemoveAllocationFromOfferList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::RemoveAllocationFromOfferList(VIDMM_GLOBAL_ALLOC *)
0x1400efc9f  cmp     [rdi+120h], r12
0x1400efca6  jnz     loc_1400F0040
0x1400efcac  lea     rcx, [rbp+50h+ApcState]; this
0x1400efcb0  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400efcb5  lea     r12, [rdi+88h]
0x1400efcbc  mov     rcx, r12; this
0x1400efcbf  mov     [rbp+50h+var_C0], r12
0x1400efcc3  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400efcc8  mov     rax, [r14+60h]
0x1400efccc  xor     ecx, ecx
0x1400efcce  xchg    cx, [rax+8]
0x1400efcd2  movsx   r8d, cx
0x1400efcd6  mov     [rsp+150h+var_FC], r8d
0x1400efcdb  test    r8d, r8d
0x1400efcde  jz      loc_1400EFDB9
0x1400efce4  mov     r9d, [rdi+20h]
0x1400efce8  xor     r12d, r12d
0x1400efceb  and     r9d, 20h
0x1400efcef  mov     [rsp+150h+var_E0], r9d
0x1400efcf4  cmp     [rsp+150h+var_FF], r12b
0x1400efcf9  jnz     loc_1400F005E
0x1400efcff  test    r9d, r9d
0x1400efd02  jz      loc_1400F0083
0x1400efd08  and     dword ptr [rdi+20h], 0FFFFFFBFh
0x1400efd0c  test    r13, r13
0x1400efd0f  jz      loc_1400F0301
0x1400efd15  cmp     r8d, esi
0x1400efd18  jz      loc_1400F028F
0x1400efd1e  cmp     r8d, 3
0x1400efd22  jz      loc_1400F029C
0x1400efd28  test    r9d, r9d
0x1400efd2b  jnz     loc_1400EFE02
0x1400efd31  test    ebx, ebx
0x1400efd33  jnz     loc_1400F02F8
0x1400efd39  test    cs:byte_140087201, sil
0x1400efd40  jnz     loc_1400EFF82
0x1400efd46  test    ebx, ebx
0x1400efd48  jz      loc_1400EFF09
0x1400efd4e  mov     r13d, [rsp+150h+var_FC]
0x1400efd53  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400efd5a  cmp     byte ptr [rax], 0
0x1400efd5d  jnz     loc_1400F030A
0x1400efd63  lea     rax, [rdi+70h]
0x1400efd67  mov     rdi, [rax]
0x1400efd6a  mov     [rbp+50h+var_D0], rax
0x1400efd6e  mov     [rsp+150h+var_F8], rdi
0x1400efd73  cmp     rdi, rax
0x1400efd76  jnz     loc_1400EFECE
0x1400efd7c  mov     rcx, [rbp+50h+var_C0]; this
0x1400efd80  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400efd85  cmp     r12d, 103h
0x1400efd8c  jz      loc_1400F03BD
0x1400efd92  mov     eax, r12d
0x1400efd95  jmp     loc_1400EFC1F
0x1400efd9a  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400efda1  nop     dword ptr [rax+rax+00h]
0x1400efda6  mov     [rax+18h], r14
0x1400efdaa  mov     cs:WdLogGlobalForLineNumber, 1CC5h
0x1400efdb4  jmp     loc_1400EFBFC
0x1400efdb9  mov     rdx, r14
0x1400efdbc  mov     ecx, 2
0x1400efdc1  call    cs:__imp_WdLogSingleEntry1
0x1400efdc8  nop     dword ptr [rax+rax+00h]
0x1400efdcd  mov     cs:WdLogGlobalForLineNumber, 1D13h
0x1400efdd7  test    r13, r13
0x1400efdda  jnz     loc_1400F0055
0x1400efde0  mov     rcx, r12; this
0x1400efde3  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400efde8  call    cs:__imp_?DxgkVidMmAllowFailOnOfferReclaimErrors@@YAHXZ; DxgkVidMmAllowFailOnOfferReclaimErrors(void)
0x1400efdef  nop     dword ptr [rax+rax+00h]
0x1400efdf4  neg     eax
0x1400efdf6  sbb     eax, eax
0x1400efdf8  and     eax, 0C000000Dh
0x1400efdfd  jmp     loc_1400EFC1F
0x1400efe02  mov     rax, [rsp+150h+var_F0]
0x1400efe07  mov     eax, [rax+40h]
0x1400efe0a  test    sil, al
0x1400efe0d  jnz     loc_1400EFD31
0x1400efe13  cmp     byte ptr [rdi+2Ah], 0
0x1400efe17  jz      loc_1400EFD31
0x1400efe1d  cmp     byte ptr [rdi+2Bh], 0
0x1400efe21  jnz     loc_1400EFD31
0x1400efe27  mov     eax, [rdi+20h]
0x1400efe2a  test    al, 8
0x1400efe2c  jz      loc_1400EFD31
0x1400efe32  test    ebx, ebx
0x1400efe34  jz      loc_1400EFD39
0x1400efe3a  mov     rax, [rdi+30h]
0x1400efe3e  test    rax, rax
0x1400efe41  jz      loc_1400F02F8
0x1400efe47  mov     rdx, [rax+8]; struct VIDMM_PROCESS *
0x1400efe4b  test    rdx, rdx
0x1400efe4e  jz      loc_1400F02F8
0x1400efe54  mov     r8b, sil; bool
0x1400efe57  lea     rcx, [rbp+50h+ApcState]; this
0x1400efe5b  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400efe60  mov     rcx, [rdi+0E8h]
0x1400efe67  mov     rdx, [rsp+150h+var_F0]
0x1400efe6c  mov     r8, [rdi+30h]
0x1400efe70  mov     rax, [rcx]
0x1400efe73  mov     r9, [rdx+10h]
0x1400efe77  mov     r8, [r8+10h]
0x1400efe7b  mov     rdx, [rdi+0F0h]
0x1400efe82  mov     rax, [rax+28h]
0x1400efe86  call    _guard_dispatch_icall
0x1400efe8b  lea     rcx, [rbp+50h+ApcState]; this
0x1400efe8f  movsxd  r12, eax
0x1400efe92  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400efe97  xor     eax, eax
0x1400efe99  test    r12d, r12d
0x1400efe9c  js      loc_1400F02A5
0x1400efea2  mov     [r13+0], eax
0x1400efea6  mov     [rdi+138h], rax
0x1400efead  mov     rdx, rdi
0x1400efeb0  lea     ecx, [rax+4]
0x1400efeb3  call    cs:__imp_WdLogSingleEntry1
0x1400efeba  nop     dword ptr [rax+rax+00h]
0x1400efebf  mov     cs:WdLogGlobalForLineNumber, 1DD6h
0x1400efec9  jmp     loc_1400F02C9
0x1400efece  lea     r13, [rdi-10h]
0x1400efed2  mov     r14, [r13+0]
0x1400efed6  cmp     r14, r13
0x1400efed9  jz      short loc_1400EFF01
0x1400efedb  mov     rdi, [rsp+150h+var_D8]
0x1400efee0  lea     rbx, [r14-28h]
0x1400efee4  mov     eax, [rbx+20h]
0x1400efee7  test    sil, al
0x1400efeea  jz      loc_1400F0351
0x1400efef0  mov     r14, [r14]
0x1400efef3  cmp     r14, r13
0x1400efef6  jnz     short loc_1400EFEE0
0x1400efef8  mov     rdi, [rsp+150h+var_F8]
0x1400efefd  mov     rax, [rbp+50h+var_D0]
0x1400eff01  mov     rdi, [rdi]
0x1400eff04  jmp     loc_1400EFD6E
0x1400eff09  movsxd  r13, [rsp+150h+var_FC]
0x1400eff0e  cmp     r13d, 3
0x1400eff12  jz      loc_1400EFD53
0x1400eff18  cmp     r13d, 2
0x1400eff1c  jnz     short loc_1400EFF2B
0x1400eff1e  test    dword ptr [rdi+18h], 4000000h
0x1400eff25  jnz     loc_1400EFD53
0x1400eff2b  cmp     dword ptr [rdi+48h], 0
0x1400eff2f  jz      loc_1400EFD53
0x1400eff35  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400eff3c  cmp     byte ptr [rax], 0
0x1400eff3f  jz      loc_1400EFD7C
0x1400eff45  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400eff4c  nop     dword ptr [rax+rax+00h]
0x1400eff51  mov     [rax+18h], r14
0x1400eff55  mov     qword ptr [rax+20h], 0
0x1400eff5d  mov     [rax+28h], r13
0x1400eff61  mov     ecx, [rdi+18h]
0x1400eff64  shr     rcx, 1Ah
0x1400eff68  and     rcx, rsi
0x1400eff6b  mov     [rax+30h], rcx
0x1400eff6f  mov     [rax+38h], rsi
0x1400eff73  mov     cs:WdLogGlobalForLineNumber, 1E62h
0x1400eff7d  jmp     loc_1400EFD7C
0x1400eff82  mov     al, [rdi+130h]
0x1400eff88  lea     rdx, EventReclaimAllocation
0x1400eff8f  mov     byte ptr [rsp+150h+var_128], r8b
0x1400eff94  mov     r9, r14
0x1400eff97  mov     byte ptr [rsp+150h+var_130], al
0x1400eff9b  call    McTemplateK0puu_EtwWriteTransfer
0x1400effa0  jmp     loc_1400EFD46
0x1400effa5  test    r13, r13
0x1400effa8  jnz     loc_1400EFC13
0x1400effae  mov     rdx, r14
0x1400effb1  lea     ecx, [r13+1]
0x1400effb5  call    cs:__imp_WdLogSingleEntry1
0x1400effbc  nop     dword ptr [rax+rax+00h]
0x1400effc1  mov     [rsp+150h+var_118], r12
0x1400effc6  lea     r9, aAllocation0xPW; "Allocation 0x%p was marked as decommitt"...
0x1400effcd  mov     [rsp+150h+var_120], r12
0x1400effd2  mov     edx, 40000h
0x1400effd7  mov     [rsp+150h+var_128], r12
0x1400effdc  mov     [rsp+150h+var_130], r14
0x1400effe1  mov     cs:WdLogGlobalForLineNumber, 1CD3h
0x1400effeb  call    DxgkLogInternalTriageEvent
0x1400efff0  mov     rcx, [r14+8]
0x1400efff4  lea     edx, [r13+14h]
0x1400efff8  xor     r8d, r8d
0x1400efffb  mov     rcx, [rcx+20h]
0x1400effff  call    VidSchMarkDeviceAsError
0x1400f0004  mov     eax, 0C000000Dh
0x1400f0009  jmp     loc_1400EFC1F
0x1400f000e  mov     al, sil
0x1400f0011  bt      ebx, 10h
0x1400f0015  jb      loc_1400EFC5F
0x1400f001b  jmp     loc_1400EFC5C
0x1400f0020  mov     rdx, r14; struct VIDMM_ALLOC *
0x1400f0023  mov     rcx, r15; this
0x1400f0026  call    ?ForceDecommitOffer@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::ForceDecommitOffer(VIDMM_ALLOC *)
0x1400f002b  jmp     loc_1400EFC76
0x1400f0030  mov     rdx, r14; struct VIDMM_ALLOC *
0x1400f0033  mov     rcx, r15; this
0x1400f0036  call    ?ForceDiscardOffer@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::ForceDiscardOffer(VIDMM_ALLOC *)
0x1400f003b  jmp     loc_1400EFC76
0x1400f0040  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400f0043  mov     rcx, r15; this
0x1400f0046  call    ?RemoveAllocationFromDecommitList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::RemoveAllocationFromDecommitList(VIDMM_GLOBAL_ALLOC *)
0x1400f004b  mov     [rsp+150h+var_FF], sil
0x1400f0050  jmp     loc_1400EFCAC
0x1400f0055  mov     [r13+0], esi
0x1400f0059  jmp     loc_1400EFDE0
0x1400f005e  mov     rax, [rdi+30h]
0x1400f0062  mov     rdx, [rsp+150h+var_F0]
0x1400f0067  mov     rcx, [rax+8]
0x1400f006b  mov     rdx, [rdx+10h]
0x1400f006f  neg     rdx
0x1400f0072  mov     rax, [rcx+50h]
0x1400f0076  lock add [rax+1B8h], rdx
0x1400f007e  jmp     loc_1400EFCFF
0x1400f0083  cmp     [rsp+150h+var_100], r12b
0x1400f0088  jnz     loc_1400F0228
0x1400f008e  mov     rax, [rdi+30h]
0x1400f0092  mov     rcx, [rax+8]
0x1400f0096  mov     eax, [rcx+0A0h]
0x1400f009c  test    al, 4
0x1400f009e  jnz     loc_1400F0228
0x1400f00a4  mov     r8, [rsp+150h+var_D8]
0x1400f00a9  lea     rax, [rsp+150h+var_100]
0x1400f00ae  mov     [rsp+150h+var_100], sil
0x1400f00b3  xor     r9d, r9d; void *
0x1400f00b6  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400f00b9  mov     [rsp+150h+var_130], rax; unsigned __int8 *
0x1400f00be  mov     rcx, r15; this
0x1400f00c1  mov     r8, [r8+60h]
0x1400f00c5  mov     r8, [r8+8]; struct VIDMM_PROCESS *
0x1400f00c9  call    ?CommitGlobalBackingStore@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@PEAVVIDMM_PROCESS@@PEAXPEAE@Z; VIDMM_GLOBAL::CommitGlobalBackingStore(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS *,void *,uchar *)
0x1400f00ce  mov     r12d, eax
0x1400f00d1  test    eax, eax
  ... truncated ...
```
