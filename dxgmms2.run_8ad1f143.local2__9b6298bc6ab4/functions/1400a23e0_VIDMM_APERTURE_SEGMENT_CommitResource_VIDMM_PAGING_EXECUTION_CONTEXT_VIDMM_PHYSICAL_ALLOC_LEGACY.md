# VIDMM_APERTURE_SEGMENT::CommitResource(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *)

- ea: `0x1400a23e0`
- end: `0x1400a27e9`
- name: `?CommitResource@VIDMM_APERTURE_SEGMENT@@UEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z`
- size: `1033`
- prototype: `__int64 __fastcall(VIDMM_APERTURE_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400045ec`
- `0x140031138`
- `0x140034ad8`
- `0x140047e0c`
- `0x140048090`
- `0x1400a1778`
- `0x1400a1e8c`
- `0x1400a23e0`
- `0x1400a291c`
- `0x1400cee78`
- `0x1400e6a00`
- `0x1400ed558`
- `0x140108cd8`
- `0x140109c10`
- `0x14010ad3c`
- `0x14010db5c`
- `0x140114d94`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a24f7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a24f7`
- `watchdog!WdLogSingleEntry2` at `0x1400a259c`
- `watchdog!WdLogSingleEntry2` at `0x1400a259c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a240a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a240a`
- `watchdog!WdLogSingleEntry1` at `0x1400a2453`
- `watchdog!WdLogSingleEntry1` at `0x1400a250e`
- `watchdog!WdLogSingleEntry1` at `0x1400a2453`
- `watchdog!WdLogSingleEntry1` at `0x1400a250e`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a23f1`

## pseudocode

```c
__int64 __fastcall VIDMM_APERTURE_SEGMENT::CommitResource(
        VIDMM_GLOBAL **this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        struct VIDMM_PHYSICAL_ALLOC_LEGACY *a3)
{
  __int64 v3; // rdi
  __int64 v7; // rax
  __int64 result; // rax
  char v9; // r13
  char v10; // r15
  __int64 v11; // rbp
  __int64 v12; // rcx
  int v14; // ecx
  int v15; // r8d
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // ecx
  bool v20; // al
  __int64 *v21; // rbx
  VIDMM_SEGMENT *v22; // rcx
  __int64 v23; // rax
  _DWORD *v24; // rax
  VIDMM_GLOBAL *v25; // rbp
  struct VIDMM_PHYSICAL_ADAPTER *v26; // rbx
  const unsigned __int64 *FullPfnArray; // rax
  unsigned __int16 v28; // ax
  unsigned __int64 Priority; // [rsp+28h] [rbp-80h]
  __int64 v30; // [rsp+B0h] [rbp+8h]

  v3 = *(_QWORD *)a3;
  if ( g_IsInternalReleaseOrDbg )
  {
    v7 = WdLogNewEntry5_WdTrace(this, a2);
    *(_QWORD *)(v7 + 24) = v3;
    *(_QWORD *)(v7 + 32) = *(int *)(v3 + 188);
    WdLogGlobalForLineNumber = 387;
  }
  VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(this[1], (struct VIDMM_GLOBAL_ALLOC *)v3, 1u);
  if ( VIDMM_GLOBAL::IsTdrPending(this[1]) )
  {
    WdLogSingleEntry1(4, v3);
    result = 3221226166LL;
    WdLogGlobalForLineNumber = 428;
    return result;
  }
  v9 = 0;
  if ( (*(_DWORD *)(v3 + 28) & 2) != 0 )
  {
    v21 = (__int64 *)((char *)a3 + 112);
  }
  else
  {
    if ( (*(_DWORD *)(v3 + 32) & 2) != 0 )
    {
      v10 = 0;
      v9 = 1;
    }
    else
    {
      LODWORD(v11) = VIDMM_SEGMENT::LockAllocationBackingStore((VIDMM_SEGMENT *)this, (struct VIDMM_GLOBAL_ALLOC *)v3);
      if ( (int)v11 < 0 )
        return (unsigned int)v11;
      v10 = 1;
    }
    LODWORD(v11) = VidMmiEnsureSystemCommitMdl((struct VIDMM_SEGMENT *)this, (struct VIDMM_GLOBAL_ALLOC *)v3);
    if ( (int)v11 < 0 )
    {
LABEL_17:
      if ( v10 )
        VIDMM_SEGMENT::UnlockAllocationBackingStore(this[1], (struct VIDMM_GLOBAL_ALLOC *)v3, 0);
      return (unsigned int)v11;
    }
    if ( (**(_DWORD **)(v3 + 384) & 0x4000) != 0 )
    {
      v12 = *(_QWORD *)(v3 + 56);
      if ( !((*(_BYTE *)(v12 + 10) & 5) != 0
           ? *(PVOID *)(v12 + 24)
           : MmMapLockedPagesSpecifyCache((PMDL)v12, 0, MmCached, 0, 0, 0x40000010u)) )
      {
        WdLogSingleEntry1(1, v3);
        WdLogGlobalForLineNumber = 506;
        DxgkLogInternalTriageEvent(
          v14,
          0x40000,
          v15,
          (unsigned int)L"Failed to get system address for history buffer. GlobalAlloc=%I64X",
          v3,
          0,
          0,
          0);
        LODWORD(v11) = -1073741801;
        goto LABEL_17;
      }
    }
    if ( *((_BYTE *)this[1] + 36258) )
    {
      v16 = VIDMM_SEGMENT::MapAllocationToIoMmu((VIDMM_SEGMENT *)this, a2, (struct VIDMM_GLOBAL_ALLOC *)v3);
      v11 = v16;
      if ( v16 < 0 )
      {
        _InterlockedIncrement(&dword_140086838);
        WdLogSingleEntry2(6, v3, v16);
        WdLogGlobalForLineNumber = 522;
        DxgkLogInternalTriageEvent(
          v17,
          262145,
          v18,
          (unsigned int)L"Failed to map allocation to the IOMMU. GlobalAlloc=0x%.16I64x, Status=0x%.8x",
          v3,
          v11,
          0,
          0);
        goto LABEL_17;
      }
    }
    VIDMM_SEGMENT::FlushPendingCPUAccess((VIDMM_SEGMENT *)this, a3);
    v19 = **(_DWORD **)(v3 + 384);
    if ( (v19 & 4) == 0 || (v20 = 1, (v19 & 0x800000) != 0) )
      v20 = 0;
    v21 = (__int64 *)((char *)a3 + 112);
    VIDMM_APERTURE_SEGMENT::MapApertureRange(
      (VIDMM_APERTURE_SEGMENT *)this,
      a2,
      a3,
      *((_QWORD *)a3 + 2) >> 12,
      *((_QWORD *)a3 + 14) >> 12,
      Priority,
      *(const struct _MDL **)(v3 + 56),
      0,
      v20);
  }
  v22 = (VIDMM_SEGMENT *)*((_QWORD *)a3 + 15);
  v23 = *v21;
  *((_QWORD *)a3 + 17) = v22;
  *((_QWORD *)a3 + 18) = v23;
  *(_WORD *)(*(_QWORD *)(v3 + 384) + 10LL) = VIDMM_SEGMENT::DriverId(v22);
  *(_QWORD *)(*(_QWORD *)(v3 + 384) + 40LL) = *((_QWORD *)a3 + 18) + *(_QWORD *)(*((_QWORD *)a3 + 17) + 24LL);
  *((_QWORD *)a3 + 15) = 0;
  *v21 = 0;
  v24 = *(_DWORD **)(v3 + 384);
  *(_DWORD *)(v3 + 32) &= ~8u;
  if ( (*v24 & 0x10000) != 0 )
  {
    v30 = (unsigned int)Feature_NotifyResidency2__private_featureState;
    if ( (Feature_NotifyResidency2__private_featureState & 0x10) == 0 )
    {
      LODWORD(v30) = Feature_NotifyResidency2__private_featureState | 1;
      wil_details_FeatureReporting_ReportUsageToService(Feature_NotifyResidency2__private_descriptor, v30, 3);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v30, 3, Feature_NotifyResidency2__private_descriptor);
    }
    v25 = this[1];
    if ( *(_QWORD *)(*((_QWORD *)v25 + 3) + 1776LL) )
    {
      v26 = *(struct VIDMM_PHYSICAL_ADAPTER **)(*((_QWORD *)v25 + 4560) + 8LL * ((*((_DWORD *)a3 + 15) >> 2) & 0x3F));
      FullPfnArray = VidMmGetFullPfnArray((const struct VIDMM_GLOBAL_ALLOC *)v3);
      VIDMM_GLOBAL::NotifyResidency2(
        v25,
        a2,
        v26,
        a3,
        1,
        1,
        0,
        (*((_QWORD *)a3 + 2) >> 12) + ((*((_QWORD *)a3 + 2) & 0xFFFLL) != 0),
        *((unsigned __int16 *)this + 35),
        *((_QWORD *)a3 + 18) >> 12,
        FullPfnArray);
    }
    else
    {
      v28 = VIDMM_SEGMENT::DriverId((VIDMM_SEGMENT *)this);
      VIDMM_GLOBAL::NotifyResidency(v25, a2, (struct VIDMM_GLOBAL_ALLOC *)v3, 1, v28, *((_QWORD *)a3 + 18));
    }
  }
  if ( v9 )
  {
    VIDMM_GLOBAL::ReturnPinnedBackingStore(this[1], *((_QWORD *)a3 + 2));
    *(_DWORD *)(v3 + 32) &= ~2u;
  }
  return 0;
}

```

## disassembly

```asm
0x1400a23e0  push    rbx
0x1400a23e2  push    rbp
0x1400a23e3  push    rsi
0x1400a23e4  push    rdi
0x1400a23e5  push    r12
0x1400a23e7  push    r13
0x1400a23e9  push    r14
0x1400a23eb  push    r15
0x1400a23ed  sub     rsp, 68h
0x1400a23f1  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a23f8  xor     ebx, ebx
0x1400a23fa  mov     rdi, [r8]
0x1400a23fd  mov     r14, r8
0x1400a2400  mov     r12, rdx
0x1400a2403  mov     rsi, rcx
0x1400a2406  cmp     [rax], bl
0x1400a2408  jz      short loc_1400A242F
0x1400a240a  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a2411  nop     dword ptr [rax+rax+00h]
0x1400a2416  mov     [rax+18h], rdi
0x1400a241a  movsxd  r9, dword ptr [rdi+0BCh]
0x1400a2421  mov     [rax+20h], r9
0x1400a2425  mov     cs:WdLogGlobalForLineNumber, 183h
0x1400a242f  mov     rcx, [rsi+8]; this
0x1400a2433  mov     r8b, 1; unsigned __int8
0x1400a2436  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a2439  call    ?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z; VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)
0x1400a243e  mov     rcx, [rsi+8]; this
0x1400a2442  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400a2447  test    al, al
0x1400a2449  jz      short loc_1400A2473
0x1400a244b  mov     rdx, rdi
0x1400a244e  mov     ecx, 4
0x1400a2453  call    cs:__imp_WdLogSingleEntry1
0x1400a245a  nop     dword ptr [rax+rax+00h]
0x1400a245f  mov     eax, 0C00002B6h
0x1400a2464  mov     cs:WdLogGlobalForLineNumber, 1ACh
0x1400a246e  jmp     loc_1400A27D7
0x1400a2473  mov     eax, [rdi+1Ch]
0x1400a2476  mov     r13b, bl
0x1400a2479  test    al, 2
0x1400a247b  jnz     loc_1400A263C
0x1400a2481  mov     eax, [rdi+20h]
0x1400a2484  test    al, 2
0x1400a2486  jz      short loc_1400A2490
0x1400a2488  mov     r15b, bl
0x1400a248b  mov     r13b, 1
0x1400a248e  jmp     short loc_1400A24A8
0x1400a2490  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a2493  mov     rcx, rsi; this
0x1400a2496  call    ?LockAllocationBackingStore@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::LockAllocationBackingStore(VIDMM_GLOBAL_ALLOC *)
0x1400a249b  mov     ebp, eax
0x1400a249d  test    eax, eax
0x1400a249f  js      loc_1400A2562
0x1400a24a5  mov     r15b, 1
0x1400a24a8  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a24ab  mov     rcx, rsi; struct VIDMM_SEGMENT *
0x1400a24ae  call    ?VidMmiEnsureSystemCommitMdl@@YAJPEAVVIDMM_SEGMENT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VidMmiEnsureSystemCommitMdl(VIDMM_SEGMENT *,VIDMM_GLOBAL_ALLOC *)
0x1400a24b3  mov     ebp, eax
0x1400a24b5  test    eax, eax
0x1400a24b7  js      loc_1400A254E
0x1400a24bd  mov     rax, [rdi+180h]
0x1400a24c4  mov     ecx, [rax]
0x1400a24c6  shr     ecx, 0Eh
0x1400a24c9  test    cl, 1
0x1400a24cc  jz      loc_1400A2569
0x1400a24d2  mov     rcx, [rdi+38h]; MemoryDescriptorList
0x1400a24d6  test    byte ptr [rcx+0Ah], 5
0x1400a24da  jz      short loc_1400A24E2
0x1400a24dc  mov     rax, [rcx+18h]
0x1400a24e0  jmp     short loc_1400A2503
0x1400a24e2  xor     r9d, r9d; RequestedAddress
0x1400a24e5  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x1400a24ed  xor     edx, edx; AccessMode
0x1400a24ef  mov     [rsp+0A8h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x1400a24f3  lea     r8d, [r9+1]; CacheType
0x1400a24f7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400a24fe  nop     dword ptr [rax+rax+00h]
0x1400a2503  test    rax, rax
0x1400a2506  jnz     short loc_1400A2569
0x1400a2508  mov     rdx, rdi
0x1400a250b  lea     ecx, [rax+1]
0x1400a250e  call    cs:__imp_WdLogSingleEntry1
0x1400a2515  nop     dword ptr [rax+rax+00h]
0x1400a251a  mov     qword ptr [rsp+0A8h+var_70], rbx
0x1400a251f  lea     r9, aFailedToGetSys; "Failed to get system address for histor"...
0x1400a2526  mov     [rsp+0A8h+var_78], rbx
0x1400a252b  mov     edx, 40000h
0x1400a2530  mov     qword ptr [rsp+0A8h+Priority], rbx
0x1400a2535  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a253a  mov     cs:WdLogGlobalForLineNumber, 1FAh
0x1400a2544  call    DxgkLogInternalTriageEvent
0x1400a2549  mov     ebp, 0C0000017h
0x1400a254e  test    r15b, r15b
0x1400a2551  jz      short loc_1400A2562
0x1400a2553  mov     rcx, [rsi+8]; this
0x1400a2557  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC *
0x1400a255a  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a255d  call    ?UnlockAllocationBackingStore@VIDMM_SEGMENT@@SAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_SEGMENT::UnlockAllocationBackingStore(VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x1400a2562  mov     eax, ebp
0x1400a2564  jmp     loc_1400A27D7
0x1400a2569  mov     rax, [rsi+8]
0x1400a256d  cmp     [rax+8DA2h], bl
0x1400a2573  jz      short loc_1400A25DC
0x1400a2575  mov     r8, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a2578  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a257b  mov     rcx, rsi; this
0x1400a257e  call    ?MapAllocationToIoMmu@VIDMM_SEGMENT@@IEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::MapAllocationToIoMmu(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400a2583  movsxd  rbp, eax
0x1400a2586  test    eax, eax
0x1400a2588  jns     short loc_1400A25DC
0x1400a258a  lock inc cs:dword_140086838
0x1400a2591  mov     r8, rbp
0x1400a2594  mov     rdx, rdi
0x1400a2597  mov     ecx, 6
0x1400a259c  call    cs:__imp_WdLogSingleEntry2
0x1400a25a3  nop     dword ptr [rax+rax+00h]
0x1400a25a8  mov     qword ptr [rsp+0A8h+var_70], rbx
0x1400a25ad  lea     r9, aFailedToMapAll; "Failed to map allocation to the IOMMU. "...
0x1400a25b4  mov     [rsp+0A8h+var_78], rbx
0x1400a25b9  mov     edx, 40001h
0x1400a25be  mov     qword ptr [rsp+0A8h+Priority], rbp
0x1400a25c3  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a25c8  mov     cs:WdLogGlobalForLineNumber, 20Ah
0x1400a25d2  call    DxgkLogInternalTriageEvent
0x1400a25d7  jmp     loc_1400A254E
0x1400a25dc  mov     rdx, r14; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a25df  mov     rcx, rsi; this
0x1400a25e2  call    ?FlushPendingCPUAccess@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z; VIDMM_SEGMENT::FlushPendingCPUAccess(VIDMM_PHYSICAL_ALLOC_LEGACY *)
0x1400a25e7  mov     rax, [rdi+180h]
0x1400a25ee  mov     ecx, [rax]
0x1400a25f0  test    cl, 4
0x1400a25f3  jz      short loc_1400A25FD
0x1400a25f5  mov     al, 1
0x1400a25f7  bt      ecx, 17h
0x1400a25fb  jnb     short loc_1400A25FF
0x1400a25fd  mov     al, bl
0x1400a25ff  mov     r9, [r14+10h]
0x1400a2603  lea     rbx, [r14+70h]
0x1400a2607  mov     rcx, [rbx]
0x1400a260a  xor     r15d, r15d
0x1400a260d  mov     [rsp+0A8h+var_68], al; bool
0x1400a2611  mov     r8, r14; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a2614  mov     rax, [rdi+38h]
0x1400a2618  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a261b  shr     rcx, 0Ch
0x1400a261f  mov     [rsp+0A8h+var_70], r15b; bool
0x1400a2624  mov     [rsp+0A8h+var_78], rax; struct _MDL *
0x1400a2629  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rcx; unsigned __int64
0x1400a262e  mov     rcx, rsi; this
0x1400a2631  shr     r9, 0Ch; unsigned __int64
0x1400a2635  call    ?MapApertureRange@VIDMM_APERTURE_SEGMENT@@AEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_K22PEBU_MDL@@_N4@Z; VIDMM_APERTURE_SEGMENT::MapApertureRange(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,unsigned __int64,unsigned __int64,unsigned __int64,_MDL const *,bool,bool)
0x1400a263a  jmp     short loc_1400A2643
0x1400a263c  lea     rbx, [r14+70h]
0x1400a2640  xor     r15d, r15d
0x1400a2643  mov     rcx, [r14+78h]; this
0x1400a2647  mov     rax, [rbx]
0x1400a264a  mov     [r14+88h], rcx
0x1400a2651  mov     [r14+90h], rax
0x1400a2658  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x1400a265d  mov     rcx, [rdi+180h]
0x1400a2664  mov     [rcx+0Ah], ax
0x1400a2668  mov     rax, [r14+88h]
0x1400a266f  mov     rcx, [rax+18h]
0x1400a2673  mov     rax, [rdi+180h]
0x1400a267a  add     rcx, [r14+90h]
0x1400a2681  mov     [rax+28h], rcx
0x1400a2685  mov     [r14+78h], r15
0x1400a2689  mov     [rbx], r15
0x1400a268c  mov     rax, [rdi+180h]
0x1400a2693  and     dword ptr [rdi+20h], 0FFFFFFF7h
0x1400a2697  test    dword ptr [rax], 10000h
0x1400a269d  jz      loc_1400A27BF
0x1400a26a3  mov     ecx, cs:Feature_NotifyResidency2__private_featureState
0x1400a26a9  mov     [rsp+0A8h+arg_0], r15
0x1400a26b1  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x1400a26b8  test    cl, 10h
0x1400a26bb  jnz     short loc_1400A2709
0x1400a26bd  mov     rax, [rsp+0A8h+arg_0]
0x1400a26c5  or      ecx, 1
0x1400a26c8  mov     [rsp+0A8h+arg_0], rax
0x1400a26d0  mov     ebx, 3
0x1400a26d5  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x1400a26dc  mov     r8d, ebx
0x1400a26df  mov     rdx, [rsp+0A8h+arg_0]
0x1400a26e7  lea     rcx, Feature_NotifyResidency2__private_descriptor
0x1400a26ee  call    wil_details_FeatureReporting_ReportUsageToService
0x1400a26f3  mov     rcx, [rsp+0A8h+arg_0]
0x1400a26fb  lea     r8, Feature_NotifyResidency2__private_descriptor
0x1400a2702  mov     edx, ebx
0x1400a2704  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400a2709  mov     rbp, [rsi+8]
0x1400a270d  mov     rax, [rbp+18h]
0x1400a2711  cmp     [rax+6F0h], r15
0x1400a2718  jz      short loc_1400A2795
0x1400a271a  mov     ecx, [r14+3Ch]
0x1400a271e  mov     rax, [rbp+8E80h]
0x1400a2725  shr     rcx, 2
0x1400a2729  and     ecx, 3Fh
0x1400a272c  mov     rbx, [rax+rcx*8]
0x1400a2730  mov     rcx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a2733  call    ?VidMmGetFullPfnArray@@YAPEB_KPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetFullPfnArray(VIDMM_GLOBAL_ALLOC const *)
0x1400a2738  mov     r10, [r14+10h]
0x1400a273c  mov     edx, r15d
0x1400a273f  movzx   r9d, word ptr [rsi+46h]
0x1400a2744  mov     r8, rbx; struct VIDMM_PHYSICAL_ADAPTER *
0x1400a2747  mov     r11, [r14+90h]
0x1400a274e  mov     rcx, rbp; this
0x1400a2751  mov     [rsp+0A8h+var_58], rax; unsigned __int64 *
0x1400a2756  shr     r11, 0Ch
0x1400a275a  mov     [rsp+0A8h+var_60], r11; unsigned __int64
0x1400a275f  test    r10, 0FFFh
0x1400a2766  mov     dword ptr [rsp+0A8h+var_68], r9d; unsigned int
0x1400a276b  mov     r9, r14; struct VIDMM_PHYSICAL_ALLOC *
0x1400a276e  setnz   dl
0x1400a2771  shr     r10, 0Ch
0x1400a2775  add     edx, r10d
0x1400a2778  mov     dword ptr [rsp+0A8h+var_70], edx; unsigned int
0x1400a277c  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a277f  mov     dword ptr [rsp+0A8h+var_78], r15d; unsigned int
0x1400a2784  mov     byte ptr [rsp+0A8h+Priority], 1; bool
0x1400a2789  mov     byte ptr [rsp+0A8h+BugCheckOnFailure], 1; bool
0x1400a278e  call    ?NotifyResidency2@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@_N3III_KPEB_K@Z; VIDMM_GLOBAL::NotifyResidency2(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,bool,bool,uint,uint,uint,unsigned __int64,unsigned __int64 const *)
0x1400a2793  jmp     short loc_1400A27BF
0x1400a2795  mov     rcx, rsi; this
0x1400a2798  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x1400a279d  mov     rcx, [r14+90h]
0x1400a27a4  mov     r9b, 1; bool
0x1400a27a7  mov     qword ptr [rsp+0A8h+Priority], rcx; unsigned __int64
0x1400a27ac  mov     r8, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a27af  mov     rcx, rbp; this
0x1400a27b2  mov     word ptr [rsp+0A8h+BugCheckOnFailure], ax; unsigned __int16
0x1400a27b7  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a27ba  call    ?NotifyResidency@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@_NG_K@Z; VIDMM_GLOBAL::NotifyResidency(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,bool,ushort,unsigned __int64)
0x1400a27bf  test    r13b, r13b
0x1400a27c2  jz      short loc_1400A27D5
0x1400a27c4  mov     rdx, [r14+10h]; unsigned __int64
0x1400a27c8  mov     rcx, [rsi+8]; this
0x1400a27cc  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x1400a27d1  and     dword ptr [rdi+20h], 0FFFFFFFDh
0x1400a27d5  xor     eax, eax
0x1400a27d7  add     rsp, 68h
0x1400a27db  pop     r15
0x1400a27dd  pop     r14
0x1400a27df  pop     r13
0x1400a27e1  pop     r12
0x1400a27e3  pop     rdi
0x1400a27e4  pop     rsi
0x1400a27e5  pop     rbp
0x1400a27e6  pop     rbx
0x1400a27e7  retn
```
