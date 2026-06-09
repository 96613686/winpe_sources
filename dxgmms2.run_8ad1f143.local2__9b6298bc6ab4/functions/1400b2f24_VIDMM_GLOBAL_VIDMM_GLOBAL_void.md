# VIDMM_GLOBAL::~VIDMM_GLOBAL(void)

- ea: `0x1400b2f24`
- end: `0x1400b335c`
- name: `??1VIDMM_GLOBAL@@QEAA@XZ`
- size: `1080`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140046ce4`

## callees

- `0x140020138`
- `0x14002ee90`
- `0x14002f5c0`
- `0x140030604`
- `0x140030ae0`
- `0x14003180c`
- `0x140044d80`
- `0x140045c38`
- `0x140048b54`
- `0x140058760`
- `0x1400ab080`
- `0x1400abf78`
- `0x1400adaa0`
- `0x1400b2f24`
- `0x1400b3364`
- `0x1400b3c54`
- `0x1400b4eec`
- `0x1400b8e7c`
- `0x1400c0984`
- `0x1400c1e98`
- `0x1400c3d20`
- `0x1400c4e8c`
- `0x140103068`
- `0x140108c64`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x1400b32d8`
- `ntoskrnl!MmUnlockPages` at `0x1400b32d8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400b329f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400b329f`
- `ntoskrnl!PcwCloseInstance` at `0x1400b319d`
- `ntoskrnl!PcwCloseInstance` at `0x1400b320b`
- `ntoskrnl!PcwCloseInstance` at `0x1400b319d`
- `ntoskrnl!PcwCloseInstance` at `0x1400b320b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b32f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3310`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b332a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b32f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3310`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b332a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b2f62`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b2f62`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b2f4d`

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
  __int64 v10; // r14
  unsigned int v11; // esi
  __int64 v12; // rbp
  __int64 v13; // rdi
  struct VIDMM_DMA_BUFFER *v14; // rcx
  VIDMM_DMA_POOL *v15; // rcx
  void *v16; // rcx
  void *v17; // rdi
  void *v18; // rdi
  struct _RTL_BALANCED_NODE *v19; // rax
  _QWORD *Children; // rdi
  unsigned int v21; // eax
  _QWORD *v22; // rsi
  _QWORD **v23; // rax
  _QWORD *v24; // rcx
  _QWORD *v25; // rax
  unsigned int j; // edi
  __int64 v27; // rcx
  struct _PCW_INSTANCE *v28; // rcx
  void *v29; // rcx
  unsigned int v30; // eax
  unsigned int k; // edi
  struct _PCW_INSTANCE *v32; // rcx
  unsigned int v33; // edi
  __int64 v34; // rsi
  void (__fastcall ***v35)(_QWORD, __int64); // rcx
  CVirtualAddressAllocator *v36; // rcx
  unsigned int m; // edi
  __int64 v38; // rcx
  void *v39; // rcx
  _BYTE v40[88]; // [rsp+20h] [rbp-58h] BYREF

  VIDMM_GLOBAL::LogTeardownTelemetry(this);
  if ( *((_QWORD *)this + 5174) )
    VIDMM_GLOBAL::RemoveFromAdapterList(this);
  *((_WORD *)this + 1600) = 257;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v3, v2) + 24) = this;
    WdLogGlobalForLineNumber = 945;
  }
  VIDMM_GLOBAL::DoDeferredUnlock(this);
  v4 = *(_QWORD *)(*((_QWORD *)this + 2) + 744LL);
  if ( *(int *)(*(_QWORD *)(v4 + 16) + 3116LL) >= 2500 )
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
  _mm_lfence();
  v11 = 0;
  v12 = **(_QWORD **)(v10 + 48);
  if ( *(_DWORD *)(v12 + 3112) )
  {
    do
    {
      v13 = *(_QWORD *)(*(_QWORD *)(v10 + 72) + 8LL * v11);
      if ( v13 && *(_QWORD *)(v13 + 8) )
      {
        v14 = *(struct VIDMM_DMA_BUFFER **)(v13 + 16);
        if ( v14 )
        {
          VidMmReleaseDmaBuffer(v14, 1);
          *(_QWORD *)(v13 + 16) = 0;
        }
        v15 = *(VIDMM_DMA_POOL **)(v13 + 8);
        if ( v15 )
          VIDMM_DMA_POOL::`scalar deleting destructor'(v15, v9);
        *(_QWORD *)(v13 + 8) = 0;
      }
      ++v11;
    }
    while ( v11 < *(_DWORD *)(v12 + 3112) );
  }
  v16 = (void *)*((_QWORD *)this + 4661);
  if ( v16 )
  {
    VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(v16);
    *((_QWORD *)this + 4661) = 0;
  }
  VIDMM_PAGING_PROCESS::DestroyPagingProcess((VIDMM_GLOBAL *)((char *)this + 36672));
  if ( *((_BYTE *)this + 37228) )
    VIDMM_PROCESS::CloseAdapter(g_pVidMmSystemProcess, this);
  v17 = *(void **)this;
  *((_QWORD *)this + 5126) = 0;
  if ( v17 )
  {
    VidMmTerminateWorkerThread(v17);
    operator delete(v17);
    *(_QWORD *)this = 0;
  }
  v18 = (void *)*((_QWORD *)this + 6);
  if ( v18 )
  {
    VIDMM_PAGING::~VIDMM_PAGING(*((VIDMM_PAGING **)this + 6));
    operator delete(v18);
    *((_QWORD *)this + 6) = 0;
  }
  DXGAUTOEXPUSHLOCKSHARED::DXGAUTOEXPUSHLOCKSHARED(
    (DXGAUTOEXPUSHLOCKSHARED *)v40,
    (struct _EX_PUSH_LOCK *const)&VIDMM_PARTITION::_PartitionLock);
  v19 = VIDMM_PARTITION::_PartitionTree;
  Children = 0;
  while ( v19 )
  {
    Children = v19->Children;
    v19 = v19->Children[0];
  }
  while ( Children )
  {
    v21 = VIDMM_GLOBAL::AdapterId(this);
    v22 = (_QWORD *)(Children[5] + 384LL * v21);
    if ( v22[1] )
    {
      VidMmiClosePerfCounters((struct VIDMM_PARTITION_ADAPTER_INFO *)(Children[5] + 384LL * v21));
      NonPagedPoolZeroedArray<VIDMM_SEGMENT_GROUP_STATE,1,1647405398>::Clear(v22 + 3);
      v22[1] = 0;
      *v22 = 0;
    }
    v23 = (_QWORD **)Children[1];
    if ( v23 )
    {
      v24 = *v23;
      if ( *v23 )
      {
        do
        {
          Children = v24;
          v24 = (_QWORD *)*v24;
        }
        while ( v24 );
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
        v25 = Children;
        Children = (_QWORD *)(Children[2] & 0xFFFFFFFFFFFFFFFCuLL);
      }
      while ( Children && (_QWORD *)*Children != v25 );
    }
  }
  DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v40);
  for ( j = 0; j < *((_DWORD *)this + 778); ++j )
  {
    v27 = *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * j);
    if ( (*(_BYTE *)(v27 + 1160) & 1) == 0 )
    {
      v28 = *(struct _PCW_INSTANCE **)(v27 + 1528);
      if ( v28 )
        PcwCloseInstance(v28);
    }
  }
  v29 = (void *)*((_QWORD *)this + 499);
  if ( v29 )
  {
    operator delete(v29);
    *((_QWORD *)this + 498) = 0;
    *((_QWORD *)this + 500) = 0;
    *((_QWORD *)this + 499) = 0;
  }
  operator delete(*((void **)this + 4670));
  v30 = *((_DWORD *)this + 778);
  for ( k = 0; k < v30; ++k )
  {
    v32 = *(struct _PCW_INSTANCE **)(*(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * k) + 2272LL);
    if ( v32 )
      PcwCloseInstance(v32);
    v30 = *((_DWORD *)this + 778);
  }
  if ( *((_QWORD *)this + 4560) )
  {
    v33 = 0;
    if ( v30 )
    {
      do
      {
        v34 = v33;
        v35 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 4560) + 8LL * v33);
        if ( v35 )
          (**v35)(v35, 1);
        ++v33;
        *(_QWORD *)(*((_QWORD *)this + 4560) + 8 * v34) = 0;
      }
      while ( v33 < *((_DWORD *)this + 778) );
    }
    operator delete(*((void **)this + 4560));
    *((_QWORD *)this + 4560) = 0;
  }
  v36 = (CVirtualAddressAllocator *)*((_QWORD *)this + 5134);
  if ( v36 )
    CVirtualAddressAllocator::DestroyVaAllocator(v36, 0);
  VIDMM_GLOBAL::FreeForwardProgressMdl(this);
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)this + 36544));
  if ( *((_QWORD *)this + 5104) )
  {
    for ( m = 0; m < *((_DWORD *)this + 10204); ++m )
    {
      v38 = *(_QWORD *)(*((_QWORD *)this + 5104) + 8LL * m);
      if ( v38 )
      {
        if ( (*(_BYTE *)(v38 + 10) & 2) != 0 )
          MmUnlockPages((PMDL)v38);
        ExFreePoolWithTag(*(PVOID *)(*((_QWORD *)this + 5104) + 8LL * m), 0);
      }
    }
    ExFreePoolWithTag(*((PVOID *)this + 5104), 0);
  }
  v39 = (void *)*((_QWORD *)this + 5097);
  if ( v39 )
    ExFreePoolWithTag(v39, 0);
  VIDMM_LOCKED_PAGE_HISTORY::~VIDMM_LOCKED_PAGE_HISTORY((VIDMM_GLOBAL *)((char *)this + 41408));
  DXGK_LOG::~DXGK_LOG((VIDMM_GLOBAL *)((char *)this + 37328));
}

```

## disassembly

```asm
0x1400b2f24  push    rbx
0x1400b2f26  push    rbp
0x1400b2f27  push    rsi
0x1400b2f28  push    rdi
0x1400b2f29  push    r14
0x1400b2f2b  push    r15
0x1400b2f2d  sub     rsp, 48h
0x1400b2f31  mov     rbx, rcx
0x1400b2f34  call    ?LogTeardownTelemetry@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::LogTeardownTelemetry(void)
0x1400b2f39  xor     r15d, r15d
0x1400b2f3c  cmp     [rbx+0A1B0h], r15
0x1400b2f43  jz      short loc_1400B2F4D
0x1400b2f45  mov     rcx, rbx; this
0x1400b2f48  call    ?RemoveFromAdapterList@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::RemoveFromAdapterList(void)
0x1400b2f4d  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b2f54  mov     word ptr [rbx+0C80h], 101h
0x1400b2f5d  cmp     [rax], r15b
0x1400b2f60  jz      short loc_1400B2F7C
0x1400b2f62  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b2f69  nop     dword ptr [rax+rax+00h]
0x1400b2f6e  mov     [rax+18h], rbx
0x1400b2f72  mov     cs:WdLogGlobalForLineNumber, 3B1h
0x1400b2f7c  mov     rcx, rbx; this
0x1400b2f7f  call    ?DoDeferredUnlock@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::DoDeferredUnlock(void)
0x1400b2f84  mov     rax, [rbx+10h]
0x1400b2f88  mov     rsi, [rax+2E8h]
0x1400b2f8f  mov     rax, [rsi+10h]
0x1400b2f93  cmp     dword ptr [rax+0C2Ch], 9C4h
0x1400b2f9d  jl      short loc_1400B2FE8
0x1400b2f9f  mov     edi, r15d
0x1400b2fa2  cmp     [rsi+58h], r15d
0x1400b2fa6  jbe     short loc_1400B2FE8
0x1400b2fa8  mov     rdx, [rsi+308h]
0x1400b2faf  mov     r8d, [rsi+350h]
0x1400b2fb6  mov     r9d, edi
0x1400b2fb9  lea     rax, [rdx+r9*8]
0x1400b2fbd  cmp     edi, r8d
0x1400b2fc0  jb      short loc_1400B2FC5
0x1400b2fc2  mov     rax, rdx
0x1400b2fc5  mov     rax, [rax]
0x1400b2fc8  mov     ecx, [rax+0Ch]
0x1400b2fcb  test    cl, 2
0x1400b2fce  jz      short loc_1400B2FE1
0x1400b2fd0  cmp     edi, r8d
0x1400b2fd3  jnb     short loc_1400B2FD9
0x1400b2fd5  lea     rdx, [rdx+r9*8]
0x1400b2fd9  mov     rcx, [rdx]; struct _VIDSCH_NODE *
0x1400b2fdc  call    ?VidSchiDestroyNodeSchedulingLog@@YAXPEAU_VIDSCH_NODE@@@Z; VidSchiDestroyNodeSchedulingLog(_VIDSCH_NODE *)
0x1400b2fe1  inc     edi
0x1400b2fe3  cmp     edi, [rsi+58h]
0x1400b2fe6  jb      short loc_1400B2FA8
0x1400b2fe8  mov     rcx, rbx; this
0x1400b2feb  call    ?DestroyPagingFenceObjects@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::DestroyPagingFenceObjects(void)
0x1400b2ff0  mov     r14, [rbx+30h]
0x1400b2ff4  lfence
0x1400b2ff7  mov     rax, [r14+30h]
0x1400b2ffb  mov     esi, r15d
0x1400b2ffe  mov     rbp, [rax]
0x1400b3001  cmp     [rbp+0C28h], r15d
0x1400b3008  jbe     short loc_1400B304F
0x1400b300a  mov     rax, [r14+48h]
0x1400b300e  mov     ecx, esi
0x1400b3010  mov     rdi, [rax+rcx*8]
0x1400b3014  test    rdi, rdi
0x1400b3017  jz      short loc_1400B3045
0x1400b3019  cmp     [rdi+8], r15
0x1400b301d  jz      short loc_1400B3045
0x1400b301f  mov     rcx, [rdi+10h]; struct VIDMM_DMA_BUFFER *
0x1400b3023  test    rcx, rcx
0x1400b3026  jz      short loc_1400B3033
0x1400b3028  mov     dl, 1; bool
0x1400b302a  call    ?VidMmReleaseDmaBuffer@@YAXPEAUVIDMM_DMA_BUFFER@@_N@Z; VidMmReleaseDmaBuffer(VIDMM_DMA_BUFFER *,bool)
0x1400b302f  mov     [rdi+10h], r15
0x1400b3033  mov     rcx, [rdi+8]; this
0x1400b3037  test    rcx, rcx
0x1400b303a  jz      short loc_1400B3041
0x1400b303c  call    ??_GVIDMM_DMA_POOL@@QEAAPEAXI@Z; VIDMM_DMA_POOL::`scalar deleting destructor'(uint)
0x1400b3041  mov     [rdi+8], r15
0x1400b3045  inc     esi
0x1400b3047  cmp     esi, [rbp+0C28h]
0x1400b304d  jb      short loc_1400B300A
0x1400b304f  mov     rcx, [rbx+91A8h]; Entry
0x1400b3056  test    rcx, rcx
0x1400b3059  jz      short loc_1400B3067
0x1400b305b  call    ?ReleaseVaRangeReference@VIDMM_MAPPED_VA_RANGE@@QEAAJXZ; VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(void)
0x1400b3060  mov     [rbx+91A8h], r15
0x1400b3067  lea     rcx, [rbx+8F40h]; this
0x1400b306e  call    ?DestroyPagingProcess@VIDMM_PAGING_PROCESS@@QEAAXXZ; VIDMM_PAGING_PROCESS::DestroyPagingProcess(void)
0x1400b3073  cmp     [rbx+916Ch], r15b
0x1400b307a  jz      short loc_1400B308B
0x1400b307c  mov     rcx, cs:?g_pVidMmSystemProcess@@3PEAVVIDMM_PROCESS@@EA; this
0x1400b3083  mov     rdx, rbx; struct VIDMM_GLOBAL *
0x1400b3086  call    ?CloseAdapter@VIDMM_PROCESS@@QEAAXPEAVVIDMM_GLOBAL@@@Z; VIDMM_PROCESS::CloseAdapter(VIDMM_GLOBAL *)
0x1400b308b  mov     rdi, [rbx]
0x1400b308e  mov     [rbx+0A030h], r15
0x1400b3095  test    rdi, rdi
0x1400b3098  jz      short loc_1400B30AD
0x1400b309a  mov     rcx, rdi
0x1400b309d  call    VidMmTerminateWorkerThread
0x1400b30a2  mov     rcx, rdi; void *
0x1400b30a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b30aa  mov     [rbx], r15
0x1400b30ad  mov     rdi, [rbx+30h]
0x1400b30b1  test    rdi, rdi
0x1400b30b4  jz      short loc_1400B30CA
0x1400b30b6  mov     rcx, rdi; this
0x1400b30b9  call    ??1VIDMM_PAGING@@QEAA@XZ; VIDMM_PAGING::~VIDMM_PAGING(void)
0x1400b30be  mov     rcx, rdi; void *
0x1400b30c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b30c6  mov     [rbx+30h], r15
0x1400b30ca  lea     rdx, ?_PartitionLock@VIDMM_PARTITION@@2U_EX_PUSH_LOCK@@A; struct _EX_PUSH_LOCK *
0x1400b30d1  lea     rcx, [rsp+78h+var_58]; this
0x1400b30d6  call    ??0DXGAUTOEXPUSHLOCKSHARED@@QEAA@QEAU_EX_PUSH_LOCK@@@Z; DXGAUTOEXPUSHLOCKSHARED::DXGAUTOEXPUSHLOCKSHARED(_EX_PUSH_LOCK * const)
0x1400b30db  mov     rax, cs:?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x1400b30e2  mov     rdi, r15
0x1400b30e5  jmp     short loc_1400B30ED
0x1400b30e7  mov     rdi, rax
0x1400b30ea  mov     rax, [rax]
0x1400b30ed  test    rax, rax
0x1400b30f0  jnz     short loc_1400B30E7
0x1400b30f2  jmp     short loc_1400B3160
0x1400b30f4  mov     rcx, rbx; this
0x1400b30f7  call    ?AdapterId@VIDMM_GLOBAL@@QEBAKXZ; VIDMM_GLOBAL::AdapterId(void)
0x1400b30fc  mov     ecx, eax
0x1400b30fe  lea     rsi, [rcx+rcx*2]
0x1400b3102  shl     rsi, 7
0x1400b3106  add     rsi, [rdi+28h]
0x1400b310a  cmp     [rsi+8], r15
0x1400b310e  jz      short loc_1400B3128
0x1400b3110  mov     rcx, rsi; struct VIDMM_PARTITION_ADAPTER_INFO *
0x1400b3113  call    ?VidMmiClosePerfCounters@@YAXPEAUVIDMM_PARTITION_ADAPTER_INFO@@@Z; VidMmiClosePerfCounters(VIDMM_PARTITION_ADAPTER_INFO *)
0x1400b3118  lea     rcx, [rsi+18h]
0x1400b311c  call    ?Clear@?$NonPagedPoolZeroedArray@UVIDMM_SEGMENT_GROUP_STATE@@$00$0GCDBGJFG@@@QEAAXXZ; NonPagedPoolZeroedArray<VIDMM_SEGMENT_GROUP_STATE,1,1647405398>::Clear(void)
0x1400b3121  mov     [rsi+8], r15
0x1400b3125  mov     [rsi], r15
0x1400b3128  mov     rax, [rdi+8]
0x1400b312c  test    rax, rax
0x1400b312f  jz      short loc_1400B3153
0x1400b3131  mov     rcx, [rax]
0x1400b3134  test    rcx, rcx
0x1400b3137  jz      short loc_1400B3149
0x1400b3139  mov     rax, [rcx]
0x1400b313c  mov     rdi, rcx
0x1400b313f  mov     rcx, rax
0x1400b3142  test    rax, rax
0x1400b3145  jnz     short loc_1400B3139
0x1400b3147  jmp     short loc_1400B3160
0x1400b3149  mov     rdi, rax
0x1400b314c  jmp     short loc_1400B3160
0x1400b314e  cmp     [rdi], rax
0x1400b3151  jz      short loc_1400B3160
0x1400b3153  mov     rax, rdi
0x1400b3156  mov     rdi, [rdi+10h]
0x1400b315a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1400b315e  jnz     short loc_1400B314E
0x1400b3160  test    rdi, rdi
0x1400b3163  jnz     short loc_1400B30F4
0x1400b3165  lea     rcx, [rsp+78h+var_58]; this
0x1400b316a  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x1400b316f  mov     edi, r15d
0x1400b3172  cmp     [rbx+0C28h], r15d
0x1400b3179  jbe     short loc_1400B31B3
0x1400b317b  mov     rax, [rbx+8E80h]
0x1400b3182  mov     ecx, edi
0x1400b3184  mov     rcx, [rax+rcx*8]
0x1400b3188  test    byte ptr [rcx+488h], 1
0x1400b318f  jnz     short loc_1400B31A9
0x1400b3191  mov     rcx, [rcx+5F8h]; Instance
0x1400b3198  test    rcx, rcx
0x1400b319b  jz      short loc_1400B31A9
0x1400b319d  call    cs:__imp_PcwCloseInstance
0x1400b31a4  nop     dword ptr [rax+rax+00h]
0x1400b31a9  inc     edi
0x1400b31ab  cmp     edi, [rbx+0C28h]
0x1400b31b1  jb      short loc_1400B317B
0x1400b31b3  mov     rcx, [rbx+0F98h]; void *
0x1400b31ba  test    rcx, rcx
0x1400b31bd  jz      short loc_1400B31D9
0x1400b31bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b31c4  mov     [rbx+0F90h], r15
0x1400b31cb  mov     [rbx+0FA0h], r15
0x1400b31d2  mov     [rbx+0F98h], r15
0x1400b31d9  mov     rcx, [rbx+91F0h]; void *
0x1400b31e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b31e5  mov     eax, [rbx+0C28h]
0x1400b31eb  mov     edi, r15d
0x1400b31ee  test    eax, eax
0x1400b31f0  jz      short loc_1400B3223
0x1400b31f2  mov     rax, [rbx+8E80h]
0x1400b31f9  mov     ecx, edi
0x1400b31fb  mov     rcx, [rax+rcx*8]
0x1400b31ff  mov     rcx, [rcx+8E0h]; Instance
0x1400b3206  test    rcx, rcx
0x1400b3209  jz      short loc_1400B3217
0x1400b320b  call    cs:__imp_PcwCloseInstance
0x1400b3212  nop     dword ptr [rax+rax+00h]
0x1400b3217  mov     eax, [rbx+0C28h]
0x1400b321d  inc     edi
0x1400b321f  cmp     edi, eax
0x1400b3221  jb      short loc_1400B31F2
0x1400b3223  cmp     [rbx+8E80h], r15
0x1400b322a  jz      short loc_1400B327D
0x1400b322c  mov     edi, r15d
0x1400b322f  test    eax, eax
0x1400b3231  jz      short loc_1400B326A
0x1400b3233  mov     rax, [rbx+8E80h]
0x1400b323a  mov     esi, edi
0x1400b323c  mov     rcx, [rax+rsi*8]
0x1400b3240  test    rcx, rcx
0x1400b3243  jz      short loc_1400B3255
0x1400b3245  mov     rax, [rcx]
0x1400b3248  mov     edx, 1
0x1400b324d  mov     rax, [rax]
0x1400b3250  call    _guard_dispatch_icall
0x1400b3255  mov     rax, [rbx+8E80h]
0x1400b325c  inc     edi
0x1400b325e  mov     [rax+rsi*8], r15
0x1400b3262  cmp     edi, [rbx+0C28h]
0x1400b3268  jb      short loc_1400B3233
0x1400b326a  mov     rcx, [rbx+8E80h]; void *
0x1400b3271  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b3276  mov     [rbx+8E80h], r15
0x1400b327d  mov     rcx, [rbx+0A070h]; this
0x1400b3284  test    rcx, rcx
0x1400b3287  jz      short loc_1400B3290
0x1400b3289  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400b328b  call    ?DestroyVaAllocator@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; CVirtualAddressAllocator::DestroyVaAllocator(VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400b3290  mov     rcx, rbx; this
0x1400b3293  call    ?FreeForwardProgressMdl@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::FreeForwardProgressMdl(void)
0x1400b3298  lea     rcx, [rbx+8EC0h]; Lookaside
0x1400b329f  call    cs:__imp_ExDeletePagedLookasideList
0x1400b32a6  nop     dword ptr [rax+rax+00h]
0x1400b32ab  cmp     [rbx+9F80h], r15
0x1400b32b2  jz      short loc_1400B331C
0x1400b32b4  mov     edi, r15d
0x1400b32b7  cmp     [rbx+9F70h], r15d
0x1400b32be  jbe     short loc_1400B3307
0x1400b32c0  mov     rax, [rbx+9F80h]
0x1400b32c7  mov     esi, edi
0x1400b32c9  mov     rcx, [rax+rsi*8]; MemoryDescriptorList
0x1400b32cd  test    rcx, rcx
0x1400b32d0  jz      short loc_1400B32FD
0x1400b32d2  test    byte ptr [rcx+0Ah], 2
0x1400b32d6  jz      short loc_1400B32E4
0x1400b32d8  call    cs:__imp_MmUnlockPages
0x1400b32df  nop     dword ptr [rax+rax+00h]
0x1400b32e4  mov     rcx, [rbx+9F80h]
0x1400b32eb  xor     edx, edx; Tag
0x1400b32ed  mov     rcx, [rcx+rsi*8]; P
0x1400b32f1  call    cs:__imp_ExFreePoolWithTag
0x1400b32f8  nop     dword ptr [rax+rax+00h]
0x1400b32fd  inc     edi
0x1400b32ff  cmp     edi, [rbx+9F70h]
0x1400b3305  jb      short loc_1400B32C0
0x1400b3307  mov     rcx, [rbx+9F80h]; P
0x1400b330e  xor     edx, edx; Tag
0x1400b3310  call    cs:__imp_ExFreePoolWithTag
0x1400b3317  nop     dword ptr [rax+rax+00h]
0x1400b331c  mov     rcx, [rbx+9F48h]; P
0x1400b3323  test    rcx, rcx
0x1400b3326  jz      short loc_1400B3336
0x1400b3328  xor     edx, edx; Tag
0x1400b332a  call    cs:__imp_ExFreePoolWithTag
0x1400b3331  nop     dword ptr [rax+rax+00h]
0x1400b3336  lea     rcx, [rbx+0A1C0h]; this
0x1400b333d  call    ??1VIDMM_LOCKED_PAGE_HISTORY@@QEAA@XZ; VIDMM_LOCKED_PAGE_HISTORY::~VIDMM_LOCKED_PAGE_HISTORY(void)
0x1400b3342  lea     rcx, [rbx+91D0h]; this
0x1400b3349  call    ??1DXGK_LOG@@QEAA@XZ; DXGK_LOG::~DXGK_LOG(void)
0x1400b334e  add     rsp, 48h
0x1400b3352  pop     r15
0x1400b3354  pop     r14
0x1400b3356  pop     rdi
0x1400b3357  pop     rsi
0x1400b3358  pop     rbp
0x1400b3359  pop     rbx
0x1400b335a  retn
```
