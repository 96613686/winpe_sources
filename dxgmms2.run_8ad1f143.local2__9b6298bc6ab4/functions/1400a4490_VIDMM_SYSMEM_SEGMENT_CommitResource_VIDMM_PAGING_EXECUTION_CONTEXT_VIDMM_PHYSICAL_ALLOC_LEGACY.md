# VIDMM_SYSMEM_SEGMENT::CommitResource(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *)

- ea: `0x1400a4490`
- end: `0x1400a480d`
- name: `?CommitResource@VIDMM_SYSMEM_SEGMENT@@UEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z`
- size: `893`
- prototype: `__int64 __fastcall(VIDMM_SYSMEM_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400045ec`
- `0x140034ad8`
- `0x140035f6c`
- `0x140047e0c`
- `0x140048090`
- `0x1400a1e8c`
- `0x1400a4490`
- `0x1400cee78`
- `0x1400e6a00`
- `0x1400ed558`
- `0x140108cd8`
- `0x140109c10`
- `0x14010ad3c`
- `0x14010db5c`
- `0x140114d94`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a45ab`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a45ab`
- `watchdog!WdLogSingleEntry2` at `0x1400a463b`
- `watchdog!WdLogSingleEntry2` at `0x1400a463b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a44bc`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a44bc`
- `watchdog!WdLogSingleEntry1` at `0x1400a4508`
- `watchdog!WdLogSingleEntry1` at `0x1400a45c1`
- `watchdog!WdLogSingleEntry1` at `0x1400a4508`
- `watchdog!WdLogSingleEntry1` at `0x1400a45c1`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a44a1`

## pseudocode

```c
__int64 __fastcall VIDMM_SYSMEM_SEGMENT::CommitResource(
        VIDMM_GLOBAL **this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        struct VIDMM_PHYSICAL_ALLOC_LEGACY *a3)
{
  __int64 v3; // rdi
  __int64 v7; // rax
  __int64 result; // rax
  char v9; // r14
  char v10; // r15
  __int64 v11; // rbp
  __int64 v12; // rcx
  int v14; // ecx
  int v15; // r8d
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r8d
  _DWORD *v20; // rax
  VIDMM_GLOBAL *v21; // rbp
  const unsigned __int64 *FullPfnArray; // rax
  __int64 v23; // [rsp+B0h] [rbp+8h]

  v3 = *(_QWORD *)a3;
  if ( g_IsInternalReleaseOrDbg )
  {
    v7 = WdLogNewEntry5_WdTrace(this, a2);
    *(_QWORD *)(v7 + 24) = v3;
    *(_QWORD *)(v7 + 32) = *(int *)(v3 + 188);
    WdLogGlobalForLineNumber = 208;
  }
  VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(this[1], (struct VIDMM_GLOBAL_ALLOC *)v3, 1u);
  if ( VIDMM_GLOBAL::IsTdrPending(this[1]) )
  {
    WdLogSingleEntry1(4, v3);
    result = 3221226166LL;
    WdLogGlobalForLineNumber = 247;
    return result;
  }
  if ( (*(_DWORD *)(v3 + 32) & 2) != 0 )
  {
    v9 = 0;
    v10 = 1;
  }
  else
  {
    LODWORD(v11) = VIDMM_SEGMENT::LockAllocationBackingStore((VIDMM_SEGMENT *)this, (struct VIDMM_GLOBAL_ALLOC *)v3);
    if ( (int)v11 < 0 )
      return (unsigned int)v11;
    v10 = 0;
    v9 = 1;
  }
  if ( (**(_DWORD **)(v3 + 384) & 0x4000) != 0 )
  {
    LODWORD(v11) = VidMmiEnsureSystemCommitMdl((struct VIDMM_SEGMENT *)this, (struct VIDMM_GLOBAL_ALLOC *)v3);
    if ( (int)v11 < 0 )
      goto LABEL_19;
    v12 = *(_QWORD *)(v3 + 56);
    if ( !((*(_BYTE *)(v12 + 10) & 5) != 0
         ? *(PVOID *)(v12 + 24)
         : MmMapLockedPagesSpecifyCache((PMDL)v12, 0, MmCached, 0, 0, 0x40000010u)) )
    {
      WdLogSingleEntry1(1, v3);
      WdLogGlobalForLineNumber = 298;
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
      goto LABEL_19;
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
      WdLogGlobalForLineNumber = 315;
      DxgkLogInternalTriageEvent(
        v17,
        262145,
        v18,
        (unsigned int)L"Failed to map allocation to the IOMMU. GlobalAlloc=0x%.16I64x, Status=0x%.8x",
        v3,
        v11,
        0,
        0);
LABEL_19:
      if ( v9 )
        VIDMM_SEGMENT::UnlockAllocationBackingStore(this[1], (struct VIDMM_GLOBAL_ALLOC *)v3, 0);
      return (unsigned int)v11;
    }
  }
  VIDMM_SEGMENT::FlushPendingCPUAccess((VIDMM_SEGMENT *)this, a3);
  if ( (byte_140086201 & 0x10) != 0 )
    McTemplateK0ppq_EtwWriteTransfer(
      (unsigned __int16)(*((_WORD *)this + 35) + 1),
      (unsigned int)EventPagingOpSysmemCommit,
      v19,
      *((_QWORD *)this[1] + 3),
      v3,
      *((_BYTE *)this + 70) + 1);
  *((_QWORD *)a3 + 17) = *((_QWORD *)a3 + 15);
  *((_QWORD *)a3 + 18) = *((_QWORD *)a3 + 14);
  *((_QWORD *)a3 + 15) = 0;
  *((_QWORD *)a3 + 14) = 0;
  v20 = *(_DWORD **)(v3 + 384);
  *(_DWORD *)(v3 + 32) &= ~8u;
  if ( (*v20 & 0x10000) != 0 )
  {
    v23 = (unsigned int)Feature_NotifyResidency2__private_featureState;
    if ( (Feature_NotifyResidency2__private_featureState & 0x10) == 0 )
    {
      LODWORD(v23) = Feature_NotifyResidency2__private_featureState | 1;
      wil_details_FeatureReporting_ReportUsageToService(Feature_NotifyResidency2__private_descriptor, v23, 3);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v23, 3, Feature_NotifyResidency2__private_descriptor);
    }
    v21 = this[1];
    if ( *(_QWORD *)(*((_QWORD *)v21 + 3) + 1776LL) )
    {
      FullPfnArray = VidMmGetFullPfnArray((const struct VIDMM_GLOBAL_ALLOC *)v3);
      VIDMM_GLOBAL::NotifyResidency2(
        v21,
        a2,
        this[2],
        a3,
        1,
        1,
        0,
        (*((_QWORD *)a3 + 2) >> 12) + ((*((_QWORD *)a3 + 2) & 0xFFFLL) != 0),
        *((unsigned __int16 *)this + 35),
        *((_QWORD *)a3 + 18) >> 12,
        FullPfnArray);
    }
  }
  if ( v10 )
  {
    VIDMM_GLOBAL::ReturnPinnedBackingStore(this[1], *((_QWORD *)a3 + 2));
    *(_DWORD *)(v3 + 32) &= ~2u;
  }
  return 0;
}

```

## disassembly

```asm
0x1400a4490  push    rbx
0x1400a4492  push    rbp
0x1400a4493  push    rsi
0x1400a4494  push    rdi
0x1400a4495  push    r12
0x1400a4497  push    r13
0x1400a4499  push    r14
0x1400a449b  push    r15
0x1400a449d  sub     rsp, 68h
0x1400a44a1  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a44a8  xor     r13d, r13d
0x1400a44ab  mov     rdi, [r8]
0x1400a44ae  mov     rbx, r8
0x1400a44b1  mov     r12, rdx
0x1400a44b4  mov     rsi, rcx
0x1400a44b7  cmp     [rax], r13b
0x1400a44ba  jz      short loc_1400A44E1
0x1400a44bc  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a44c3  nop     dword ptr [rax+rax+00h]
0x1400a44c8  mov     [rax+18h], rdi
0x1400a44cc  movsxd  r9, dword ptr [rdi+0BCh]
0x1400a44d3  mov     [rax+20h], r9
0x1400a44d7  mov     cs:WdLogGlobalForLineNumber, 0D0h
0x1400a44e1  mov     rcx, [rsi+8]; this
0x1400a44e5  mov     ebp, 1
0x1400a44ea  mov     r8b, bpl; unsigned __int8
0x1400a44ed  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a44f0  call    ?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z; VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)
0x1400a44f5  mov     rcx, [rsi+8]; this
0x1400a44f9  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400a44fe  test    al, al
0x1400a4500  jz      short loc_1400A4528
0x1400a4502  mov     rdx, rdi
0x1400a4505  lea     ecx, [rbp+3]
0x1400a4508  call    cs:__imp_WdLogSingleEntry1
0x1400a450f  nop     dword ptr [rax+rax+00h]
0x1400a4514  mov     eax, 0C00002B6h
0x1400a4519  mov     cs:WdLogGlobalForLineNumber, 0F7h
0x1400a4523  jmp     loc_1400A468C
0x1400a4528  mov     eax, [rdi+20h]
0x1400a452b  test    al, 2
0x1400a452d  jz      short loc_1400A4537
0x1400a452f  mov     r14b, r13b
0x1400a4532  mov     r15b, bpl
0x1400a4535  jmp     short loc_1400A4557
0x1400a4537  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a453a  mov     rcx, rsi; this
0x1400a453d  call    ?LockAllocationBackingStore@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::LockAllocationBackingStore(VIDMM_GLOBAL_ALLOC *)
0x1400a4542  mov     ebp, eax
0x1400a4544  test    eax, eax
0x1400a4546  js      loc_1400A468A
0x1400a454c  mov     ebp, 1
0x1400a4551  mov     r15b, r13b
0x1400a4554  mov     r14b, bpl
0x1400a4557  mov     rax, [rdi+180h]
0x1400a455e  mov     ecx, [rax]
0x1400a4560  shr     ecx, 0Eh
0x1400a4563  test    bpl, cl
0x1400a4566  jz      loc_1400A4603
0x1400a456c  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a456f  mov     rcx, rsi; struct VIDMM_SEGMENT *
0x1400a4572  call    ?VidMmiEnsureSystemCommitMdl@@YAJPEAVVIDMM_SEGMENT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VidMmiEnsureSystemCommitMdl(VIDMM_SEGMENT *,VIDMM_GLOBAL_ALLOC *)
0x1400a4577  mov     ebp, eax
0x1400a4579  test    eax, eax
0x1400a457b  js      loc_1400A4676
0x1400a4581  mov     rcx, [rdi+38h]; MemoryDescriptorList
0x1400a4585  mov     ebp, 1
0x1400a458a  test    byte ptr [rcx+0Ah], 5
0x1400a458e  jz      short loc_1400A4596
0x1400a4590  mov     rax, [rcx+18h]
0x1400a4594  jmp     short loc_1400A45B7
0x1400a4596  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x1400a459e  xor     r9d, r9d; RequestedAddress
0x1400a45a1  mov     r8d, ebp; CacheType
0x1400a45a4  mov     [rsp+0A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400a45a9  xor     edx, edx; AccessMode
0x1400a45ab  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400a45b2  nop     dword ptr [rax+rax+00h]
0x1400a45b7  test    rax, rax
0x1400a45ba  jnz     short loc_1400A4603
0x1400a45bc  mov     rdx, rdi
0x1400a45bf  mov     ecx, ebp
0x1400a45c1  call    cs:__imp_WdLogSingleEntry1
0x1400a45c8  nop     dword ptr [rax+rax+00h]
0x1400a45cd  mov     qword ptr [rsp+0A8h+var_70], r13
0x1400a45d2  lea     r9, aFailedToGetSys; "Failed to get system address for histor"...
0x1400a45d9  mov     qword ptr [rsp+0A8h+var_78], r13
0x1400a45de  mov     edx, 40000h
0x1400a45e3  mov     qword ptr [rsp+0A8h+Priority], r13
0x1400a45e8  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a45ed  mov     cs:WdLogGlobalForLineNumber, 12Ah
0x1400a45f7  call    DxgkLogInternalTriageEvent
0x1400a45fc  mov     ebp, 0C0000017h
0x1400a4601  jmp     short loc_1400A4676
0x1400a4603  mov     rax, [rsi+8]
0x1400a4607  cmp     [rax+8DA2h], r13b
0x1400a460e  jz      loc_1400A469E
0x1400a4614  mov     r8, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a4617  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a461a  mov     rcx, rsi; this
0x1400a461d  call    ?MapAllocationToIoMmu@VIDMM_SEGMENT@@IEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::MapAllocationToIoMmu(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400a4622  movsxd  rbp, eax
0x1400a4625  test    eax, eax
0x1400a4627  jns     short loc_1400A469E
0x1400a4629  lock inc cs:dword_140086838
0x1400a4630  mov     r8, rbp
0x1400a4633  mov     rdx, rdi
0x1400a4636  mov     ecx, 6
0x1400a463b  call    cs:__imp_WdLogSingleEntry2
0x1400a4642  nop     dword ptr [rax+rax+00h]
0x1400a4647  mov     qword ptr [rsp+0A8h+var_70], r13
0x1400a464c  lea     r9, aFailedToMapAll; "Failed to map allocation to the IOMMU. "...
0x1400a4653  mov     qword ptr [rsp+0A8h+var_78], r13
0x1400a4658  mov     edx, 40001h
0x1400a465d  mov     qword ptr [rsp+0A8h+Priority], rbp
0x1400a4662  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a4667  mov     cs:WdLogGlobalForLineNumber, 13Bh
0x1400a4671  call    DxgkLogInternalTriageEvent
0x1400a4676  test    r14b, r14b
0x1400a4679  jz      short loc_1400A468A
0x1400a467b  mov     rcx, [rsi+8]; this
0x1400a467f  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC *
0x1400a4682  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a4685  call    ?UnlockAllocationBackingStore@VIDMM_SEGMENT@@SAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_SEGMENT::UnlockAllocationBackingStore(VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x1400a468a  mov     eax, ebp
0x1400a468c  add     rsp, 68h
0x1400a4690  pop     r15
0x1400a4692  pop     r14
0x1400a4694  pop     r13
0x1400a4696  pop     r12
0x1400a4698  pop     rdi
0x1400a4699  pop     rsi
0x1400a469a  pop     rbp
0x1400a469b  pop     rbx
0x1400a469c  retn
0x1400a469e  mov     rdx, rbx; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a46a1  mov     rcx, rsi; this
0x1400a46a4  call    ?FlushPendingCPUAccess@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z; VIDMM_SEGMENT::FlushPendingCPUAccess(VIDMM_PHYSICAL_ALLOC_LEGACY *)
0x1400a46a9  test    cs:byte_140086201, 10h
0x1400a46b0  mov     r14d, 1
0x1400a46b6  jz      short loc_1400A46E0
0x1400a46b8  movzx   eax, word ptr [rsi+46h]
0x1400a46bc  lea     rdx, EventPagingOpSysmemCommit
0x1400a46c3  mov     r9, [rsi+8]
0x1400a46c7  add     ax, r14w
0x1400a46cb  movzx   ecx, ax
0x1400a46ce  mov     [rsp+0A8h+Priority], ecx
0x1400a46d2  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a46d7  mov     r9, [r9+18h]
0x1400a46db  call    McTemplateK0ppq_EtwWriteTransfer
0x1400a46e0  mov     rax, [rbx+78h]
0x1400a46e4  mov     [rbx+88h], rax
0x1400a46eb  mov     rax, [rbx+70h]
0x1400a46ef  mov     [rbx+90h], rax
0x1400a46f6  mov     [rbx+78h], r13
0x1400a46fa  mov     [rbx+70h], r13
0x1400a46fe  mov     rax, [rdi+180h]
0x1400a4705  and     dword ptr [rdi+20h], 0FFFFFFF7h
0x1400a4709  test    dword ptr [rax], 10000h
0x1400a470f  jz      loc_1400A47F0
0x1400a4715  mov     ecx, cs:Feature_NotifyResidency2__private_featureState
0x1400a471b  mov     [rsp+0A8h+arg_0], r13
0x1400a4723  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x1400a472a  test    cl, 10h
0x1400a472d  jnz     short loc_1400A477B
0x1400a472f  mov     rax, [rsp+0A8h+arg_0]
0x1400a4737  or      ecx, r14d
0x1400a473a  mov     [rsp+0A8h+arg_0], rax
0x1400a4742  mov     ebp, 3
0x1400a4747  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x1400a474e  mov     r8d, ebp
0x1400a4751  mov     rdx, [rsp+0A8h+arg_0]
0x1400a4759  lea     rcx, Feature_NotifyResidency2__private_descriptor
0x1400a4760  call    wil_details_FeatureReporting_ReportUsageToService
0x1400a4765  mov     rcx, [rsp+0A8h+arg_0]
0x1400a476d  lea     r8, Feature_NotifyResidency2__private_descriptor
0x1400a4774  mov     edx, ebp
0x1400a4776  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400a477b  mov     rbp, [rsi+8]
0x1400a477f  mov     rax, [rbp+18h]
0x1400a4783  cmp     [rax+6F0h], r13
0x1400a478a  jz      short loc_1400A47F0
0x1400a478c  mov     rcx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a478f  call    ?VidMmGetFullPfnArray@@YAPEB_KPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetFullPfnArray(VIDMM_GLOBAL_ALLOC const *)
0x1400a4794  mov     r9, [rbx+10h]
0x1400a4798  mov     edx, r13d
0x1400a479b  movzx   r8d, word ptr [rsi+46h]
0x1400a47a0  mov     rcx, rbp; this
0x1400a47a3  mov     r10, [rbx+90h]
0x1400a47aa  mov     [rsp+0A8h+var_58], rax; unsigned __int64 *
0x1400a47af  shr     r10, 0Ch
0x1400a47b3  mov     [rsp+0A8h+var_60], r10; unsigned __int64
0x1400a47b8  test    r9, 0FFFh
0x1400a47bf  mov     [rsp+0A8h+var_68], r8d; unsigned int
0x1400a47c4  mov     r8, [rsi+10h]; struct VIDMM_PHYSICAL_ADAPTER *
0x1400a47c8  setnz   dl
0x1400a47cb  shr     r9, 0Ch
0x1400a47cf  add     edx, r9d
0x1400a47d2  mov     r9, rbx; struct VIDMM_PHYSICAL_ALLOC *
0x1400a47d5  mov     [rsp+0A8h+var_70], edx; unsigned int
0x1400a47d9  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a47dc  mov     [rsp+0A8h+var_78], r13d; unsigned int
0x1400a47e1  mov     byte ptr [rsp+0A8h+Priority], r14b; bool
0x1400a47e6  mov     byte ptr [rsp+0A8h+BugCheckOnFailure], r14b; bool
0x1400a47eb  call    ?NotifyResidency2@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@_N3III_KPEB_K@Z; VIDMM_GLOBAL::NotifyResidency2(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,bool,bool,uint,uint,uint,unsigned __int64,unsigned __int64 const *)
0x1400a47f0  test    r15b, r15b
0x1400a47f3  jz      short loc_1400A4806
0x1400a47f5  mov     rdx, [rbx+10h]; unsigned __int64
0x1400a47f9  mov     rcx, [rsi+8]; this
0x1400a47fd  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x1400a4802  and     dword ptr [rdi+20h], 0FFFFFFFDh
0x1400a4806  xor     eax, eax
0x1400a4808  jmp     loc_1400A468C
```
