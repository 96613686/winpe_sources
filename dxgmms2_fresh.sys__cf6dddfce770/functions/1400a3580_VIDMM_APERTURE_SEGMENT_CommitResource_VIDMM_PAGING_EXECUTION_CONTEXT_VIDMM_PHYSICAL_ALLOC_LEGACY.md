# VIDMM_APERTURE_SEGMENT::CommitResource(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *)

- ea: `0x1400a3580`
- end: `0x1400a3989`
- name: `?CommitResource@VIDMM_APERTURE_SEGMENT@@UEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z`
- size: `1033`
- prototype: `__int64 __fastcall(VIDMM_APERTURE_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140004268`
- `0x14002ed18`
- `0x1400333c8`
- `0x140048084`
- `0x140048308`
- `0x1400a2918`
- `0x1400a302c`
- `0x1400a3580`
- `0x1400a3abc`
- `0x1400d5098`
- `0x1400ef500`
- `0x14010d018`
- `0x14010d9c0`
- `0x14010e858`
- `0x140110658`
- `0x1401114dc`
- `0x140118954`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a3697`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a3697`
- `watchdog!WdLogSingleEntry2` at `0x1400a373c`
- `watchdog!WdLogSingleEntry2` at `0x1400a373c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a35aa`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a35aa`
- `watchdog!WdLogSingleEntry1` at `0x1400a35f3`
- `watchdog!WdLogSingleEntry1` at `0x1400a36ae`
- `watchdog!WdLogSingleEntry1` at `0x1400a35f3`
- `watchdog!WdLogSingleEntry1` at `0x1400a36ae`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a3591`

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
    if ( (**(_DWORD **)(v3 + 392) & 0x4000) != 0 )
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
        _InterlockedIncrement(&dword_140087818);
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
    v19 = **(_DWORD **)(v3 + 392);
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
  *(_WORD *)(*(_QWORD *)(v3 + 392) + 10LL) = VIDMM_SEGMENT::DriverId(v22);
  *(_QWORD *)(*(_QWORD *)(v3 + 392) + 40LL) = *((_QWORD *)a3 + 18) + *(_QWORD *)(*((_QWORD *)a3 + 17) + 24LL);
  *((_QWORD *)a3 + 15) = 0;
  *v21 = 0;
  v24 = *(_DWORD **)(v3 + 392);
  *(_DWORD *)(v3 + 32) &= ~8u;
  if ( (*v24 & 0x10000) != 0 )
  {
    v30 = (unsigned int)Feature_NotifyResidency2__private_featureState;
    if ( (Feature_NotifyResidency2__private_featureState & 0x10) == 0 )
    {
      LODWORD(v30) = Feature_NotifyResidency2__private_featureState | 1;
      wil_details_FeatureReporting_ReportUsageToService(&Feature_NotifyResidency2__private_descriptor, v30, 3);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v30, 3, &Feature_NotifyResidency2__private_descriptor);
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
0x1400a3580  push    rbx
0x1400a3582  push    rbp
0x1400a3583  push    rsi
0x1400a3584  push    rdi
0x1400a3585  push    r12
0x1400a3587  push    r13
0x1400a3589  push    r14
0x1400a358b  push    r15
0x1400a358d  sub     rsp, 68h
0x1400a3591  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a3598  xor     ebx, ebx
0x1400a359a  mov     rdi, [r8]
0x1400a359d  mov     r14, r8
0x1400a35a0  mov     r12, rdx
0x1400a35a3  mov     rsi, rcx
0x1400a35a6  cmp     [rax], bl
0x1400a35a8  jz      short loc_1400A35CF
0x1400a35aa  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a35b1  nop     dword ptr [rax+rax+00h]
0x1400a35b6  mov     [rax+18h], rdi
0x1400a35ba  movsxd  r9, dword ptr [rdi+0BCh]
0x1400a35c1  mov     [rax+20h], r9
0x1400a35c5  mov     cs:WdLogGlobalForLineNumber, 183h
0x1400a35cf  mov     rcx, [rsi+8]; this
0x1400a35d3  mov     r8b, 1; unsigned __int8
0x1400a35d6  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a35d9  call    ?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z; VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)
0x1400a35de  mov     rcx, [rsi+8]; this
0x1400a35e2  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400a35e7  test    al, al
0x1400a35e9  jz      short loc_1400A3613
0x1400a35eb  mov     rdx, rdi
0x1400a35ee  mov     ecx, 4
0x1400a35f3  call    cs:__imp_WdLogSingleEntry1
0x1400a35fa  nop     dword ptr [rax+rax+00h]
0x1400a35ff  mov     eax, 0C00002B6h
0x1400a3604  mov     cs:WdLogGlobalForLineNumber, 1ACh
0x1400a360e  jmp     loc_1400A3977
0x1400a3613  mov     eax, [rdi+1Ch]
0x1400a3616  mov     r13b, bl
0x1400a3619  test    al, 2
0x1400a361b  jnz     loc_1400A37DC
0x1400a3621  mov     eax, [rdi+20h]
0x1400a3624  test    al, 2
0x1400a3626  jz      short loc_1400A3630
0x1400a3628  mov     r15b, bl
0x1400a362b  mov     r13b, 1
0x1400a362e  jmp     short loc_1400A3648
0x1400a3630  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a3633  mov     rcx, rsi; this
0x1400a3636  call    ?LockAllocationBackingStore@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::LockAllocationBackingStore(VIDMM_GLOBAL_ALLOC *)
0x1400a363b  mov     ebp, eax
0x1400a363d  test    eax, eax
0x1400a363f  js      loc_1400A3702
0x1400a3645  mov     r15b, 1
0x1400a3648  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a364b  mov     rcx, rsi; struct VIDMM_SEGMENT *
0x1400a364e  call    ?VidMmiEnsureSystemCommitMdl@@YAJPEAVVIDMM_SEGMENT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VidMmiEnsureSystemCommitMdl(VIDMM_SEGMENT *,VIDMM_GLOBAL_ALLOC *)
0x1400a3653  mov     ebp, eax
0x1400a3655  test    eax, eax
0x1400a3657  js      loc_1400A36EE
0x1400a365d  mov     rax, [rdi+188h]
0x1400a3664  mov     ecx, [rax]
0x1400a3666  shr     ecx, 0Eh
0x1400a3669  test    cl, 1
0x1400a366c  jz      loc_1400A3709
0x1400a3672  mov     rcx, [rdi+38h]; MemoryDescriptorList
0x1400a3676  test    byte ptr [rcx+0Ah], 5
0x1400a367a  jz      short loc_1400A3682
0x1400a367c  mov     rax, [rcx+18h]
0x1400a3680  jmp     short loc_1400A36A3
0x1400a3682  xor     r9d, r9d; RequestedAddress
0x1400a3685  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x1400a368d  xor     edx, edx; AccessMode
0x1400a368f  mov     [rsp+0A8h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x1400a3693  lea     r8d, [r9+1]; CacheType
0x1400a3697  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400a369e  nop     dword ptr [rax+rax+00h]
0x1400a36a3  test    rax, rax
0x1400a36a6  jnz     short loc_1400A3709
0x1400a36a8  mov     rdx, rdi
0x1400a36ab  lea     ecx, [rax+1]
0x1400a36ae  call    cs:__imp_WdLogSingleEntry1
0x1400a36b5  nop     dword ptr [rax+rax+00h]
0x1400a36ba  mov     qword ptr [rsp+0A8h+var_70], rbx
0x1400a36bf  lea     r9, aFailedToGetSys; "Failed to get system address for histor"...
0x1400a36c6  mov     [rsp+0A8h+var_78], rbx
0x1400a36cb  mov     edx, 40000h
0x1400a36d0  mov     qword ptr [rsp+0A8h+Priority], rbx
0x1400a36d5  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a36da  mov     cs:WdLogGlobalForLineNumber, 1FAh
0x1400a36e4  call    DxgkLogInternalTriageEvent
0x1400a36e9  mov     ebp, 0C0000017h
0x1400a36ee  test    r15b, r15b
0x1400a36f1  jz      short loc_1400A3702
0x1400a36f3  mov     rcx, [rsi+8]; this
0x1400a36f7  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC *
0x1400a36fa  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a36fd  call    ?UnlockAllocationBackingStore@VIDMM_SEGMENT@@SAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_SEGMENT::UnlockAllocationBackingStore(VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x1400a3702  mov     eax, ebp
0x1400a3704  jmp     loc_1400A3977
0x1400a3709  mov     rax, [rsi+8]
0x1400a370d  cmp     [rax+8DA2h], bl
0x1400a3713  jz      short loc_1400A377C
0x1400a3715  mov     r8, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a3718  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a371b  mov     rcx, rsi; this
0x1400a371e  call    ?MapAllocationToIoMmu@VIDMM_SEGMENT@@IEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::MapAllocationToIoMmu(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400a3723  movsxd  rbp, eax
0x1400a3726  test    eax, eax
0x1400a3728  jns     short loc_1400A377C
0x1400a372a  lock inc cs:dword_140087818
0x1400a3731  mov     r8, rbp
0x1400a3734  mov     rdx, rdi
0x1400a3737  mov     ecx, 6
0x1400a373c  call    cs:__imp_WdLogSingleEntry2
0x1400a3743  nop     dword ptr [rax+rax+00h]
0x1400a3748  mov     qword ptr [rsp+0A8h+var_70], rbx
0x1400a374d  lea     r9, aFailedToMapAll; "Failed to map allocation to the IOMMU. "...
0x1400a3754  mov     [rsp+0A8h+var_78], rbx
0x1400a3759  mov     edx, 40001h
0x1400a375e  mov     qword ptr [rsp+0A8h+Priority], rbp
0x1400a3763  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a3768  mov     cs:WdLogGlobalForLineNumber, 20Ah
0x1400a3772  call    DxgkLogInternalTriageEvent
0x1400a3777  jmp     loc_1400A36EE
0x1400a377c  mov     rdx, r14; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a377f  mov     rcx, rsi; this
0x1400a3782  call    ?FlushPendingCPUAccess@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z; VIDMM_SEGMENT::FlushPendingCPUAccess(VIDMM_PHYSICAL_ALLOC_LEGACY *)
0x1400a3787  mov     rax, [rdi+188h]
0x1400a378e  mov     ecx, [rax]
0x1400a3790  test    cl, 4
0x1400a3793  jz      short loc_1400A379D
0x1400a3795  mov     al, 1
0x1400a3797  bt      ecx, 17h
0x1400a379b  jnb     short loc_1400A379F
0x1400a379d  mov     al, bl
0x1400a379f  mov     r9, [r14+10h]
0x1400a37a3  lea     rbx, [r14+70h]
0x1400a37a7  mov     rcx, [rbx]
0x1400a37aa  xor     r15d, r15d
0x1400a37ad  mov     [rsp+0A8h+var_68], al; bool
0x1400a37b1  mov     r8, r14; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a37b4  mov     rax, [rdi+38h]
0x1400a37b8  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a37bb  shr     rcx, 0Ch
0x1400a37bf  mov     [rsp+0A8h+var_70], r15b; bool
0x1400a37c4  mov     [rsp+0A8h+var_78], rax; struct _MDL *
0x1400a37c9  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rcx; unsigned __int64
0x1400a37ce  mov     rcx, rsi; this
0x1400a37d1  shr     r9, 0Ch; unsigned __int64
0x1400a37d5  call    ?MapApertureRange@VIDMM_APERTURE_SEGMENT@@AEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_K22PEBU_MDL@@_N4@Z; VIDMM_APERTURE_SEGMENT::MapApertureRange(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,unsigned __int64,unsigned __int64,unsigned __int64,_MDL const *,bool,bool)
0x1400a37da  jmp     short loc_1400A37E3
0x1400a37dc  lea     rbx, [r14+70h]
0x1400a37e0  xor     r15d, r15d
0x1400a37e3  mov     rcx, [r14+78h]; this
0x1400a37e7  mov     rax, [rbx]
0x1400a37ea  mov     [r14+88h], rcx
0x1400a37f1  mov     [r14+90h], rax
0x1400a37f8  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x1400a37fd  mov     rcx, [rdi+188h]
0x1400a3804  mov     [rcx+0Ah], ax
0x1400a3808  mov     rax, [r14+88h]
0x1400a380f  mov     rcx, [rax+18h]
0x1400a3813  mov     rax, [rdi+188h]
0x1400a381a  add     rcx, [r14+90h]
0x1400a3821  mov     [rax+28h], rcx
0x1400a3825  mov     [r14+78h], r15
0x1400a3829  mov     [rbx], r15
0x1400a382c  mov     rax, [rdi+188h]
0x1400a3833  and     dword ptr [rdi+20h], 0FFFFFFF7h
0x1400a3837  test    dword ptr [rax], 10000h
0x1400a383d  jz      loc_1400A395F
0x1400a3843  mov     ecx, cs:Feature_NotifyResidency2__private_featureState
0x1400a3849  mov     [rsp+0A8h+arg_0], r15
0x1400a3851  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x1400a3858  test    cl, 10h
0x1400a385b  jnz     short loc_1400A38A9
0x1400a385d  mov     rax, [rsp+0A8h+arg_0]
0x1400a3865  or      ecx, 1
0x1400a3868  mov     [rsp+0A8h+arg_0], rax
0x1400a3870  mov     ebx, 3
0x1400a3875  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x1400a387c  mov     r8d, ebx
0x1400a387f  mov     rdx, [rsp+0A8h+arg_0]
0x1400a3887  lea     rcx, Feature_NotifyResidency2__private_descriptor
0x1400a388e  call    wil_details_FeatureReporting_ReportUsageToService
0x1400a3893  mov     rcx, [rsp+0A8h+arg_0]
0x1400a389b  lea     r8, Feature_NotifyResidency2__private_descriptor
0x1400a38a2  mov     edx, ebx
0x1400a38a4  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400a38a9  mov     rbp, [rsi+8]
0x1400a38ad  mov     rax, [rbp+18h]
0x1400a38b1  cmp     [rax+6F0h], r15
0x1400a38b8  jz      short loc_1400A3935
0x1400a38ba  mov     ecx, [r14+3Ch]
0x1400a38be  mov     rax, [rbp+8E80h]
0x1400a38c5  shr     rcx, 2
0x1400a38c9  and     ecx, 3Fh
0x1400a38cc  mov     rbx, [rax+rcx*8]
0x1400a38d0  mov     rcx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a38d3  call    ?VidMmGetFullPfnArray@@YAPEB_KPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetFullPfnArray(VIDMM_GLOBAL_ALLOC const *)
0x1400a38d8  mov     r10, [r14+10h]
0x1400a38dc  mov     edx, r15d
0x1400a38df  movzx   r9d, word ptr [rsi+46h]
0x1400a38e4  mov     r8, rbx; struct VIDMM_PHYSICAL_ADAPTER *
0x1400a38e7  mov     r11, [r14+90h]
0x1400a38ee  mov     rcx, rbp; this
0x1400a38f1  mov     [rsp+0A8h+var_58], rax; unsigned __int64 *
0x1400a38f6  shr     r11, 0Ch
0x1400a38fa  mov     [rsp+0A8h+var_60], r11; unsigned __int64
0x1400a38ff  test    r10, 0FFFh
0x1400a3906  mov     dword ptr [rsp+0A8h+var_68], r9d; unsigned int
0x1400a390b  mov     r9, r14; struct VIDMM_PHYSICAL_ALLOC *
0x1400a390e  setnz   dl
0x1400a3911  shr     r10, 0Ch
0x1400a3915  add     edx, r10d
0x1400a3918  mov     dword ptr [rsp+0A8h+var_70], edx; unsigned int
0x1400a391c  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a391f  mov     dword ptr [rsp+0A8h+var_78], r15d; unsigned int
0x1400a3924  mov     byte ptr [rsp+0A8h+Priority], 1; bool
0x1400a3929  mov     byte ptr [rsp+0A8h+BugCheckOnFailure], 1; bool
0x1400a392e  call    ?NotifyResidency2@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@_N3III_KPEB_K@Z; VIDMM_GLOBAL::NotifyResidency2(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,bool,bool,uint,uint,uint,unsigned __int64,unsigned __int64 const *)
0x1400a3933  jmp     short loc_1400A395F
0x1400a3935  mov     rcx, rsi; this
0x1400a3938  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x1400a393d  mov     rcx, [r14+90h]
0x1400a3944  mov     r9b, 1; bool
0x1400a3947  mov     qword ptr [rsp+0A8h+Priority], rcx; unsigned __int64
0x1400a394c  mov     r8, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a394f  mov     rcx, rbp; this
0x1400a3952  mov     word ptr [rsp+0A8h+BugCheckOnFailure], ax; unsigned __int16
0x1400a3957  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a395a  call    ?NotifyResidency@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@_NG_K@Z; VIDMM_GLOBAL::NotifyResidency(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,bool,ushort,unsigned __int64)
0x1400a395f  test    r13b, r13b
0x1400a3962  jz      short loc_1400A3975
0x1400a3964  mov     rdx, [r14+10h]; unsigned __int64
0x1400a3968  mov     rcx, [rsi+8]; this
0x1400a396c  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x1400a3971  and     dword ptr [rdi+20h], 0FFFFFFFDh
0x1400a3975  xor     eax, eax
0x1400a3977  add     rsp, 68h
0x1400a397b  pop     r15
0x1400a397d  pop     r14
0x1400a397f  pop     r13
0x1400a3981  pop     r12
0x1400a3983  pop     rdi
0x1400a3984  pop     rsi
0x1400a3985  pop     rbp
0x1400a3986  pop     rbx
0x1400a3987  retn
```
