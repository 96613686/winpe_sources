# VIDMM_GLOBAL::~VIDMM_GLOBAL(void)

- ea: `0x1400b4524`
- end: `0x1400b4978`
- name: `??1VIDMM_GLOBAL@@QEAA@XZ`
- size: `1108`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140046ff4`

## callees

- `0x14001e5d8`
- `0x14002bf50`
- `0x14002c680`
- `0x14002e344`
- `0x14002e6c0`
- `0x14002f6a8`
- `0x140044f84`
- `0x140045e38`
- `0x140049190`
- `0x140059030`
- `0x1400ac0c8`
- `0x1400ad328`
- `0x1400aeff0`
- `0x1400b4524`
- `0x1400b4980`
- `0x1400b7590`
- `0x1400b8894`
- `0x1400bc864`
- `0x1400c4a74`
- `0x1400c6044`
- `0x1400c7ecc`
- `0x1400c9b74`
- `0x1400ca844`
- `0x14010aeb4`
- `0x14010cfa4`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x1400b48f4`
- `ntoskrnl!MmUnlockPages` at `0x1400b48f4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400b48bb`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400b48bb`
- `ntoskrnl!PcwCloseInstance` at `0x1400b47b9`
- `ntoskrnl!PcwCloseInstance` at `0x1400b4827`
- `ntoskrnl!PcwCloseInstance` at `0x1400b47b9`
- `ntoskrnl!PcwCloseInstance` at `0x1400b4827`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b490d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b492c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b4946`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b490d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b492c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b4946`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b4562`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b4562`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b454d`

## pseudocode

```c
void __fastcall VIDMM_GLOBAL::~VIDMM_GLOBAL(VIDMM_GLOBAL *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rsi
  unsigned int i; // edi
  struct _VIDSCH_NODE **v6; // rdx
  unsigned int v7; // r8d
  struct _VIDSCH_NODE **v8; // rax
  unsigned int v9; // edx
  __int64 v10; // rbp
  __int64 *v11; // rax
  unsigned int v12; // esi
  __int64 j; // r14
  __int64 v14; // rdi
  struct VIDMM_DMA_BUFFER *v15; // rcx
  VIDMM_DMA_POOL *v16; // rcx
  void *v17; // rcx
  void *v18; // rdi
  void *v19; // rdi
  struct _RTL_BALANCED_NODE *v20; // rax
  _QWORD *Children; // rdi
  unsigned int v22; // eax
  _QWORD *v23; // rsi
  _QWORD **v24; // rax
  _QWORD *v25; // rcx
  _QWORD *v26; // rax
  unsigned int k; // edi
  __int64 v28; // rcx
  struct _PCW_INSTANCE *v29; // rcx
  void *v30; // rcx
  unsigned int v31; // eax
  unsigned int m; // edi
  struct _PCW_INSTANCE *v33; // rcx
  unsigned int v34; // edi
  __int64 v35; // rsi
  void (__fastcall ***v36)(_QWORD, __int64); // rcx
  CVirtualAddressAllocator *v37; // rcx
  unsigned int n; // edi
  __int64 v39; // rcx
  void *v40; // rcx
  _BYTE v41[88]; // [rsp+20h] [rbp-58h] BYREF

  VIDMM_GLOBAL::LogTeardownTelemetry(this);
  if ( *((_QWORD *)this + 5174) )
    VIDMM_GLOBAL::RemoveFromAdapterList(this);
  *((_WORD *)this + 1600) = 257;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v3, v2) + 24) = this;
    WdLogGlobalForLineNumber = 989;
  }
  VIDMM_GLOBAL::DoDeferredUnlock(this);
  v4 = *(_QWORD *)(*((_QWORD *)this + 2) + 744LL);
  if ( *(int *)(*(_QWORD *)(v4 + 16) + 3132LL) >= 2500 )
  {
    for ( i = 0; i < *(_DWORD *)(v4 + 88); ++i )
    {
      v6 = *(struct _VIDSCH_NODE ***)(v4 + 776);
      v7 = *(_DWORD *)(v4 + 848);
      v8 = &v6[i];
      if ( i >= v7 )
        v8 = *(struct _VIDSCH_NODE ***)(v4 + 776);
      if ( (*((_DWORD *)*v8 + 3) & 2) != 0 )
      {
        if ( i < v7 )
          v6 += i;
        VidSchiDestroyNodeSchedulingLog(*v6);
      }
    }
  }
  VIDMM_GLOBAL::DestroyPagingFenceObjects(this);
  v10 = *((_QWORD *)this + 6);
  if ( v10 )
  {
    _mm_lfence();
    v11 = *(__int64 **)(v10 + 48);
    v12 = 0;
    for ( j = *v11; v12 < *(_DWORD *)(j + 3112); ++v12 )
    {
      v14 = *(_QWORD *)(*(_QWORD *)(v10 + 72) + 8LL * v12);
      if ( v14 && *(_QWORD *)(v14 + 8) )
      {
        v15 = *(struct VIDMM_DMA_BUFFER **)(v14 + 16);
        if ( v15 )
        {
          VidMmReleaseDmaBuffer(v15, 1);
          *(_QWORD *)(v14 + 16) = 0;
        }
        v16 = *(VIDMM_DMA_POOL **)(v14 + 8);
        if ( v16 )
          VIDMM_DMA_POOL::`scalar deleting destructor'(v16, v9);
        *(_QWORD *)(v14 + 8) = 0;
      }
    }
  }
  v17 = (void *)*((_QWORD *)this + 4661);
  if ( v17 )
  {
    VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(v17);
    *((_QWORD *)this + 4661) = 0;
  }
  VIDMM_PAGING_PROCESS::DestroyPagingProcess((VIDMM_GLOBAL *)((char *)this + 36672));
  if ( *((_BYTE *)this + 37228) )
    VIDMM_PROCESS::CloseAdapter(g_pVidMmSystemProcess, this);
  v18 = *(void **)this;
  *((_QWORD *)this + 5126) = 0;
  if ( v18 )
  {
    VidMmTerminateWorkerThread(v18);
    operator delete(v18);
    *(_QWORD *)this = 0;
  }
  v19 = (void *)*((_QWORD *)this + 6);
  if ( v19 )
  {
    VIDMM_PAGING::~VIDMM_PAGING(*((VIDMM_PAGING **)this + 6));
    operator delete(v19);
    *((_QWORD *)this + 6) = 0;
  }
  if ( g_Feature_ResourcePoolManagement )
  {
    VidMmCloseAdapterOnAllResourcePools(this);
  }
  else
  {
    DXGAUTOEXPUSHLOCKSHARED::DXGAUTOEXPUSHLOCKSHARED(
      (DXGAUTOEXPUSHLOCKSHARED *)v41,
      (struct _EX_PUSH_LOCK *const)&VIDMM_PARTITION::_PartitionLock);
    v20 = VIDMM_PARTITION::_PartitionTree;
    Children = 0;
    while ( v20 )
    {
      Children = v20->Children;
      v20 = v20->Children[0];
    }
    while ( Children )
    {
      v22 = VIDMM_GLOBAL::AdapterId(this);
      v23 = (_QWORD *)(Children[5] + 384LL * v22);
      if ( v23[1] )
      {
        VidMmiClosePerfCounters((struct VIDMM_PARTITION_ADAPTER_INFO *)(Children[5] + 384LL * v22));
        NonPagedPoolZeroedArray<VIDMM_SEGMENT_GROUP_STATE,1,1647405398>::Clear(v23 + 3);
        v23[1] = 0;
        *v23 = 0;
      }
      v24 = (_QWORD **)Children[1];
      if ( v24 )
      {
        v25 = *v24;
        if ( *v24 )
        {
          do
          {
            Children = v25;
            v25 = (_QWORD *)*v25;
          }
          while ( v25 );
        }
        else
        {
          Children = (_QWORD *)Children[1];
        }
      }
      else
      {
        do
        {
          v26 = Children;
          Children = (_QWORD *)(Children[2] & 0xFFFFFFFFFFFFFFFCuLL);
        }
        while ( Children && (_QWORD *)*Children != v26 );
      }
    }
    DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v41);
  }
  for ( k = 0; k < *((_DWORD *)this + 778); ++k )
  {
    v28 = *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * k);
    if ( (*(_BYTE *)(v28 + 1424) & 1) == 0 )
    {
      v29 = *(struct _PCW_INSTANCE **)(v28 + 1792);
      if ( v29 )
        PcwCloseInstance(v29);
    }
  }
  v30 = (void *)*((_QWORD *)this + 499);
  if ( v30 )
  {
    operator delete(v30);
    *((_QWORD *)this + 498) = 0;
    *((_QWORD *)this + 500) = 0;
    *((_QWORD *)this + 499) = 0;
  }
  operator delete(*((void **)this + 4670));
  v31 = *((_DWORD *)this + 778);
  for ( m = 0; m < v31; ++m )
  {
    v33 = *(struct _PCW_INSTANCE **)(*(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * m) + 2536LL);
    if ( v33 )
      PcwCloseInstance(v33);
    v31 = *((_DWORD *)this + 778);
  }
  if ( *((_QWORD *)this + 4560) )
  {
    v34 = 0;
    if ( v31 )
    {
      do
      {
        v35 = v34;
        v36 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 4560) + 8LL * v34);
        if ( v36 )
          (**v36)(v36, 1);
        ++v34;
        *(_QWORD *)(*((_QWORD *)this + 4560) + 8 * v35) = 0;
      }
      while ( v34 < *((_DWORD *)this + 778) );
    }
    operator delete(*((void **)this + 4560));
    *((_QWORD *)this + 4560) = 0;
  }
  v37 = (CVirtualAddressAllocator *)*((_QWORD *)this + 5134);
  if ( v37 )
    CVirtualAddressAllocator::DestroyVaAllocator(v37, 0);
  VIDMM_GLOBAL::FreeForwardProgressMdl(this);
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)this + 36544));
  if ( *((_QWORD *)this + 5104) )
  {
    for ( n = 0; n < *((_DWORD *)this + 10204); ++n )
    {
      v39 = *(_QWORD *)(*((_QWORD *)this + 5104) + 8LL * n);
      if ( v39 )
      {
        if ( (*(_BYTE *)(v39 + 10) & 2) != 0 )
          MmUnlockPages((PMDL)v39);
        ExFreePoolWithTag(*(PVOID *)(*((_QWORD *)this + 5104) + 8LL * n), 0);
      }
    }
    ExFreePoolWithTag(*((PVOID *)this + 5104), 0);
  }
  v40 = (void *)*((_QWORD *)this + 5097);
  if ( v40 )
    ExFreePoolWithTag(v40, 0);
  VIDMM_LOCKED_PAGE_HISTORY::~VIDMM_LOCKED_PAGE_HISTORY((VIDMM_GLOBAL *)((char *)this + 41408));
  DXGK_LOG::~DXGK_LOG((VIDMM_GLOBAL *)((char *)this + 37328));
}

```

## disassembly

```asm
0x1400b4524  push    rbx
0x1400b4526  push    rbp
0x1400b4527  push    rsi
0x1400b4528  push    rdi
0x1400b4529  push    r14
0x1400b452b  push    r15
0x1400b452d  sub     rsp, 48h
0x1400b4531  mov     rbx, rcx
0x1400b4534  call    ?LogTeardownTelemetry@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::LogTeardownTelemetry(void)
0x1400b4539  xor     r15d, r15d
0x1400b453c  cmp     [rbx+0A1B0h], r15
0x1400b4543  jz      short loc_1400B454D
0x1400b4545  mov     rcx, rbx; this
0x1400b4548  call    ?RemoveFromAdapterList@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::RemoveFromAdapterList(void)
0x1400b454d  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b4554  mov     word ptr [rbx+0C80h], 101h
0x1400b455d  cmp     [rax], r15b
0x1400b4560  jz      short loc_1400B457C
0x1400b4562  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b4569  nop     dword ptr [rax+rax+00h]
0x1400b456e  mov     [rax+18h], rbx
0x1400b4572  mov     cs:WdLogGlobalForLineNumber, 3DDh
0x1400b457c  mov     rcx, rbx; this
0x1400b457f  call    ?DoDeferredUnlock@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::DoDeferredUnlock(void)
0x1400b4584  mov     rax, [rbx+10h]
0x1400b4588  mov     rsi, [rax+2E8h]
0x1400b458f  mov     rax, [rsi+10h]
0x1400b4593  cmp     dword ptr [rax+0C3Ch], 9C4h
0x1400b459d  jl      short loc_1400B45E8
0x1400b459f  mov     edi, r15d
0x1400b45a2  cmp     [rsi+58h], r15d
0x1400b45a6  jbe     short loc_1400B45E8
0x1400b45a8  mov     rdx, [rsi+308h]
0x1400b45af  mov     r8d, [rsi+350h]
0x1400b45b6  mov     r9d, edi
0x1400b45b9  lea     rax, [rdx+r9*8]
0x1400b45bd  cmp     edi, r8d
0x1400b45c0  jb      short loc_1400B45C5
0x1400b45c2  mov     rax, rdx
0x1400b45c5  mov     rax, [rax]
0x1400b45c8  mov     ecx, [rax+0Ch]
0x1400b45cb  test    cl, 2
0x1400b45ce  jz      short loc_1400B45E1
0x1400b45d0  cmp     edi, r8d
0x1400b45d3  jnb     short loc_1400B45D9
0x1400b45d5  lea     rdx, [rdx+r9*8]
0x1400b45d9  mov     rcx, [rdx]; struct _VIDSCH_NODE *
0x1400b45dc  call    ?VidSchiDestroyNodeSchedulingLog@@YAXPEAU_VIDSCH_NODE@@@Z; VidSchiDestroyNodeSchedulingLog(_VIDSCH_NODE *)
0x1400b45e1  inc     edi
0x1400b45e3  cmp     edi, [rsi+58h]
0x1400b45e6  jb      short loc_1400B45A8
0x1400b45e8  mov     rcx, rbx; this
0x1400b45eb  call    ?DestroyPagingFenceObjects@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::DestroyPagingFenceObjects(void)
0x1400b45f0  mov     rbp, [rbx+30h]
0x1400b45f4  test    rbp, rbp
0x1400b45f7  jz      short loc_1400B4655
0x1400b45f9  lfence
0x1400b45fc  mov     rax, [rbp+30h]
0x1400b4600  mov     esi, r15d
0x1400b4603  mov     r14, [rax]
0x1400b4606  cmp     [r14+0C28h], r15d
0x1400b460d  jbe     short loc_1400B4655
0x1400b460f  mov     rax, [rbp+48h]
0x1400b4613  mov     ecx, esi
0x1400b4615  mov     rdi, [rax+rcx*8]
0x1400b4619  test    rdi, rdi
0x1400b461c  jz      short loc_1400B464A
0x1400b461e  cmp     [rdi+8], r15
0x1400b4622  jz      short loc_1400B464A
0x1400b4624  mov     rcx, [rdi+10h]; struct VIDMM_DMA_BUFFER *
0x1400b4628  test    rcx, rcx
0x1400b462b  jz      short loc_1400B4638
0x1400b462d  mov     dl, 1; bool
0x1400b462f  call    ?VidMmReleaseDmaBuffer@@YAXPEAUVIDMM_DMA_BUFFER@@_N@Z; VidMmReleaseDmaBuffer(VIDMM_DMA_BUFFER *,bool)
0x1400b4634  mov     [rdi+10h], r15
0x1400b4638  mov     rcx, [rdi+8]; this
0x1400b463c  test    rcx, rcx
0x1400b463f  jz      short loc_1400B4646
0x1400b4641  call    ??_GVIDMM_DMA_POOL@@QEAAPEAXI@Z; VIDMM_DMA_POOL::`scalar deleting destructor'(uint)
0x1400b4646  mov     [rdi+8], r15
0x1400b464a  inc     esi
0x1400b464c  cmp     esi, [r14+0C28h]
0x1400b4653  jb      short loc_1400B460F
0x1400b4655  mov     rcx, [rbx+91A8h]; Entry
0x1400b465c  test    rcx, rcx
0x1400b465f  jz      short loc_1400B466D
0x1400b4661  call    ?ReleaseVaRangeReference@VIDMM_MAPPED_VA_RANGE@@QEAAJXZ; VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(void)
0x1400b4666  mov     [rbx+91A8h], r15
0x1400b466d  lea     rcx, [rbx+8F40h]; this
0x1400b4674  call    ?DestroyPagingProcess@VIDMM_PAGING_PROCESS@@QEAAXXZ; VIDMM_PAGING_PROCESS::DestroyPagingProcess(void)
0x1400b4679  cmp     [rbx+916Ch], r15b
0x1400b4680  jz      short loc_1400B4691
0x1400b4682  mov     rcx, cs:?g_pVidMmSystemProcess@@3PEAVVIDMM_PROCESS@@EA; this
0x1400b4689  mov     rdx, rbx; struct VIDMM_GLOBAL *
0x1400b468c  call    ?CloseAdapter@VIDMM_PROCESS@@QEAAXPEAVVIDMM_GLOBAL@@@Z; VIDMM_PROCESS::CloseAdapter(VIDMM_GLOBAL *)
0x1400b4691  mov     rdi, [rbx]
0x1400b4694  mov     [rbx+0A030h], r15
0x1400b469b  test    rdi, rdi
0x1400b469e  jz      short loc_1400B46B3
0x1400b46a0  mov     rcx, rdi
0x1400b46a3  call    VidMmTerminateWorkerThread
0x1400b46a8  mov     rcx, rdi; void *
0x1400b46ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b46b0  mov     [rbx], r15
0x1400b46b3  mov     rdi, [rbx+30h]
0x1400b46b7  test    rdi, rdi
0x1400b46ba  jz      short loc_1400B46D0
0x1400b46bc  mov     rcx, rdi; this
0x1400b46bf  call    ??1VIDMM_PAGING@@QEAA@XZ; VIDMM_PAGING::~VIDMM_PAGING(void)
0x1400b46c4  mov     rcx, rdi; void *
0x1400b46c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b46cc  mov     [rbx+30h], r15
0x1400b46d0  cmp     cs:?g_Feature_ResourcePoolManagement@@3_NA, r15b; bool g_Feature_ResourcePoolManagement
0x1400b46d7  jz      short loc_1400B46E6
0x1400b46d9  mov     rcx, rbx; struct VIDMM_GLOBAL *
0x1400b46dc  call    ?VidMmCloseAdapterOnAllResourcePools@@YAXPEAVVIDMM_GLOBAL@@@Z; VidMmCloseAdapterOnAllResourcePools(VIDMM_GLOBAL *)
0x1400b46e1  jmp     loc_1400B478B
0x1400b46e6  lea     rdx, ?_PartitionLock@VIDMM_PARTITION@@2U_EX_PUSH_LOCK@@A; struct _EX_PUSH_LOCK *
0x1400b46ed  lea     rcx, [rsp+78h+var_58]; this
0x1400b46f2  call    ??0DXGAUTOEXPUSHLOCKSHARED@@QEAA@QEAU_EX_PUSH_LOCK@@@Z; DXGAUTOEXPUSHLOCKSHARED::DXGAUTOEXPUSHLOCKSHARED(_EX_PUSH_LOCK * const)
0x1400b46f7  mov     rax, cs:?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x1400b46fe  mov     rdi, r15
0x1400b4701  jmp     short loc_1400B4709
0x1400b4703  mov     rdi, rax
0x1400b4706  mov     rax, [rax]
0x1400b4709  test    rax, rax
0x1400b470c  jnz     short loc_1400B4703
0x1400b470e  jmp     short loc_1400B477C
0x1400b4710  mov     rcx, rbx; this
0x1400b4713  call    ?AdapterId@VIDMM_GLOBAL@@QEBAKXZ; VIDMM_GLOBAL::AdapterId(void)
0x1400b4718  mov     ecx, eax
0x1400b471a  lea     rsi, [rcx+rcx*2]
0x1400b471e  shl     rsi, 7
0x1400b4722  add     rsi, [rdi+28h]
0x1400b4726  cmp     [rsi+8], r15
0x1400b472a  jz      short loc_1400B4744
0x1400b472c  mov     rcx, rsi; struct VIDMM_PARTITION_ADAPTER_INFO *
0x1400b472f  call    ?VidMmiClosePerfCounters@@YAXPEAUVIDMM_PARTITION_ADAPTER_INFO@@@Z; VidMmiClosePerfCounters(VIDMM_PARTITION_ADAPTER_INFO *)
0x1400b4734  lea     rcx, [rsi+18h]
0x1400b4738  call    ?Clear@?$NonPagedPoolZeroedArray@UVIDMM_SEGMENT_GROUP_STATE@@$00$0GCDBGJFG@@@QEAAXXZ; NonPagedPoolZeroedArray<VIDMM_SEGMENT_GROUP_STATE,1,1647405398>::Clear(void)
0x1400b473d  mov     [rsi+8], r15
0x1400b4741  mov     [rsi], r15
0x1400b4744  mov     rax, [rdi+8]
0x1400b4748  test    rax, rax
0x1400b474b  jz      short loc_1400B476F
0x1400b474d  mov     rcx, [rax]
0x1400b4750  test    rcx, rcx
0x1400b4753  jz      short loc_1400B4765
0x1400b4755  mov     rax, [rcx]
0x1400b4758  mov     rdi, rcx
0x1400b475b  mov     rcx, rax
0x1400b475e  test    rax, rax
0x1400b4761  jnz     short loc_1400B4755
0x1400b4763  jmp     short loc_1400B477C
0x1400b4765  mov     rdi, rax
0x1400b4768  jmp     short loc_1400B477C
0x1400b476a  cmp     [rdi], rax
0x1400b476d  jz      short loc_1400B477C
0x1400b476f  mov     rax, rdi
0x1400b4772  mov     rdi, [rdi+10h]
0x1400b4776  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1400b477a  jnz     short loc_1400B476A
0x1400b477c  test    rdi, rdi
0x1400b477f  jnz     short loc_1400B4710
0x1400b4781  lea     rcx, [rsp+78h+var_58]; this
0x1400b4786  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x1400b478b  mov     edi, r15d
0x1400b478e  cmp     [rbx+0C28h], r15d
0x1400b4795  jbe     short loc_1400B47CF
0x1400b4797  mov     rax, [rbx+8E80h]
0x1400b479e  mov     ecx, edi
0x1400b47a0  mov     rcx, [rax+rcx*8]
0x1400b47a4  test    byte ptr [rcx+590h], 1
0x1400b47ab  jnz     short loc_1400B47C5
0x1400b47ad  mov     rcx, [rcx+700h]; Instance
0x1400b47b4  test    rcx, rcx
0x1400b47b7  jz      short loc_1400B47C5
0x1400b47b9  call    cs:__imp_PcwCloseInstance
0x1400b47c0  nop     dword ptr [rax+rax+00h]
0x1400b47c5  inc     edi
0x1400b47c7  cmp     edi, [rbx+0C28h]
0x1400b47cd  jb      short loc_1400B4797
0x1400b47cf  mov     rcx, [rbx+0F98h]; void *
0x1400b47d6  test    rcx, rcx
0x1400b47d9  jz      short loc_1400B47F5
0x1400b47db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b47e0  mov     [rbx+0F90h], r15
0x1400b47e7  mov     [rbx+0FA0h], r15
0x1400b47ee  mov     [rbx+0F98h], r15
0x1400b47f5  mov     rcx, [rbx+91F0h]; void *
0x1400b47fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b4801  mov     eax, [rbx+0C28h]
0x1400b4807  mov     edi, r15d
0x1400b480a  test    eax, eax
0x1400b480c  jz      short loc_1400B483F
0x1400b480e  mov     rax, [rbx+8E80h]
0x1400b4815  mov     ecx, edi
0x1400b4817  mov     rcx, [rax+rcx*8]
0x1400b481b  mov     rcx, [rcx+9E8h]; Instance
0x1400b4822  test    rcx, rcx
0x1400b4825  jz      short loc_1400B4833
0x1400b4827  call    cs:__imp_PcwCloseInstance
0x1400b482e  nop     dword ptr [rax+rax+00h]
0x1400b4833  mov     eax, [rbx+0C28h]
0x1400b4839  inc     edi
0x1400b483b  cmp     edi, eax
0x1400b483d  jb      short loc_1400B480E
0x1400b483f  cmp     [rbx+8E80h], r15
0x1400b4846  jz      short loc_1400B4899
0x1400b4848  mov     edi, r15d
0x1400b484b  test    eax, eax
0x1400b484d  jz      short loc_1400B4886
0x1400b484f  mov     rax, [rbx+8E80h]
0x1400b4856  mov     esi, edi
0x1400b4858  mov     rcx, [rax+rsi*8]
0x1400b485c  test    rcx, rcx
0x1400b485f  jz      short loc_1400B4871
0x1400b4861  mov     rax, [rcx]
0x1400b4864  mov     edx, 1
0x1400b4869  mov     rax, [rax]
0x1400b486c  call    _guard_dispatch_icall
0x1400b4871  mov     rax, [rbx+8E80h]
0x1400b4878  inc     edi
0x1400b487a  mov     [rax+rsi*8], r15
0x1400b487e  cmp     edi, [rbx+0C28h]
0x1400b4884  jb      short loc_1400B484F
0x1400b4886  mov     rcx, [rbx+8E80h]; void *
0x1400b488d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b4892  mov     [rbx+8E80h], r15
0x1400b4899  mov     rcx, [rbx+0A070h]; this
0x1400b48a0  test    rcx, rcx
0x1400b48a3  jz      short loc_1400B48AC
0x1400b48a5  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400b48a7  call    ?DestroyVaAllocator@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; CVirtualAddressAllocator::DestroyVaAllocator(VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400b48ac  mov     rcx, rbx; this
0x1400b48af  call    ?FreeForwardProgressMdl@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::FreeForwardProgressMdl(void)
0x1400b48b4  lea     rcx, [rbx+8EC0h]; Lookaside
0x1400b48bb  call    cs:__imp_ExDeletePagedLookasideList
0x1400b48c2  nop     dword ptr [rax+rax+00h]
0x1400b48c7  cmp     [rbx+9F80h], r15
0x1400b48ce  jz      short loc_1400B4938
0x1400b48d0  mov     edi, r15d
0x1400b48d3  cmp     [rbx+9F70h], r15d
0x1400b48da  jbe     short loc_1400B4923
0x1400b48dc  mov     rax, [rbx+9F80h]
0x1400b48e3  mov     esi, edi
0x1400b48e5  mov     rcx, [rax+rsi*8]; MemoryDescriptorList
0x1400b48e9  test    rcx, rcx
0x1400b48ec  jz      short loc_1400B4919
0x1400b48ee  test    byte ptr [rcx+0Ah], 2
0x1400b48f2  jz      short loc_1400B4900
0x1400b48f4  call    cs:__imp_MmUnlockPages
0x1400b48fb  nop     dword ptr [rax+rax+00h]
0x1400b4900  mov     rcx, [rbx+9F80h]
0x1400b4907  xor     edx, edx; Tag
0x1400b4909  mov     rcx, [rcx+rsi*8]; P
0x1400b490d  call    cs:__imp_ExFreePoolWithTag
0x1400b4914  nop     dword ptr [rax+rax+00h]
0x1400b4919  inc     edi
0x1400b491b  cmp     edi, [rbx+9F70h]
0x1400b4921  jb      short loc_1400B48DC
0x1400b4923  mov     rcx, [rbx+9F80h]; P
0x1400b492a  xor     edx, edx; Tag
0x1400b492c  call    cs:__imp_ExFreePoolWithTag
0x1400b4933  nop     dword ptr [rax+rax+00h]
0x1400b4938  mov     rcx, [rbx+9F48h]; P
0x1400b493f  test    rcx, rcx
0x1400b4942  jz      short loc_1400B4952
0x1400b4944  xor     edx, edx; Tag
0x1400b4946  call    cs:__imp_ExFreePoolWithTag
0x1400b494d  nop     dword ptr [rax+rax+00h]
0x1400b4952  lea     rcx, [rbx+0A1C0h]; this
0x1400b4959  call    ??1VIDMM_LOCKED_PAGE_HISTORY@@QEAA@XZ; VIDMM_LOCKED_PAGE_HISTORY::~VIDMM_LOCKED_PAGE_HISTORY(void)
0x1400b495e  lea     rcx, [rbx+91D0h]; this
0x1400b4965  call    ??1DXGK_LOG@@QEAA@XZ; DXGK_LOG::~DXGK_LOG(void)
0x1400b496a  add     rsp, 48h
0x1400b496e  pop     r15
0x1400b4970  pop     r14
0x1400b4972  pop     rdi
0x1400b4973  pop     rsi
0x1400b4974  pop     rbp
0x1400b4975  pop     rbx
0x1400b4976  retn
```
