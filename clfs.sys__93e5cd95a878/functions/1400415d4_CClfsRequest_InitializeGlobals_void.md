# CClfsRequest::InitializeGlobals(void)

- ea: `0x1400415d4`
- end: `0x1400419c3`
- name: `?InitializeGlobals@CClfsRequest@@SAJXZ`
- size: `1007`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004c5a0`

## callees

- `0x14000ed64`
- `0x1400415d4`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140041674`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140041674`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004160e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004160e`
- `ntoskrnl!KeInitializeEvent` at `0x140041647`
- `ntoskrnl!KeInitializeEvent` at `0x140041647`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400416c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400416f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041725`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041755`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041785`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400417b5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400417e5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041815`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041845`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041875`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400418a5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400418d5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400416c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400416f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041725`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041755`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041785`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400417b5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400417e5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041815`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041845`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041875`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400418a5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400418d5`

## pseudocode

```c
__int64 CClfsRequest::InitializeGlobals(void)
{
  __int64 v0; // rsi
  __int64 v1; // rdi
  struct _CLFS_FCB_TABLE_HEADER *v2; // rax
  _QWORD *PoolWithTag; // rax
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  unsigned int v15; // ebx
  __int64 Tag; // [rsp+28h] [rbp-50h]

  ExInitializeNPagedLookasideList(&CClfsRequest::m_laList, 0, 0, 0x200u, 0x138u, 0x47666C43u, 0);
  v0 = 0;
  v1 = 0;
  do
  {
    *(struct _CLFS_FCB_TABLE_HEADER near **)((char *)&CClfsRequest::m_rgFcbTable + v1 + 8) = 0;
    *(_DWORD *)((char *)&CClfsRequest::m_rgFcbTable + v1 + 16) = 0;
    *(_DWORD *)((char *)&CClfsRequest::m_rgFcbTable + v1) = 1;
    KeInitializeEvent((PRKEVENT)((char *)&CClfsRequest::m_rgFcbTable + v1 + 24), SynchronizationEvent, 0);
    RtlInitializeGenericTableAvl(
      (PRTL_AVL_TABLE)((char *)&CClfsRequest::m_rgFcbTable + v1 + 56),
      (PRTL_AVL_COMPARE_ROUTINE)CClfsLogFcbCommon::CompareLogFileName,
      CClfsLogFcbPhysical::AllocateFcb,
      CClfsLogFcbPhysical::FreeFcb,
      (char *)&CClfsRequest::m_rgFcbTable + v1);
    ++v0;
    v2 = (struct _CLFS_FCB_TABLE_HEADER *)((char *)&CClfsRequest::m_rgFcbTable + v1 + 160);
    *(struct _CLFS_FCB_TABLE_HEADER near **)((char *)&CClfsRequest::m_rgFcbTable + v1 + 168) = v2;
    *(struct _CLFS_FCB_TABLE_HEADER near **)((char *)&CClfsRequest::m_rgFcbTable + v1 + 160) = v2;
    v1 += 176;
  }
  while ( v0 != 5 );
  CClfsRequest::m_fInitialize = 1;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( PoolWithTag )
    *PoolWithTag = &CClfsRequest_State_Initial::`vftable';
  else
    PoolWithTag = 0;
  CClfsRequest::m_pCClfsRequest_State_Initial = PoolWithTag;
  v4 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v4 )
    *v4 = &CClfsRequest_State_Initial::`vftable';
  else
    v4 = 0;
  CClfsRequest::m_pCClfsRequest_State_Done = v4;
  v5 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v5 )
    *v5 = &CClfsRequest_State_FlushPending::`vftable';
  else
    v5 = 0;
  CClfsRequest::m_pCClfsRequest_State_FlushPending = v5;
  v6 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v6 )
    *v6 = &CClfsRequest_State_AppendPendingFlush::`vftable';
  else
    v6 = 0;
  CClfsRequest::m_pCClfsRequest_State_AppendPendingFlush = v6;
  v7 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v7 )
    *v7 = &CClfsRequest_State_ReadAwaitingCompletion::`vftable';
  else
    v7 = 0;
  CClfsRequest::m_pCClfsRequest_State_ReadAwaitingCompletion = v7;
  v8 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v8 )
    *v8 = &CClfsRequest_State_ReadPending::`vftable';
  else
    v8 = 0;
  CClfsRequest::m_pCClfsRequest_State_ReadPending = v8;
  v9 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v9 )
    *v9 = &CClfsRequest_State_ReadPendingFailed::`vftable';
  else
    v9 = 0;
  CClfsRequest::m_pCClfsRequest_State_ReadPendingFailed = v9;
  v10 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v10 )
    *v10 = &CClfsRequest_State_WriteRestartPending::`vftable';
  else
    v10 = 0;
  CClfsRequest::m_pCClfsRequest_State_WriteRestartPending = v10;
  v11 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v11 )
    *v11 = &CClfsRequest_State_WriteRestartInProgress::`vftable';
  else
    v11 = 0;
  CClfsRequest::m_pCClfsRequest_State_WriteRestartInProgress = v11;
  v12 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v12 )
    *v12 = &CClfsRequest_State_AdvanceLogBasePending::`vftable';
  else
    v12 = 0;
  CClfsRequest::m_pCClfsRequest_State_AdvanceLogBasePending = v12;
  v13 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v13 )
    *v13 = &CClfsRequest_State_AdvanceLogBaseAwaitingRestart::`vftable';
  else
    v13 = 0;
  CClfsRequest::m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart = v13;
  v14 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x50666C43u);
  if ( v14 )
    *v14 = &CClfsRequest_State_ReadMgmtNotificationPending::`vftable';
  else
    v14 = 0;
  CClfsRequest::m_pCClfsRequest_State_ReadMgmtNotificationPending = v14;
  if ( !CClfsRequest::m_pCClfsRequest_State_Initial
    || !CClfsRequest::m_pCClfsRequest_State_Done
    || !CClfsRequest::m_pCClfsRequest_State_FlushPending
    || !CClfsRequest::m_pCClfsRequest_State_AppendPendingFlush
    || !CClfsRequest::m_pCClfsRequest_State_ReadAwaitingCompletion
    || !CClfsRequest::m_pCClfsRequest_State_ReadPending
    || !CClfsRequest::m_pCClfsRequest_State_ReadPendingFailed
    || !CClfsRequest::m_pCClfsRequest_State_WriteRestartPending
    || !CClfsRequest::m_pCClfsRequest_State_WriteRestartInProgress
    || !CClfsRequest::m_pCClfsRequest_State_AdvanceLogBasePending
    || !CClfsRequest::m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart
    || (v15 = 0, !v14) )
  {
    v15 = -1073741670;
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
    {
      LODWORD(Tag) = -1073741670;
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        17,
        (unsigned int)WPP_e99822b18e20334f40b669f21686eb29_Traceguids,
        (unsigned int)"CClfsRequest::InitializeGlobals",
        122,
        Tag);
    }
  }
  return v15;
}

```

## disassembly

```asm
0x1400415d4  push    rbx
0x1400415d6  push    rbp
0x1400415d7  push    rsi
0x1400415d8  push    rdi
0x1400415d9  push    r14
0x1400415db  push    r15
0x1400415dd  sub     rsp, 48h
0x1400415e1  xor     ebp, ebp
0x1400415e3  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400415ea  mov     [rsp+78h+Depth], bp; Depth
0x1400415ef  mov     r14d, 200h
0x1400415f5  mov     dword ptr [rsp+78h+Tag], 47666C43h; Tag
0x1400415fd  mov     r9d, r14d; Flags
0x140041600  xor     r8d, r8d; Free
0x140041603  mov     [rsp+78h+Size], 138h; Size
0x14004160c  xor     edx, edx; Allocate
0x14004160e  call    cs:__imp_ExInitializeNPagedLookasideList
0x140041615  nop     dword ptr [rax+rax+00h]
0x14004161a  mov     esi, ebp
0x14004161c  lea     r15, ?m_rgFcbTable@CClfsRequest@@0PAU_CLFS_FCB_TABLE_HEADER@@A; _CLFS_FCB_TABLE_HEADER near * CClfsRequest::m_rgFcbTable
0x140041623  mov     edi, ebp
0x140041625  xor     r8d, r8d; State
0x140041628  mov     [rdi+r15+8], rbp
0x14004162d  lea     rcx, [r15+18h]
0x140041631  mov     [rdi+r15+10h], ebp
0x140041636  lea     rbx, [rdi+r15]
0x14004163a  add     rcx, rdi; Event
0x14004163d  mov     dword ptr [rbx], 1
0x140041643  lea     edx, [r8+1]; Type
0x140041647  call    cs:__imp_KeInitializeEvent
0x14004164e  nop     dword ptr [rax+rax+00h]
0x140041653  lea     rcx, [r15+38h]
0x140041657  mov     [rsp+78h+Size], rbx; TableContext
0x14004165c  add     rcx, rdi; Table
0x14004165f  lea     r9, ?FreeFcb@CClfsLogFcbPhysical@@SAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x140041666  lea     r8, ?AllocateFcb@CClfsLogFcbPhysical@@SAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x14004166d  lea     rdx, ?CompareLogFileName@CClfsLogFcbCommon@@SA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x140041674  call    cs:__imp_RtlInitializeGenericTableAvl
0x14004167b  nop     dword ptr [rax+rax+00h]
0x140041680  lea     rax, [r15+0A0h]
0x140041687  inc     rsi
0x14004168a  add     rax, rdi
0x14004168d  mov     [rdi+r15+0A8h], rax
0x140041695  mov     [rdi+r15+0A0h], rax
0x14004169d  add     rdi, 0B0h
0x1400416a4  cmp     rsi, 5
0x1400416a8  jnz     loc_140041625
0x1400416ae  mov     ebx, 50666C43h
0x1400416b3  mov     cs:?m_fInitialize@CClfsRequest@@0_NA, 1; bool CClfsRequest::m_fInitialize
0x1400416ba  lea     edi, [rsi+3]
0x1400416bd  mov     r8d, ebx; Tag
0x1400416c0  mov     edx, edi; NumberOfBytes
0x1400416c2  mov     ecx, r14d; PoolType
0x1400416c5  call    cs:__imp_ExAllocatePoolWithTag
0x1400416cc  nop     dword ptr [rax+rax+00h]
0x1400416d1  test    rax, rax
0x1400416d4  jz      short loc_1400416E2
0x1400416d6  lea     rcx, ??_7CClfsRequest_State_Initial@@6B@; const CClfsRequest_State_Initial::`vftable'
0x1400416dd  mov     [rax], rcx
0x1400416e0  jmp     short loc_1400416E5
0x1400416e2  mov     rax, rbp
0x1400416e5  mov     r8d, ebx; Tag
0x1400416e8  mov     cs:?m_pCClfsRequest_State_Initial@CClfsRequest@@0PEAVCClfsRequest_State_Initial@@EA, rax; CClfsRequest_State_Initial * CClfsRequest::m_pCClfsRequest_State_Initial
0x1400416ef  mov     rdx, rdi; NumberOfBytes
0x1400416f2  mov     ecx, r14d; PoolType
0x1400416f5  call    cs:__imp_ExAllocatePoolWithTag
0x1400416fc  nop     dword ptr [rax+rax+00h]
0x140041701  test    rax, rax
0x140041704  jz      short loc_140041712
0x140041706  lea     rcx, ??_7CClfsRequest_State_Initial@@6B@; const CClfsRequest_State_Initial::`vftable'
0x14004170d  mov     [rax], rcx
0x140041710  jmp     short loc_140041715
0x140041712  mov     rax, rbp
0x140041715  mov     r8d, ebx; Tag
0x140041718  mov     cs:?m_pCClfsRequest_State_Done@CClfsRequest@@0PEAVCClfsRequest_State_Done@@EA, rax; CClfsRequest_State_Done * CClfsRequest::m_pCClfsRequest_State_Done
0x14004171f  mov     rdx, rdi; NumberOfBytes
0x140041722  mov     ecx, r14d; PoolType
0x140041725  call    cs:__imp_ExAllocatePoolWithTag
0x14004172c  nop     dword ptr [rax+rax+00h]
0x140041731  test    rax, rax
0x140041734  jz      short loc_140041742
0x140041736  lea     rcx, ??_7CClfsRequest_State_FlushPending@@6B@; const CClfsRequest_State_FlushPending::`vftable'
0x14004173d  mov     [rax], rcx
0x140041740  jmp     short loc_140041745
0x140041742  mov     rax, rbp
0x140041745  mov     r8d, ebx; Tag
0x140041748  mov     cs:?m_pCClfsRequest_State_FlushPending@CClfsRequest@@0PEAVCClfsRequest_State_FlushPending@@EA, rax; CClfsRequest_State_FlushPending * CClfsRequest::m_pCClfsRequest_State_FlushPending
0x14004174f  mov     rdx, rdi; NumberOfBytes
0x140041752  mov     ecx, r14d; PoolType
0x140041755  call    cs:__imp_ExAllocatePoolWithTag
0x14004175c  nop     dword ptr [rax+rax+00h]
0x140041761  test    rax, rax
0x140041764  jz      short loc_140041772
0x140041766  lea     rcx, ??_7CClfsRequest_State_AppendPendingFlush@@6B@; const CClfsRequest_State_AppendPendingFlush::`vftable'
0x14004176d  mov     [rax], rcx
0x140041770  jmp     short loc_140041775
0x140041772  mov     rax, rbp
0x140041775  mov     r8d, ebx; Tag
0x140041778  mov     cs:?m_pCClfsRequest_State_AppendPendingFlush@CClfsRequest@@0PEAVCClfsRequest_State_AppendPendingFlush@@EA, rax; CClfsRequest_State_AppendPendingFlush * CClfsRequest::m_pCClfsRequest_State_AppendPendingFlush
0x14004177f  mov     rdx, rdi; NumberOfBytes
0x140041782  mov     ecx, r14d; PoolType
0x140041785  call    cs:__imp_ExAllocatePoolWithTag
0x14004178c  nop     dword ptr [rax+rax+00h]
0x140041791  test    rax, rax
0x140041794  jz      short loc_1400417A2
0x140041796  lea     rcx, ??_7CClfsRequest_State_ReadAwaitingCompletion@@6B@; const CClfsRequest_State_ReadAwaitingCompletion::`vftable'
0x14004179d  mov     [rax], rcx
0x1400417a0  jmp     short loc_1400417A5
0x1400417a2  mov     rax, rbp
0x1400417a5  mov     r8d, ebx; Tag
0x1400417a8  mov     cs:?m_pCClfsRequest_State_ReadAwaitingCompletion@CClfsRequest@@0PEAVCClfsRequest_State_ReadAwaitingCompletion@@EA, rax; CClfsRequest_State_ReadAwaitingCompletion * CClfsRequest::m_pCClfsRequest_State_ReadAwaitingCompletion
0x1400417af  mov     rdx, rdi; NumberOfBytes
0x1400417b2  mov     ecx, r14d; PoolType
0x1400417b5  call    cs:__imp_ExAllocatePoolWithTag
0x1400417bc  nop     dword ptr [rax+rax+00h]
0x1400417c1  test    rax, rax
0x1400417c4  jz      short loc_1400417D2
0x1400417c6  lea     rcx, ??_7CClfsRequest_State_ReadPending@@6B@; const CClfsRequest_State_ReadPending::`vftable'
0x1400417cd  mov     [rax], rcx
0x1400417d0  jmp     short loc_1400417D5
0x1400417d2  mov     rax, rbp
0x1400417d5  mov     r8d, ebx; Tag
0x1400417d8  mov     cs:?m_pCClfsRequest_State_ReadPending@CClfsRequest@@0PEAVCClfsRequest_State_ReadPending@@EA, rax; CClfsRequest_State_ReadPending * CClfsRequest::m_pCClfsRequest_State_ReadPending
0x1400417df  mov     rdx, rdi; NumberOfBytes
0x1400417e2  mov     ecx, r14d; PoolType
0x1400417e5  call    cs:__imp_ExAllocatePoolWithTag
0x1400417ec  nop     dword ptr [rax+rax+00h]
0x1400417f1  test    rax, rax
0x1400417f4  jz      short loc_140041802
0x1400417f6  lea     rcx, ??_7CClfsRequest_State_ReadPendingFailed@@6B@; const CClfsRequest_State_ReadPendingFailed::`vftable'
0x1400417fd  mov     [rax], rcx
0x140041800  jmp     short loc_140041805
0x140041802  mov     rax, rbp
0x140041805  mov     r8d, ebx; Tag
0x140041808  mov     cs:?m_pCClfsRequest_State_ReadPendingFailed@CClfsRequest@@0PEAVCClfsRequest_State_ReadPendingFailed@@EA, rax; CClfsRequest_State_ReadPendingFailed * CClfsRequest::m_pCClfsRequest_State_ReadPendingFailed
0x14004180f  mov     rdx, rdi; NumberOfBytes
0x140041812  mov     ecx, r14d; PoolType
0x140041815  call    cs:__imp_ExAllocatePoolWithTag
0x14004181c  nop     dword ptr [rax+rax+00h]
0x140041821  test    rax, rax
0x140041824  jz      short loc_140041832
0x140041826  lea     rcx, ??_7CClfsRequest_State_WriteRestartPending@@6B@; const CClfsRequest_State_WriteRestartPending::`vftable'
0x14004182d  mov     [rax], rcx
0x140041830  jmp     short loc_140041835
0x140041832  mov     rax, rbp
0x140041835  mov     r8d, ebx; Tag
0x140041838  mov     cs:?m_pCClfsRequest_State_WriteRestartPending@CClfsRequest@@0PEAVCClfsRequest_State_WriteRestartPending@@EA, rax; CClfsRequest_State_WriteRestartPending * CClfsRequest::m_pCClfsRequest_State_WriteRestartPending
0x14004183f  mov     rdx, rdi; NumberOfBytes
0x140041842  mov     ecx, r14d; PoolType
0x140041845  call    cs:__imp_ExAllocatePoolWithTag
0x14004184c  nop     dword ptr [rax+rax+00h]
0x140041851  test    rax, rax
0x140041854  jz      short loc_140041862
0x140041856  lea     rcx, ??_7CClfsRequest_State_WriteRestartInProgress@@6B@; const CClfsRequest_State_WriteRestartInProgress::`vftable'
0x14004185d  mov     [rax], rcx
0x140041860  jmp     short loc_140041865
0x140041862  mov     rax, rbp
0x140041865  mov     r8d, ebx; Tag
0x140041868  mov     cs:?m_pCClfsRequest_State_WriteRestartInProgress@CClfsRequest@@0PEAVCClfsRequest_State_WriteRestartInProgress@@EA, rax; CClfsRequest_State_WriteRestartInProgress * CClfsRequest::m_pCClfsRequest_State_WriteRestartInProgress
0x14004186f  mov     rdx, rdi; NumberOfBytes
0x140041872  mov     ecx, r14d; PoolType
0x140041875  call    cs:__imp_ExAllocatePoolWithTag
0x14004187c  nop     dword ptr [rax+rax+00h]
0x140041881  test    rax, rax
0x140041884  jz      short loc_140041892
0x140041886  lea     rcx, ??_7CClfsRequest_State_AdvanceLogBasePending@@6B@; const CClfsRequest_State_AdvanceLogBasePending::`vftable'
0x14004188d  mov     [rax], rcx
0x140041890  jmp     short loc_140041895
0x140041892  mov     rax, rbp
0x140041895  mov     r8d, ebx; Tag
0x140041898  mov     cs:?m_pCClfsRequest_State_AdvanceLogBasePending@CClfsRequest@@0PEAVCClfsRequest_State_AdvanceLogBasePending@@EA, rax; CClfsRequest_State_AdvanceLogBasePending * CClfsRequest::m_pCClfsRequest_State_AdvanceLogBasePending
0x14004189f  mov     rdx, rdi; NumberOfBytes
0x1400418a2  mov     ecx, r14d; PoolType
0x1400418a5  call    cs:__imp_ExAllocatePoolWithTag
0x1400418ac  nop     dword ptr [rax+rax+00h]
0x1400418b1  test    rax, rax
0x1400418b4  jz      short loc_1400418C2
0x1400418b6  lea     rcx, ??_7CClfsRequest_State_AdvanceLogBaseAwaitingRestart@@6B@; const CClfsRequest_State_AdvanceLogBaseAwaitingRestart::`vftable'
0x1400418bd  mov     [rax], rcx
0x1400418c0  jmp     short loc_1400418C5
0x1400418c2  mov     rax, rbp
0x1400418c5  mov     r8d, ebx; Tag
0x1400418c8  mov     cs:?m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart@CClfsRequest@@0PEAVCClfsRequest_State_AdvanceLogBaseAwaitingRestart@@EA, rax; CClfsRequest_State_AdvanceLogBaseAwaitingRestart * CClfsRequest::m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart
0x1400418cf  mov     rdx, rdi; NumberOfBytes
0x1400418d2  mov     ecx, r14d; PoolType
0x1400418d5  call    cs:__imp_ExAllocatePoolWithTag
0x1400418dc  nop     dword ptr [rax+rax+00h]
0x1400418e1  test    rax, rax
0x1400418e4  jz      short loc_1400418F2
0x1400418e6  lea     rcx, ??_7CClfsRequest_State_ReadMgmtNotificationPending@@6B@; const CClfsRequest_State_ReadMgmtNotificationPending::`vftable'
0x1400418ed  mov     [rax], rcx
0x1400418f0  jmp     short loc_1400418F5
0x1400418f2  mov     rax, rbp
0x1400418f5  cmp     cs:?m_pCClfsRequest_State_Initial@CClfsRequest@@0PEAVCClfsRequest_State_Initial@@EA, rbp; CClfsRequest_State_Initial * CClfsRequest::m_pCClfsRequest_State_Initial
0x1400418fc  mov     cs:?m_pCClfsRequest_State_ReadMgmtNotificationPending@CClfsRequest@@0PEAVCClfsRequest_State_ReadMgmtNotificationPending@@EA, rax; CClfsRequest_State_ReadMgmtNotificationPending * CClfsRequest::m_pCClfsRequest_State_ReadMgmtNotificationPending
0x140041903  jz      short loc_140041966
0x140041905  cmp     cs:?m_pCClfsRequest_State_Done@CClfsRequest@@0PEAVCClfsRequest_State_Done@@EA, rbp; CClfsRequest_State_Done * CClfsRequest::m_pCClfsRequest_State_Done
0x14004190c  jz      short loc_140041966
0x14004190e  cmp     cs:?m_pCClfsRequest_State_FlushPending@CClfsRequest@@0PEAVCClfsRequest_State_FlushPending@@EA, rbp; CClfsRequest_State_FlushPending * CClfsRequest::m_pCClfsRequest_State_FlushPending
0x140041915  jz      short loc_140041966
0x140041917  cmp     cs:?m_pCClfsRequest_State_AppendPendingFlush@CClfsRequest@@0PEAVCClfsRequest_State_AppendPendingFlush@@EA, rbp; CClfsRequest_State_AppendPendingFlush * CClfsRequest::m_pCClfsRequest_State_AppendPendingFlush
0x14004191e  jz      short loc_140041966
0x140041920  cmp     cs:?m_pCClfsRequest_State_ReadAwaitingCompletion@CClfsRequest@@0PEAVCClfsRequest_State_ReadAwaitingCompletion@@EA, rbp; CClfsRequest_State_ReadAwaitingCompletion * CClfsRequest::m_pCClfsRequest_State_ReadAwaitingCompletion
0x140041927  jz      short loc_140041966
0x140041929  cmp     cs:?m_pCClfsRequest_State_ReadPending@CClfsRequest@@0PEAVCClfsRequest_State_ReadPending@@EA, rbp; CClfsRequest_State_ReadPending * CClfsRequest::m_pCClfsRequest_State_ReadPending
0x140041930  jz      short loc_140041966
0x140041932  cmp     cs:?m_pCClfsRequest_State_ReadPendingFailed@CClfsRequest@@0PEAVCClfsRequest_State_ReadPendingFailed@@EA, rbp; CClfsRequest_State_ReadPendingFailed * CClfsRequest::m_pCClfsRequest_State_ReadPendingFailed
0x140041939  jz      short loc_140041966
0x14004193b  cmp     cs:?m_pCClfsRequest_State_WriteRestartPending@CClfsRequest@@0PEAVCClfsRequest_State_WriteRestartPending@@EA, rbp; CClfsRequest_State_WriteRestartPending * CClfsRequest::m_pCClfsRequest_State_WriteRestartPending
0x140041942  jz      short loc_140041966
0x140041944  cmp     cs:?m_pCClfsRequest_State_WriteRestartInProgress@CClfsRequest@@0PEAVCClfsRequest_State_WriteRestartInProgress@@EA, rbp; CClfsRequest_State_WriteRestartInProgress * CClfsRequest::m_pCClfsRequest_State_WriteRestartInProgress
0x14004194b  jz      short loc_140041966
0x14004194d  cmp     cs:?m_pCClfsRequest_State_AdvanceLogBasePending@CClfsRequest@@0PEAVCClfsRequest_State_AdvanceLogBasePending@@EA, rbp; CClfsRequest_State_AdvanceLogBasePending * CClfsRequest::m_pCClfsRequest_State_AdvanceLogBasePending
0x140041954  jz      short loc_140041966
0x140041956  cmp     cs:?m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart@CClfsRequest@@0PEAVCClfsRequest_State_AdvanceLogBaseAwaitingRestart@@EA, rbp; CClfsRequest_State_AdvanceLogBaseAwaitingRestart * CClfsRequest::m_pCClfsRequest_State_AdvanceLogBaseAwaitingRestart
0x14004195d  jz      short loc_140041966
0x14004195f  mov     ebx, ebp
0x140041961  test    rax, rax
0x140041964  jnz     short loc_1400419B3
0x140041966  mov     ebx, 0C000009Ah
0x14004196b  mov     rcx, cs:WPP_GLOBAL_Control
0x140041972  lea     rax, WPP_GLOBAL_Control
0x140041979  cmp     rcx, rax
0x14004197c  jz      short loc_1400419B3
0x14004197e  test    dword ptr [rcx+2Ch], 8000000h
0x140041985  jz      short loc_1400419B3
0x140041987  mov     rcx, [rcx+18h]
0x14004198b  lea     r9, aCclfsrequestIn; "CClfsRequest::InitializeGlobals"
0x140041992  mov     edx, 11h
0x140041997  mov     dword ptr [rsp+78h+Tag], 0C000009Ah
0x14004199f  lea     r8, WPP_e99822b18e20334f40b669f21686eb29_Traceguids
0x1400419a6  mov     dword ptr [rsp+78h+Size], 67Ah
0x1400419ae  call    WPP_SF_slD
0x1400419b3  mov     eax, ebx
0x1400419b5  add     rsp, 48h
0x1400419b9  pop     r15
0x1400419bb  pop     r14
0x1400419bd  pop     rdi
0x1400419be  pop     rsi
0x1400419bf  pop     rbp
0x1400419c0  pop     rbx
0x1400419c1  retn
```
