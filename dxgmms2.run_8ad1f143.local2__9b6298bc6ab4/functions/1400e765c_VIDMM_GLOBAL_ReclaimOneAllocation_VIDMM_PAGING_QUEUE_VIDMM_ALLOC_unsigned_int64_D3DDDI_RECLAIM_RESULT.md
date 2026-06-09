# VIDMM_GLOBAL::ReclaimOneAllocation(VIDMM_PAGING_QUEUE *,VIDMM_ALLOC *,unsigned __int64 *,_D3DDDI_RECLAIM_RESULT *)

- ea: `0x1400e765c`
- end: `0x1400e7ea5`
- name: `?ReclaimOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_ALLOC@@PEA_KPEAW4_D3DDDI_RECLAIM_RESULT@@@Z`
- size: `2121`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_QUEUE *@<rdx>, struct VIDMM_ALLOC *@<r8>, unsigned __int64 *@<r9>, enum _D3DDDI_RECLAIM_RESULT *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140118f88`

## callees

- `0x1400045ec`
- `0x1400204c0`
- `0x14002ec00`
- `0x14002ed1c`
- `0x14002fbac`
- `0x14002fd94`
- `0x140030fc4`
- `0x140032a04`
- `0x1400335c4`
- `0x1400336b8`
- `0x140035984`
- `0x140037d38`
- `0x140058680`
- `0x140058760`
- `0x140058ac0`
- `0x1400b4c38`
- `0x1400b4cfc`
- `0x1400e2504`
- `0x1400e5be4`
- `0x1400e765c`
- `0x1400ef544`
- `0x1400efba0`
- `0x1400f0f80`
- `0x140102eb4`
- `0x140113110`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400e7bba`
- `ntoskrnl!KeStackAttachProcess` at `0x1400e7c94`
- `ntoskrnl!KeStackAttachProcess` at `0x1400e7bba`
- `ntoskrnl!KeStackAttachProcess` at `0x1400e7c94`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400e7bd8`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400e7cb4`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400e7bd8`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400e7cb4`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e784e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e79f9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e7dbe`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e784e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e79f9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e7dbe`
- `watchdog!WdLogSingleEntry1` at `0x1400e7875`
- `watchdog!WdLogSingleEntry1` at `0x1400e7967`
- `watchdog!WdLogSingleEntry1` at `0x1400e7a69`
- `watchdog!WdLogSingleEntry1` at `0x1400e7c1b`
- `watchdog!WdLogSingleEntry1` at `0x1400e7d03`
- `watchdog!WdLogSingleEntry1` at `0x1400e7d64`
- `watchdog!WdLogSingleEntry1` at `0x1400e7875`
- `watchdog!WdLogSingleEntry1` at `0x1400e7967`
- `watchdog!WdLogSingleEntry1` at `0x1400e7a69`
- `watchdog!WdLogSingleEntry1` at `0x1400e7c1b`
- `watchdog!WdLogSingleEntry1` at `0x1400e7d03`
- `watchdog!WdLogSingleEntry1` at `0x1400e7d64`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e7683`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e7807`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e79e9`
- `dxgkrnl!DxgkVidMmAllowFailOnOfferReclaimErrors` at `0x1400e789c`
- `dxgkrnl!DxgkVidMmAllowFailOnOfferReclaimErrors` at `0x1400e789c`

## string_xrefs

- `0x1400e7a7a`: `Allocation 0x%p was marked as decommittable, but the caller did not provide a result output`
- `0x1400e7c30`: `Failed to recommit the backing store for local alloc %p during Reclaim`
- `0x1400e7d14`: `Failed to recommit global alloc 0x%p backing store`

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
  unsigned __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // r8d
  struct VIDMM_LOCAL_ALLOC *v18; // r12
  int v19; // r9d
  __int64 v20; // r13
  enum _D3DDDI_RECLAIM_RESULT *v21; // rax
  enum _D3DDDI_RECLAIM_RESULT *v22; // rdi
  __int64 v23; // rax
  int v24; // r8d
  enum _D3DDDI_RECLAIM_RESULT *v25; // r13
  enum _D3DDDI_RECLAIM_RESULT *v26; // r14
  struct VIDMM_PAGING_QUEUE *v27; // rdi
  enum _D3DDDI_RECLAIM_RESULT *v28; // rbx
  _QWORD *v29; // rax
  int v30; // ecx
  int v31; // r8d
  enum _D3DDDI_RECLAIM_RESULT *i; // rax
  __int64 v33; // rcx
  __int64 v34; // rbx
  int v35; // ecx
  int v36; // r8d
  __int64 v37; // r12
  __int64 v38; // rcx
  int v39; // ecx
  int v40; // r8d
  _QWORD *v41; // rax
  int v42; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v43; // [rsp+50h] [rbp-B0h] BYREF
  char v44; // [rsp+51h] [rbp-AFh]
  int v45; // [rsp+54h] [rbp-ACh]
  enum _D3DDDI_RECLAIM_RESULT *v46; // [rsp+58h] [rbp-A8h]
  __int64 v47; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  int v49; // [rsp+70h] [rbp-90h]
  struct VIDMM_PAGING_QUEUE *v50; // [rsp+78h] [rbp-88h]
  enum _D3DDDI_RECLAIM_RESULT *v51; // [rsp+80h] [rbp-80h]
  __int64 v52; // [rsp+88h] [rbp-78h]
  DXGFASTMUTEX *v53; // [rsp+90h] [rbp-70h]
  unsigned __int64 *v54; // [rsp+98h] [rbp-68h]
  struct _KAPC_STATE ApcState[2]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = a5;
  v54 = a4;
  v50 = a2;
  v51 = a5;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(this, a2) + 24) = a3;
    WdLogGlobalForLineNumber = 7224;
  }
  v8 = *a3;
  v48 = 0;
  v9 = *v8;
  v10 = *(_DWORD *)(*v8 + 32) & 0x40;
  if ( v10 && !a5 )
  {
    WdLogSingleEntry1(1, a3);
    WdLogGlobalForLineNumber = 7238;
    DxgkLogInternalTriageEvent(
      v30,
      0x40000,
      v31,
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
  v47 = *(_QWORD *)v9;
  if ( !v10 || (v13 = 1, (v12 & 0x10000) == 0) )
    v13 = 0;
  v14 = v12 & 8;
  v43 = v13;
  if ( v13 )
  {
    VIDMM_GLOBAL::ForceDecommitOffer(this, (struct VIDMM_ALLOC *)a3);
  }
  else if ( v14 )
  {
    VIDMM_GLOBAL::ForceDiscardOffer(this, (struct VIDMM_ALLOC *)a3);
  }
  v44 = 0;
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
    (DXGAUTOPUSHLOCKEXCLUSIVE *)ApcState,
    (VIDMM_GLOBAL *)((char *)this + 36408));
  if ( *(_QWORD *)(v9 + 272) )
    VIDMM_GLOBAL::RemoveAllocationFromOfferList(this, (struct VIDMM_GLOBAL_ALLOC *)v9);
  if ( *(_QWORD *)(v9 + 288) )
  {
    VIDMM_GLOBAL::RemoveAllocationFromDecommitList(this, (struct VIDMM_GLOBAL_ALLOC *)v9);
    v44 = 1;
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)ApcState);
  v53 = (DXGFASTMUTEX *)(v9 + 136);
  DXGFASTMUTEX::Acquire((DXGFASTMUTEX *)(v9 + 136));
  v16 = *((unsigned __int16 *)a3[12] + 4);
  *((_WORD *)a3[12] + 4) = 0;
  v17 = (__int16)v16;
  v45 = (__int16)v16;
  if ( (_WORD)v16 )
  {
    LODWORD(v18) = 0;
    v19 = *(_DWORD *)(v9 + 32) & 0x20;
    v49 = v19;
    if ( v44 )
    {
      v16 = *(_QWORD *)(*(_QWORD *)(v9 + 48) + 8LL);
      v15 = -*(_QWORD *)(v47 + 16);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v16 + 72) + 440LL), v15);
    }
    if ( !v19 )
    {
      if ( !v43 && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 48) + 8LL) + 152LL) & 4) == 0 )
      {
        v43 = 1;
        LODWORD(v18) = VIDMM_GLOBAL::CommitGlobalBackingStore(
                         this,
                         (struct VIDMM_GLOBAL_ALLOC *)v9,
                         *(struct VIDMM_PROCESS **)(*((_QWORD *)v50 + 12) + 8LL),
                         0,
                         &v43);
        if ( (int)v18 >= 0 )
        {
          v16 = v9 + 112;
          for ( i = *(enum _D3DDDI_RECLAIM_RESULT **)(v9 + 112); ; i = *(enum _D3DDDI_RECLAIM_RESULT **)v46 )
          {
            v46 = i;
            if ( i == (enum _D3DDDI_RECLAIM_RESULT *)v16 )
            {
              v17 = v45;
              v19 = v49;
              *(_BYTE *)(v9 + 42) = 0;
              goto LABEL_19;
            }
            v18 = (struct VIDMM_LOCAL_ALLOC *)(i - 12);
            v33 = *((_QWORD *)i - 5);
            memset(ApcState, 0, 48);
            v52 = (__int64)(i - 12);
            KeStackAttachProcess(*(PRKPROCESS *)(v33 + 16), ApcState);
            LODWORD(v18) = VIDMM_GLOBAL::CommitLocalBackingStore(this, v18);
            KeUnstackDetachProcess(ApcState);
            if ( (int)v18 < 0 )
              break;
            v16 = v9 + 112;
          }
          v34 = v52;
          WdLogSingleEntry1(1, v52);
          WdLogGlobalForLineNumber = 7379;
          DxgkLogInternalTriageEvent(
            v35,
            0x40000,
            v36,
            (unsigned int)L"Failed to recommit the backing store for local alloc %p during Reclaim",
            v34,
            0,
            0,
            0);
          v37 = *((_QWORD *)v46 + 1);
          if ( v37 != v9 + 112 )
          {
            do
            {
              v38 = *(_QWORD *)(v37 - 40);
              memset(ApcState, 0, 48);
              KeStackAttachProcess(*(PRKPROCESS *)(v38 + 16), ApcState);
              VIDMM_GLOBAL::UncommitLocalBackingStore(this, (struct VIDMM_LOCAL_ALLOC *)(v37 - 48), 1);
              KeUnstackDetachProcess(ApcState);
              v37 = *(_QWORD *)(v37 + 8);
            }
            while ( v37 != v9 + 112 );
            v5 = v51;
          }
          VIDMM_GLOBAL::UncommitGlobalBackingStore(this, (struct VIDMM_GLOBAL_ALLOC *)v9, 0);
        }
      }
      LODWORD(v18) = 0;
      *((_WORD *)a3[12] + 4) = 3;
      *v5 = D3DDDI_RECLAIM_RESULT_NOT_COMMITTED;
      _InterlockedAdd(&dword_14008680C, 1u);
      WdLogSingleEntry1(6, v9);
      WdLogGlobalForLineNumber = 7429;
      DxgkLogInternalTriageEvent(
        v39,
        262145,
        v40,
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
      if ( (byte_140086201 & 1) != 0 )
        McTemplateK0puu_EtwWriteTransfer(
          v16,
          (unsigned int)EventReclaimAllocation,
          v17,
          (_DWORD)a3,
          *(_BYTE *)(v9 + 304),
          v17);
      if ( v14 )
      {
        LODWORD(v20) = v45;
      }
      else
      {
        v20 = v45;
        if ( v45 != 3 && (v45 != 2 || (*(_DWORD *)(v9 + 24) & 0x4000000) == 0) && *(_DWORD *)(v9 + 72) )
        {
          if ( g_IsInternalReleaseOrDbg )
          {
            v29 = (_QWORD *)WdLogNewEntry5_WdTrace(v16, v15);
            v29[3] = a3;
            v29[4] = 0;
            v29[5] = v20;
            v29[6] = ((unsigned __int64)*(unsigned int *)(v9 + 24) >> 26) & 1;
            v29[7] = 1;
            WdLogGlobalForLineNumber = 7637;
          }
          goto LABEL_33;
        }
      }
      if ( g_IsInternalReleaseOrDbg )
      {
        v41 = (_QWORD *)WdLogNewEntry5_WdTrace(v16, v15);
        v41[3] = a3;
        v41[4] = v14 != 0;
        v41[5] = (int)v20;
        v41[6] = ((unsigned __int64)*(unsigned int *)(v9 + 24) >> 26) & 1;
        v41[7] = 0;
        WdLogGlobalForLineNumber = 7584;
      }
      v21 = (enum _D3DDDI_RECLAIM_RESULT *)(v9 + 112);
      v22 = *(enum _D3DDDI_RECLAIM_RESULT **)(v9 + 112);
      v51 = v21;
      while ( 1 )
      {
        v46 = v22;
        if ( v22 == v21 )
          break;
        v25 = v22 - 4;
        v26 = (enum _D3DDDI_RECLAIM_RESULT *)*((_QWORD *)v22 - 2);
        if ( v26 != v22 - 4 )
        {
          v27 = v50;
          do
          {
            v28 = v26 - 10;
            if ( (*(v26 - 2) & 1) == 0 && VIDMM_ALLOC::HasAnyResidencyReferences((VIDMM_ALLOC *)(v26 - 10)) )
            {
              memset(ApcState, 0, 0x58u);
              LODWORD(ApcState[0].ApcListHead[0].Flink) = 210;
              ApcState[0].ApcListHead[1].Flink = (struct _LIST_ENTRY *)(v26 - 10);
              LODWORD(v18) = VIDMM_GLOBAL::QueueDeferredCommand(
                               this,
                               v27,
                               (struct _VIDMM_DEFERRED_COMMAND *)ApcState,
                               0,
                               &v48);
              if ( (v28[7] & 0x20) != 0 )
              {
                *((_QWORD *)v28 + 102) = v48;
                *((_QWORD *)v28 + 99) = v27;
              }
            }
            v26 = *(enum _D3DDDI_RECLAIM_RESULT **)v26;
          }
          while ( v26 != v25 );
          v22 = v46;
          v21 = v51;
        }
        v22 = *(enum _D3DDDI_RECLAIM_RESULT **)v22;
      }
LABEL_33:
      DXGFASTMUTEX::Release(v53);
      if ( (_DWORD)v18 == 259 )
      {
        if ( v54 )
        {
          *v54 = v48;
        }
        else
        {
          VIDMM_GLOBAL::WaitForFence(this, *((struct _VIDSCH_SYNC_OBJECT **)v50 + 11), v48);
          LODWORD(v18) = 0;
        }
      }
      return (unsigned int)v18;
    }
    if ( v17 == 1 )
    {
      *a5 = D3DDDI_RECLAIM_RESULT_OK;
    }
    else
    {
      if ( v17 == 3 )
        *a5 = D3DDDI_RECLAIM_RESULT_DISCARDED;
      if ( v19
        && (*(_DWORD *)(v47 + 64) & 1) == 0
        && *(_BYTE *)(v9 + 42)
        && !*(_BYTE *)(v9 + 43)
        && (*(_DWORD *)(v9 + 32) & 8) != 0 )
      {
        if ( !v14 )
          goto LABEL_25;
        v23 = *(_QWORD *)(v9 + 48);
        if ( v23 )
        {
          v15 = *(_QWORD *)(v23 + 8);
          if ( v15 )
          {
            VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
              (VIDMM_PROCESS_AUTOATTACH *)ApcState,
              (struct VIDMM_PROCESS *)v15,
              1);
            v18 = (struct VIDMM_LOCAL_ALLOC *)(*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v9 + 232) + 40LL))(
                                                *(_QWORD *)(v9 + 232),
                                                *(_QWORD *)(v9 + 240),
                                                *(_QWORD *)(*(_QWORD *)(v9 + 48) + 16LL),
                                                *(_QWORD *)(v47 + 16));
            VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)ApcState);
            if ( (int)v18 < 0 )
            {
              *(_BYTE *)(v9 + 42) = 0;
              WdLogSingleEntry1(4, v18);
              LODWORD(v18) = 0;
              WdLogGlobalForLineNumber = 7502;
            }
            else
            {
              *a5 = D3DDDI_RECLAIM_RESULT_OK;
              *(_QWORD *)(v9 + 312) = 0;
              WdLogSingleEntry1(4, v9);
              WdLogGlobalForLineNumber = 7497;
            }
            if ( (byte_140086201 & 1) != 0 )
              McTemplateK0pqqt_EtwWriteTransfer(v16, v15, v24, v9, v42, *(_QWORD *)(v47 + 16) >> 12, 1);
            *(_DWORD *)(v9 + 32) &= ~8u;
            v17 = v45;
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
  WdLogGlobalForLineNumber = 7302;
  if ( a5 )
    *a5 = D3DDDI_RECLAIM_RESULT_DISCARDED;
  DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v9 + 136));
  return DxgkVidMmAllowFailOnOfferReclaimErrors() != 0 ? 0xC000000D : 0;
}

```

## disassembly

```asm
0x1400e765c  push    rbp
0x1400e765e  push    rbx
0x1400e765f  push    rsi
0x1400e7660  push    rdi
0x1400e7661  push    r12
0x1400e7663  push    r13
0x1400e7665  push    r14
0x1400e7667  push    r15
0x1400e7669  lea     rbp, [rsp-18h]
0x1400e766e  sub     rsp, 118h
0x1400e7675  mov     rax, cs:__security_cookie
0x1400e767c  xor     rax, rsp
0x1400e767f  mov     [rbp+50h+var_50], rax
0x1400e7683  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400e768a  xor     r12d, r12d
0x1400e768d  mov     r13, [rbp+50h+arg_20]
0x1400e7694  mov     r14, r8
0x1400e7697  mov     [rbp+50h+var_B8], r9
0x1400e769b  mov     r15, rcx
0x1400e769e  mov     [rsp+150h+var_D8], rdx
0x1400e76a3  mov     [rbp+50h+var_D0], r13
0x1400e76a7  cmp     [rax], r12b
0x1400e76aa  jnz     loc_1400E784E
0x1400e76b0  mov     rax, [r14]
0x1400e76b3  mov     [rsp+150h+var_E8], r12
0x1400e76b8  mov     rdi, [rax]
0x1400e76bb  mov     ecx, [rdi+20h]
0x1400e76be  and     ecx, 40h
0x1400e76c1  jnz     loc_1400E7A59
0x1400e76c7  test    byte ptr [r15+9169h], 20h
0x1400e76cf  jz      short loc_1400E76F4
0x1400e76d1  xor     eax, eax
0x1400e76d3  mov     rcx, [rbp+50h+var_50]
0x1400e76d7  xor     rcx, rsp; StackCookie
0x1400e76da  call    __security_check_cookie
0x1400e76df  add     rsp, 118h
0x1400e76e6  pop     r15
0x1400e76e8  pop     r14
0x1400e76ea  pop     r13
0x1400e76ec  pop     r12
0x1400e76ee  pop     rdi
0x1400e76ef  pop     rsi
0x1400e76f0  pop     rbx
0x1400e76f1  pop     rbp
0x1400e76f2  retn
0x1400e76f4  mov     rax, [rdi]
0x1400e76f7  mov     esi, 1
0x1400e76fc  mov     ebx, [r15+0C48h]
0x1400e7703  mov     [rsp+150h+var_F0], rax
0x1400e7708  test    ecx, ecx
0x1400e770a  jnz     loc_1400E7AC2
0x1400e7710  mov     al, r12b
0x1400e7713  and     ebx, 8
0x1400e7716  mov     [rsp+150h+var_100], al
0x1400e771a  test    al, al
0x1400e771c  jnz     loc_1400E7AD4
0x1400e7722  test    ebx, ebx
0x1400e7724  jnz     loc_1400E7AE4
0x1400e772a  lea     rdx, [r15+8E38h]; struct DXGPUSHLOCK *
0x1400e7731  mov     [rsp+150h+var_FF], r12b
0x1400e7736  lea     rcx, [rbp+50h+ApcState]; this
0x1400e773a  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1400e773f  cmp     [rdi+110h], r12
0x1400e7746  jz      short loc_1400E7753
0x1400e7748  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400e774b  mov     rcx, r15; this
0x1400e774e  call    ?RemoveAllocationFromOfferList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::RemoveAllocationFromOfferList(VIDMM_GLOBAL_ALLOC *)
0x1400e7753  cmp     [rdi+120h], r12
0x1400e775a  jnz     loc_1400E7AF4
0x1400e7760  lea     rcx, [rbp+50h+ApcState]; this
0x1400e7764  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400e7769  lea     r12, [rdi+88h]
0x1400e7770  mov     rcx, r12; this
0x1400e7773  mov     [rbp+50h+var_C0], r12
0x1400e7777  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400e777c  mov     rax, [r14+60h]
0x1400e7780  xor     ecx, ecx
0x1400e7782  xchg    cx, [rax+8]
0x1400e7786  movsx   r8d, cx
0x1400e778a  mov     [rsp+150h+var_FC], r8d
0x1400e778f  test    r8d, r8d
0x1400e7792  jz      loc_1400E786D
0x1400e7798  mov     r9d, [rdi+20h]
0x1400e779c  xor     r12d, r12d
0x1400e779f  and     r9d, 20h
0x1400e77a3  mov     [rsp+150h+var_E0], r9d
0x1400e77a8  cmp     [rsp+150h+var_FF], r12b
0x1400e77ad  jnz     loc_1400E7B12
0x1400e77b3  test    r9d, r9d
0x1400e77b6  jz      loc_1400E7B37
0x1400e77bc  and     dword ptr [rdi+20h], 0FFFFFFBFh
0x1400e77c0  test    r13, r13
0x1400e77c3  jz      loc_1400E7DB5
0x1400e77c9  cmp     r8d, esi
0x1400e77cc  jz      loc_1400E7D43
0x1400e77d2  cmp     r8d, 3
0x1400e77d6  jz      loc_1400E7D50
0x1400e77dc  test    r9d, r9d
0x1400e77df  jnz     loc_1400E78B6
0x1400e77e5  test    ebx, ebx
0x1400e77e7  jnz     loc_1400E7DAC
0x1400e77ed  test    cs:byte_140086201, sil
0x1400e77f4  jnz     loc_1400E7A36
0x1400e77fa  test    ebx, ebx
0x1400e77fc  jz      loc_1400E79BD
0x1400e7802  mov     r13d, [rsp+150h+var_FC]
0x1400e7807  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400e780e  cmp     byte ptr [rax], 0
0x1400e7811  jnz     loc_1400E7DBE
0x1400e7817  lea     rax, [rdi+70h]
0x1400e781b  mov     rdi, [rax]
0x1400e781e  mov     [rbp+50h+var_D0], rax
0x1400e7822  mov     [rsp+150h+var_F8], rdi
0x1400e7827  cmp     rdi, rax
0x1400e782a  jnz     loc_1400E7982
0x1400e7830  mov     rcx, [rbp+50h+var_C0]; this
0x1400e7834  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400e7839  cmp     r12d, 103h
0x1400e7840  jz      loc_1400E7E71
0x1400e7846  mov     eax, r12d
0x1400e7849  jmp     loc_1400E76D3
0x1400e784e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400e7855  nop     dword ptr [rax+rax+00h]
0x1400e785a  mov     [rax+18h], r14
0x1400e785e  mov     cs:WdLogGlobalForLineNumber, 1C38h
0x1400e7868  jmp     loc_1400E76B0
0x1400e786d  mov     rdx, r14
0x1400e7870  mov     ecx, 2
0x1400e7875  call    cs:__imp_WdLogSingleEntry1
0x1400e787c  nop     dword ptr [rax+rax+00h]
0x1400e7881  mov     cs:WdLogGlobalForLineNumber, 1C86h
0x1400e788b  test    r13, r13
0x1400e788e  jnz     loc_1400E7B09
0x1400e7894  mov     rcx, r12; this
0x1400e7897  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400e789c  call    cs:__imp_?DxgkVidMmAllowFailOnOfferReclaimErrors@@YAHXZ; DxgkVidMmAllowFailOnOfferReclaimErrors(void)
0x1400e78a3  nop     dword ptr [rax+rax+00h]
0x1400e78a8  neg     eax
0x1400e78aa  sbb     eax, eax
0x1400e78ac  and     eax, 0C000000Dh
0x1400e78b1  jmp     loc_1400E76D3
0x1400e78b6  mov     rax, [rsp+150h+var_F0]
0x1400e78bb  mov     eax, [rax+40h]
0x1400e78be  test    sil, al
0x1400e78c1  jnz     loc_1400E77E5
0x1400e78c7  cmp     byte ptr [rdi+2Ah], 0
0x1400e78cb  jz      loc_1400E77E5
0x1400e78d1  cmp     byte ptr [rdi+2Bh], 0
0x1400e78d5  jnz     loc_1400E77E5
0x1400e78db  mov     eax, [rdi+20h]
0x1400e78de  test    al, 8
0x1400e78e0  jz      loc_1400E77E5
0x1400e78e6  test    ebx, ebx
0x1400e78e8  jz      loc_1400E77ED
0x1400e78ee  mov     rax, [rdi+30h]
0x1400e78f2  test    rax, rax
0x1400e78f5  jz      loc_1400E7DAC
0x1400e78fb  mov     rdx, [rax+8]; struct VIDMM_PROCESS *
0x1400e78ff  test    rdx, rdx
0x1400e7902  jz      loc_1400E7DAC
0x1400e7908  mov     r8b, sil; bool
0x1400e790b  lea     rcx, [rbp+50h+ApcState]; this
0x1400e790f  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400e7914  mov     rcx, [rdi+0E8h]
0x1400e791b  mov     rdx, [rsp+150h+var_F0]
0x1400e7920  mov     r8, [rdi+30h]
0x1400e7924  mov     rax, [rcx]
0x1400e7927  mov     r9, [rdx+10h]
0x1400e792b  mov     r8, [r8+10h]
0x1400e792f  mov     rdx, [rdi+0F0h]
0x1400e7936  mov     rax, [rax+28h]
0x1400e793a  call    _guard_dispatch_icall
0x1400e793f  lea     rcx, [rbp+50h+ApcState]; this
0x1400e7943  movsxd  r12, eax
0x1400e7946  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400e794b  xor     eax, eax
0x1400e794d  test    r12d, r12d
0x1400e7950  js      loc_1400E7D59
0x1400e7956  mov     [r13+0], eax
0x1400e795a  mov     [rdi+138h], rax
0x1400e7961  mov     rdx, rdi
0x1400e7964  lea     ecx, [rax+4]
0x1400e7967  call    cs:__imp_WdLogSingleEntry1
0x1400e796e  nop     dword ptr [rax+rax+00h]
0x1400e7973  mov     cs:WdLogGlobalForLineNumber, 1D49h
0x1400e797d  jmp     loc_1400E7D7D
0x1400e7982  lea     r13, [rdi-10h]
0x1400e7986  mov     r14, [r13+0]
0x1400e798a  cmp     r14, r13
0x1400e798d  jz      short loc_1400E79B5
0x1400e798f  mov     rdi, [rsp+150h+var_D8]
0x1400e7994  lea     rbx, [r14-28h]
0x1400e7998  mov     eax, [rbx+20h]
0x1400e799b  test    sil, al
0x1400e799e  jz      loc_1400E7E05
0x1400e79a4  mov     r14, [r14]
0x1400e79a7  cmp     r14, r13
0x1400e79aa  jnz     short loc_1400E7994
0x1400e79ac  mov     rdi, [rsp+150h+var_F8]
0x1400e79b1  mov     rax, [rbp+50h+var_D0]
0x1400e79b5  mov     rdi, [rdi]
0x1400e79b8  jmp     loc_1400E7822
0x1400e79bd  movsxd  r13, [rsp+150h+var_FC]
0x1400e79c2  cmp     r13d, 3
0x1400e79c6  jz      loc_1400E7807
0x1400e79cc  cmp     r13d, 2
0x1400e79d0  jnz     short loc_1400E79DF
0x1400e79d2  test    dword ptr [rdi+18h], 4000000h
0x1400e79d9  jnz     loc_1400E7807
0x1400e79df  cmp     dword ptr [rdi+48h], 0
0x1400e79e3  jz      loc_1400E7807
0x1400e79e9  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400e79f0  cmp     byte ptr [rax], 0
0x1400e79f3  jz      loc_1400E7830
0x1400e79f9  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400e7a00  nop     dword ptr [rax+rax+00h]
0x1400e7a05  mov     [rax+18h], r14
0x1400e7a09  mov     qword ptr [rax+20h], 0
0x1400e7a11  mov     [rax+28h], r13
0x1400e7a15  mov     ecx, [rdi+18h]
0x1400e7a18  shr     rcx, 1Ah
0x1400e7a1c  and     rcx, rsi
0x1400e7a1f  mov     [rax+30h], rcx
0x1400e7a23  mov     [rax+38h], rsi
0x1400e7a27  mov     cs:WdLogGlobalForLineNumber, 1DD5h
0x1400e7a31  jmp     loc_1400E7830
0x1400e7a36  mov     al, [rdi+130h]
0x1400e7a3c  lea     rdx, EventReclaimAllocation
0x1400e7a43  mov     byte ptr [rsp+150h+var_128], r8b
0x1400e7a48  mov     r9, r14
0x1400e7a4b  mov     byte ptr [rsp+150h+var_130], al
0x1400e7a4f  call    McTemplateK0puu_EtwWriteTransfer
0x1400e7a54  jmp     loc_1400E77FA
0x1400e7a59  test    r13, r13
0x1400e7a5c  jnz     loc_1400E76C7
0x1400e7a62  mov     rdx, r14
0x1400e7a65  lea     ecx, [r13+1]
0x1400e7a69  call    cs:__imp_WdLogSingleEntry1
0x1400e7a70  nop     dword ptr [rax+rax+00h]
0x1400e7a75  mov     [rsp+150h+var_118], r12
0x1400e7a7a  lea     r9, aAllocation0xPW; "Allocation 0x%p was marked as decommitt"...
0x1400e7a81  mov     [rsp+150h+var_120], r12
0x1400e7a86  mov     edx, 40000h
0x1400e7a8b  mov     [rsp+150h+var_128], r12
0x1400e7a90  mov     [rsp+150h+var_130], r14
0x1400e7a95  mov     cs:WdLogGlobalForLineNumber, 1C46h
0x1400e7a9f  call    DxgkLogInternalTriageEvent
0x1400e7aa4  mov     rcx, [r14+8]
0x1400e7aa8  lea     edx, [r13+14h]
0x1400e7aac  xor     r8d, r8d
0x1400e7aaf  mov     rcx, [rcx+20h]
0x1400e7ab3  call    VidSchMarkDeviceAsError
0x1400e7ab8  mov     eax, 0C000000Dh
0x1400e7abd  jmp     loc_1400E76D3
0x1400e7ac2  mov     al, sil
0x1400e7ac5  bt      ebx, 10h
0x1400e7ac9  jb      loc_1400E7713
0x1400e7acf  jmp     loc_1400E7710
0x1400e7ad4  mov     rdx, r14; struct VIDMM_ALLOC *
0x1400e7ad7  mov     rcx, r15; this
0x1400e7ada  call    ?ForceDecommitOffer@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::ForceDecommitOffer(VIDMM_ALLOC *)
0x1400e7adf  jmp     loc_1400E772A
0x1400e7ae4  mov     rdx, r14; struct VIDMM_ALLOC *
0x1400e7ae7  mov     rcx, r15; this
0x1400e7aea  call    ?ForceDiscardOffer@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::ForceDiscardOffer(VIDMM_ALLOC *)
0x1400e7aef  jmp     loc_1400E772A
0x1400e7af4  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400e7af7  mov     rcx, r15; this
0x1400e7afa  call    ?RemoveAllocationFromDecommitList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::RemoveAllocationFromDecommitList(VIDMM_GLOBAL_ALLOC *)
0x1400e7aff  mov     [rsp+150h+var_FF], sil
0x1400e7b04  jmp     loc_1400E7760
0x1400e7b09  mov     [r13+0], esi
0x1400e7b0d  jmp     loc_1400E7894
0x1400e7b12  mov     rax, [rdi+30h]
0x1400e7b16  mov     rdx, [rsp+150h+var_F0]
0x1400e7b1b  mov     rcx, [rax+8]
0x1400e7b1f  mov     rdx, [rdx+10h]
0x1400e7b23  neg     rdx
0x1400e7b26  mov     rax, [rcx+48h]
0x1400e7b2a  lock add [rax+1B8h], rdx
0x1400e7b32  jmp     loc_1400E77B3
0x1400e7b37  cmp     [rsp+150h+var_100], r12b
0x1400e7b3c  jnz     loc_1400E7CDC
0x1400e7b42  mov     rax, [rdi+30h]
0x1400e7b46  mov     rcx, [rax+8]
0x1400e7b4a  mov     eax, [rcx+98h]
0x1400e7b50  test    al, 4
0x1400e7b52  jnz     loc_1400E7CDC
0x1400e7b58  mov     r8, [rsp+150h+var_D8]
0x1400e7b5d  lea     rax, [rsp+150h+var_100]
0x1400e7b62  mov     [rsp+150h+var_100], sil
0x1400e7b67  xor     r9d, r9d; void *
0x1400e7b6a  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400e7b6d  mov     [rsp+150h+var_130], rax; unsigned __int8 *
0x1400e7b72  mov     rcx, r15; this
0x1400e7b75  mov     r8, [r8+60h]
0x1400e7b79  mov     r8, [r8+8]; struct VIDMM_PROCESS *
0x1400e7b7d  call    ?CommitGlobalBackingStore@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@PEAVVIDMM_PROCESS@@PEAXPEAE@Z; VIDMM_GLOBAL::CommitGlobalBackingStore(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS *,void *,uchar *)
0x1400e7b82  mov     r12d, eax
0x1400e7b85  test    eax, eax
  ... truncated ...
```
