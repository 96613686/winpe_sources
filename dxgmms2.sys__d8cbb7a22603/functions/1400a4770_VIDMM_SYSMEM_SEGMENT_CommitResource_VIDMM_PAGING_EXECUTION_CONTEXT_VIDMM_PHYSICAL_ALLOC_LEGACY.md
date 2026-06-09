# VIDMM_SYSMEM_SEGMENT::CommitResource(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *)

- ea: `0x1400a4770`
- end: `0x1400a4aed`
- name: `?CommitResource@VIDMM_SYSMEM_SEGMENT@@UEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z`
- size: `893`
- prototype: `__int64 __fastcall(VIDMM_SYSMEM_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140004268`
- `0x1400333c8`
- `0x140034d6c`
- `0x140048084`
- `0x140048308`
- `0x1400a302c`
- `0x1400a4770`
- `0x1400d5098`
- `0x1400ef500`
- `0x14010d018`
- `0x14010d9c0`
- `0x14010e858`
- `0x140110658`
- `0x1401114dc`
- `0x140118954`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a488b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a488b`
- `watchdog!WdLogSingleEntry2` at `0x1400a491b`
- `watchdog!WdLogSingleEntry2` at `0x1400a491b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a479c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a479c`
- `watchdog!WdLogSingleEntry1` at `0x1400a47e8`
- `watchdog!WdLogSingleEntry1` at `0x1400a48a1`
- `watchdog!WdLogSingleEntry1` at `0x1400a47e8`
- `watchdog!WdLogSingleEntry1` at `0x1400a48a1`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a4781`

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
    v7 = WdLogNewEntry5_WdTrace(this);
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
  if ( (**(_DWORD **)(v3 + 392) & 0x4000) != 0 )
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
      _InterlockedIncrement(&dword_140087818);
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
  if ( (byte_140087201 & 0x10) != 0 )
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
  v20 = *(_DWORD **)(v3 + 392);
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
0x1400a4770  push    rbx
0x1400a4772  push    rbp
0x1400a4773  push    rsi
0x1400a4774  push    rdi
0x1400a4775  push    r12
0x1400a4777  push    r13
0x1400a4779  push    r14
0x1400a477b  push    r15
0x1400a477d  sub     rsp, 68h
0x1400a4781  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a4788  xor     r13d, r13d
0x1400a478b  mov     rdi, [r8]
0x1400a478e  mov     rbx, r8
0x1400a4791  mov     r12, rdx
0x1400a4794  mov     rsi, rcx
0x1400a4797  cmp     [rax], r13b
0x1400a479a  jz      short loc_1400A47C1
0x1400a479c  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a47a3  nop     dword ptr [rax+rax+00h]
0x1400a47a8  mov     [rax+18h], rdi
0x1400a47ac  movsxd  r9, dword ptr [rdi+0BCh]
0x1400a47b3  mov     [rax+20h], r9
0x1400a47b7  mov     cs:WdLogGlobalForLineNumber, 0D0h
0x1400a47c1  mov     rcx, [rsi+8]; this
0x1400a47c5  mov     ebp, 1
0x1400a47ca  mov     r8b, bpl; unsigned __int8
0x1400a47cd  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a47d0  call    ?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z; VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)
0x1400a47d5  mov     rcx, [rsi+8]; this
0x1400a47d9  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400a47de  test    al, al
0x1400a47e0  jz      short loc_1400A4808
0x1400a47e2  mov     rdx, rdi
0x1400a47e5  lea     ecx, [rbp+3]
0x1400a47e8  call    cs:__imp_WdLogSingleEntry1
0x1400a47ef  nop     dword ptr [rax+rax+00h]
0x1400a47f4  mov     eax, 0C00002B6h
0x1400a47f9  mov     cs:WdLogGlobalForLineNumber, 0F7h
0x1400a4803  jmp     loc_1400A496C
0x1400a4808  mov     eax, [rdi+20h]
0x1400a480b  test    al, 2
0x1400a480d  jz      short loc_1400A4817
0x1400a480f  mov     r14b, r13b
0x1400a4812  mov     r15b, bpl
0x1400a4815  jmp     short loc_1400A4837
0x1400a4817  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a481a  mov     rcx, rsi; this
0x1400a481d  call    ?LockAllocationBackingStore@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::LockAllocationBackingStore(VIDMM_GLOBAL_ALLOC *)
0x1400a4822  mov     ebp, eax
0x1400a4824  test    eax, eax
0x1400a4826  js      loc_1400A496A
0x1400a482c  mov     ebp, 1
0x1400a4831  mov     r15b, r13b
0x1400a4834  mov     r14b, bpl
0x1400a4837  mov     rax, [rdi+188h]
0x1400a483e  mov     ecx, [rax]
0x1400a4840  shr     ecx, 0Eh
0x1400a4843  test    bpl, cl
0x1400a4846  jz      loc_1400A48E3
0x1400a484c  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a484f  mov     rcx, rsi; struct VIDMM_SEGMENT *
0x1400a4852  call    ?VidMmiEnsureSystemCommitMdl@@YAJPEAVVIDMM_SEGMENT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VidMmiEnsureSystemCommitMdl(VIDMM_SEGMENT *,VIDMM_GLOBAL_ALLOC *)
0x1400a4857  mov     ebp, eax
0x1400a4859  test    eax, eax
0x1400a485b  js      loc_1400A4956
0x1400a4861  mov     rcx, [rdi+38h]; MemoryDescriptorList
0x1400a4865  mov     ebp, 1
0x1400a486a  test    byte ptr [rcx+0Ah], 5
0x1400a486e  jz      short loc_1400A4876
0x1400a4870  mov     rax, [rcx+18h]
0x1400a4874  jmp     short loc_1400A4897
0x1400a4876  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x1400a487e  xor     r9d, r9d; RequestedAddress
0x1400a4881  mov     r8d, ebp; CacheType
0x1400a4884  mov     [rsp+0A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400a4889  xor     edx, edx; AccessMode
0x1400a488b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400a4892  nop     dword ptr [rax+rax+00h]
0x1400a4897  test    rax, rax
0x1400a489a  jnz     short loc_1400A48E3
0x1400a489c  mov     rdx, rdi
0x1400a489f  mov     ecx, ebp
0x1400a48a1  call    cs:__imp_WdLogSingleEntry1
0x1400a48a8  nop     dword ptr [rax+rax+00h]
0x1400a48ad  mov     qword ptr [rsp+0A8h+var_70], r13
0x1400a48b2  lea     r9, aFailedToGetSys; "Failed to get system address for histor"...
0x1400a48b9  mov     qword ptr [rsp+0A8h+var_78], r13
0x1400a48be  mov     edx, 40000h
0x1400a48c3  mov     qword ptr [rsp+0A8h+Priority], r13
0x1400a48c8  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a48cd  mov     cs:WdLogGlobalForLineNumber, 12Ah
0x1400a48d7  call    DxgkLogInternalTriageEvent
0x1400a48dc  mov     ebp, 0C0000017h
0x1400a48e1  jmp     short loc_1400A4956
0x1400a48e3  mov     rax, [rsi+8]
0x1400a48e7  cmp     [rax+8DA2h], r13b
0x1400a48ee  jz      loc_1400A497E
0x1400a48f4  mov     r8, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a48f7  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a48fa  mov     rcx, rsi; this
0x1400a48fd  call    ?MapAllocationToIoMmu@VIDMM_SEGMENT@@IEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::MapAllocationToIoMmu(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400a4902  movsxd  rbp, eax
0x1400a4905  test    eax, eax
0x1400a4907  jns     short loc_1400A497E
0x1400a4909  lock inc cs:dword_140087818
0x1400a4910  mov     r8, rbp
0x1400a4913  mov     rdx, rdi
0x1400a4916  mov     ecx, 6
0x1400a491b  call    cs:__imp_WdLogSingleEntry2
0x1400a4922  nop     dword ptr [rax+rax+00h]
0x1400a4927  mov     qword ptr [rsp+0A8h+var_70], r13
0x1400a492c  lea     r9, aFailedToMapAll; "Failed to map allocation to the IOMMU. "...
0x1400a4933  mov     qword ptr [rsp+0A8h+var_78], r13
0x1400a4938  mov     edx, 40001h
0x1400a493d  mov     qword ptr [rsp+0A8h+Priority], rbp
0x1400a4942  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a4947  mov     cs:WdLogGlobalForLineNumber, 13Bh
0x1400a4951  call    DxgkLogInternalTriageEvent
0x1400a4956  test    r14b, r14b
0x1400a4959  jz      short loc_1400A496A
0x1400a495b  mov     rcx, [rsi+8]; this
0x1400a495f  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC *
0x1400a4962  mov     rdx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a4965  call    ?UnlockAllocationBackingStore@VIDMM_SEGMENT@@SAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_SEGMENT::UnlockAllocationBackingStore(VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x1400a496a  mov     eax, ebp
0x1400a496c  add     rsp, 68h
0x1400a4970  pop     r15
0x1400a4972  pop     r14
0x1400a4974  pop     r13
0x1400a4976  pop     r12
0x1400a4978  pop     rdi
0x1400a4979  pop     rsi
0x1400a497a  pop     rbp
0x1400a497b  pop     rbx
0x1400a497c  retn
0x1400a497e  mov     rdx, rbx; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a4981  mov     rcx, rsi; this
0x1400a4984  call    ?FlushPendingCPUAccess@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z; VIDMM_SEGMENT::FlushPendingCPUAccess(VIDMM_PHYSICAL_ALLOC_LEGACY *)
0x1400a4989  test    cs:byte_140087201, 10h
0x1400a4990  mov     r14d, 1
0x1400a4996  jz      short loc_1400A49C0
0x1400a4998  movzx   eax, word ptr [rsi+46h]
0x1400a499c  lea     rdx, EventPagingOpSysmemCommit
0x1400a49a3  mov     r9, [rsi+8]
0x1400a49a7  add     ax, r14w
0x1400a49ab  movzx   ecx, ax
0x1400a49ae  mov     [rsp+0A8h+Priority], ecx
0x1400a49b2  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rdi
0x1400a49b7  mov     r9, [r9+18h]
0x1400a49bb  call    McTemplateK0ppq_EtwWriteTransfer
0x1400a49c0  mov     rax, [rbx+78h]
0x1400a49c4  mov     [rbx+88h], rax
0x1400a49cb  mov     rax, [rbx+70h]
0x1400a49cf  mov     [rbx+90h], rax
0x1400a49d6  mov     [rbx+78h], r13
0x1400a49da  mov     [rbx+70h], r13
0x1400a49de  mov     rax, [rdi+188h]
0x1400a49e5  and     dword ptr [rdi+20h], 0FFFFFFF7h
0x1400a49e9  test    dword ptr [rax], 10000h
0x1400a49ef  jz      loc_1400A4AD0
0x1400a49f5  mov     ecx, cs:Feature_NotifyResidency2__private_featureState
0x1400a49fb  mov     [rsp+0A8h+arg_0], r13
0x1400a4a03  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x1400a4a0a  test    cl, 10h
0x1400a4a0d  jnz     short loc_1400A4A5B
0x1400a4a0f  mov     rax, [rsp+0A8h+arg_0]
0x1400a4a17  or      ecx, r14d
0x1400a4a1a  mov     [rsp+0A8h+arg_0], rax
0x1400a4a22  mov     ebp, 3
0x1400a4a27  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x1400a4a2e  mov     r8d, ebp
0x1400a4a31  mov     rdx, [rsp+0A8h+arg_0]
0x1400a4a39  lea     rcx, Feature_NotifyResidency2__private_descriptor
0x1400a4a40  call    wil_details_FeatureReporting_ReportUsageToService
0x1400a4a45  mov     rcx, [rsp+0A8h+arg_0]
0x1400a4a4d  lea     r8, Feature_NotifyResidency2__private_descriptor
0x1400a4a54  mov     edx, ebp
0x1400a4a56  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400a4a5b  mov     rbp, [rsi+8]
0x1400a4a5f  mov     rax, [rbp+18h]
0x1400a4a63  cmp     [rax+6F0h], r13
0x1400a4a6a  jz      short loc_1400A4AD0
0x1400a4a6c  mov     rcx, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400a4a6f  call    ?VidMmGetFullPfnArray@@YAPEB_KPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetFullPfnArray(VIDMM_GLOBAL_ALLOC const *)
0x1400a4a74  mov     r9, [rbx+10h]
0x1400a4a78  mov     edx, r13d
0x1400a4a7b  movzx   r8d, word ptr [rsi+46h]
0x1400a4a80  mov     rcx, rbp; this
0x1400a4a83  mov     r10, [rbx+90h]
0x1400a4a8a  mov     [rsp+0A8h+var_58], rax; unsigned __int64 *
0x1400a4a8f  shr     r10, 0Ch
0x1400a4a93  mov     [rsp+0A8h+var_60], r10; unsigned __int64
0x1400a4a98  test    r9, 0FFFh
0x1400a4a9f  mov     [rsp+0A8h+var_68], r8d; unsigned int
0x1400a4aa4  mov     r8, [rsi+10h]; struct VIDMM_PHYSICAL_ADAPTER *
0x1400a4aa8  setnz   dl
0x1400a4aab  shr     r9, 0Ch
0x1400a4aaf  add     edx, r9d
0x1400a4ab2  mov     r9, rbx; struct VIDMM_PHYSICAL_ALLOC *
0x1400a4ab5  mov     [rsp+0A8h+var_70], edx; unsigned int
0x1400a4ab9  mov     rdx, r12; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a4abc  mov     [rsp+0A8h+var_78], r13d; unsigned int
0x1400a4ac1  mov     byte ptr [rsp+0A8h+Priority], r14b; bool
0x1400a4ac6  mov     byte ptr [rsp+0A8h+BugCheckOnFailure], r14b; bool
0x1400a4acb  call    ?NotifyResidency2@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@_N3III_KPEB_K@Z; VIDMM_GLOBAL::NotifyResidency2(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,bool,bool,uint,uint,uint,unsigned __int64,unsigned __int64 const *)
0x1400a4ad0  test    r15b, r15b
0x1400a4ad3  jz      short loc_1400A4AE6
0x1400a4ad5  mov     rdx, [rbx+10h]; unsigned __int64
0x1400a4ad9  mov     rcx, [rsi+8]; this
0x1400a4add  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x1400a4ae2  and     dword ptr [rdi+20h], 0FFFFFFFDh
0x1400a4ae6  xor     eax, eax
0x1400a4ae8  jmp     loc_1400A496C
```
