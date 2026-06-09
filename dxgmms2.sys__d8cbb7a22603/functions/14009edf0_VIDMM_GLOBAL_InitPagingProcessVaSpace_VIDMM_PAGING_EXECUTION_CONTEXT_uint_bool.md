# VIDMM_GLOBAL::InitPagingProcessVaSpace(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,bool)

- ea: `0x14009edf0`
- end: `0x14009fcec`
- name: `?InitPagingProcessVaSpace@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_N@Z`
- size: `3836`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, unsigned int, bool)`
- caller_count: `6`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14004792c`
- `0x1400bea60`
- `0x1400d80f0`
- `0x1400d8590`
- `0x1400e7e60`
- `0x140126e2c`

## callees

- `0x140004268`
- `0x140008c50`
- `0x14002f6a8`
- `0x140030bac`
- `0x1400333c8`
- `0x1400399b4`
- `0x14003e238`
- `0x140048084`
- `0x140048308`
- `0x140059030`
- `0x140059380`
- `0x14009d454`
- `0x14009d74c`
- `0x14009ed5c`
- `0x14009edf0`
- `0x14009ff34`
- `0x1400a8e98`
- `0x1400abf54`
- `0x1400c2168`
- `0x1400c37cc`
- `0x1400c6e30`
- `0x1400c7210`
- `0x1400d84e4`
- `0x1400e2e0c`
- `0x1400e827c`
- `0x1400ffd4c`
- `0x140101b98`
- `0x140112130`
- `0x140116794`
- `0x140123b30`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009f290`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009f55d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009f290`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009f55d`
- `watchdog!WdLogSingleEntry2` at `0x14009f694`
- `watchdog!WdLogSingleEntry2` at `0x14009f784`
- `watchdog!WdLogSingleEntry2` at `0x14009fa7b`
- `watchdog!WdLogSingleEntry2` at `0x14009facc`
- `watchdog!WdLogSingleEntry2` at `0x14009fb53`
- `watchdog!WdLogSingleEntry2` at `0x14009f694`
- `watchdog!WdLogSingleEntry2` at `0x14009f784`
- `watchdog!WdLogSingleEntry2` at `0x14009fa7b`
- `watchdog!WdLogSingleEntry2` at `0x14009facc`
- `watchdog!WdLogSingleEntry2` at `0x14009fb53`
- `watchdog!WdLogSingleEntry0` at `0x14009f869`
- `watchdog!WdLogSingleEntry0` at `0x14009f869`
- `watchdog!WdLogSingleEntry1` at `0x14009ef56`
- `watchdog!WdLogSingleEntry1` at `0x14009f007`
- `watchdog!WdLogSingleEntry1` at `0x14009f1c8`
- `watchdog!WdLogSingleEntry1` at `0x14009f247`
- `watchdog!WdLogSingleEntry1` at `0x14009f306`
- `watchdog!WdLogSingleEntry1` at `0x14009f39b`
- `watchdog!WdLogSingleEntry1` at `0x14009f7d4`
- `watchdog!WdLogSingleEntry1` at `0x14009ef56`
- `watchdog!WdLogSingleEntry1` at `0x14009f007`
- `watchdog!WdLogSingleEntry1` at `0x14009f1c8`
- `watchdog!WdLogSingleEntry1` at `0x14009f247`
- `watchdog!WdLogSingleEntry1` at `0x14009f306`
- `watchdog!WdLogSingleEntry1` at `0x14009f39b`
- `watchdog!WdLogSingleEntry1` at `0x14009f7d4`

## string_xrefs

- `0x14009f87a`: `Failed to allocate temporary VIDMM_MAPPED_VA_RANGE`
- `0x14009ef68`: `Invalid _Config.PagingProcessVaSpaceBitCount`
- `0x14009f6b1`: `Failed to commit VA space for the paging process. pVaAllocator=0x%p, pFailedAlloc=0x%p`
- `0x14009fadc`: `Failed to commit virtual address range for paging buffer. pVaAllocator=0x%p, pFailedAlloc=0x%p`
- `0x14009fb65`: `Failed to recommit virtual address range for scheduling logs, ADAPTER_RENDER=0x%p, PhysicalAdapterIndex=%u`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::InitPagingProcessVaSpace(
        VIDMM_GLOBAL *this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        unsigned int a3,
        bool a4)
{
  __int64 v7; // r12
  unsigned __int64 v8; // r13
  DXGADAPTER *v9; // rcx
  char v10; // cl
  int v11; // r8d
  __int64 result; // rax
  int inited; // eax
  unsigned int v14; // esi
  __int64 v15; // rdi
  int v16; // ecx
  int v17; // r8d
  int HwQueue; // edi
  __int64 v19; // r14
  __int64 v20; // rax
  bool v21; // zf
  CVirtualAddressAllocator *v22; // r15
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r10
  __int64 v26; // rcx
  __int64 v27; // rdi
  unsigned __int64 v28; // rdx
  __int64 v29; // rdi
  unsigned __int64 v30; // rdi
  __int64 v31; // rax
  unsigned __int64 v32; // r14
  int v33; // ecx
  int v34; // r8d
  int v35; // r13d
  __int64 v36; // rdi
  int v37; // ecx
  int v38; // r8d
  PVOID v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  int v42; // ecx
  int v43; // r8d
  unsigned __int64 *v44; // r13
  int v45; // ecx
  int v46; // r8d
  unsigned __int64 v47; // rcx
  unsigned __int64 v48; // rdi
  unsigned int v49; // eax
  __int64 *v50; // r9
  __int64 v51; // rdx
  _QWORD *v52; // r13
  PVOID v53; // r10
  __int64 v54; // rdx
  __int64 v55; // r9
  __int64 v56; // rcx
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v57; // r14
  int v58; // ecx
  int v59; // r8d
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  int v63; // ecx
  int v64; // r8d
  unsigned int v65; // r8d
  unsigned __int64 v66; // r9
  int v67; // ecx
  _QWORD *v68; // rax
  _QWORD *v69; // rdx
  int v70; // ecx
  int v71; // r8d
  unsigned __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rcx
  unsigned __int64 LogicalAddress; // rdi
  const struct VIDMM_GLOBAL_ALLOC *v76; // rcx
  const unsigned __int64 *FullPfnArray; // r14
  __int64 v78; // rcx
  __int64 v79; // r14
  int v80; // ecx
  int v81; // r8d
  int v82; // ecx
  int v83; // r8d
  int v84; // ecx
  int v85; // r8d
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v86; // rbx
  int v87; // eax
  __int64 v88; // [rsp+50h] [rbp-B0h]
  int v89; // [rsp+68h] [rbp-98h]
  int v90; // [rsp+70h] [rbp-90h]
  bool v91; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v92[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v93[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v94; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v95; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v96; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v97[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v98; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v99; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v100; // [rsp+100h] [rbp+0h]
  _QWORD *v101; // [rsp+108h] [rbp+8h]
  _QWORD v102[20]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v103; // [rsp+1C0h] [rbp+C0h] BYREF
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v104; // [rsp+1C8h] [rbp+C8h]
  unsigned int v105; // [rsp+1D0h] [rbp+D0h] BYREF
  bool v106; // [rsp+1D8h] [rbp+D8h]

  v106 = a4;
  v105 = a3;
  v104 = a2;
  v7 = *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * a3);
  v8 = 0;
  v95 = 0;
  v103 = (unsigned int)Feature_NotifyResidency2__private_featureState;
  if ( (Feature_NotifyResidency2__private_featureState & 0x10) == 0 )
  {
    LODWORD(v103) = Feature_NotifyResidency2__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(Feature_NotifyResidency2__private_descriptor, v103, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v103, 3, Feature_NotifyResidency2__private_descriptor);
  }
  v9 = (DXGADAPTER *)*((_QWORD *)this + 3);
  *(_QWORD *)&v97[36] = 0;
  *(_DWORD *)&v97[44] = 0;
  *(_QWORD *)&v97[8] = &v105;
  *(_QWORD *)&v97[24] = &v95;
  *(_QWORD *)v97 = 48;
  *(_QWORD *)&v97[16] = 4;
  *(_DWORD *)&v97[32] = 4;
  if ( (int)DXGADAPTER::DdiQueryAdapterInfo(v9, (struct _DXGKARG_QUERYADAPTERINFO *)v97) >= 0 )
    v8 = (unsigned __int64)v95 << 20;
  v10 = *(_BYTE *)(v7 + 1348);
  if ( v10 >= 0 || (*(_BYTE *)(v7 + 1349) & 1) == 0 )
  {
    if ( *(_BYTE *)(*((_QWORD *)this + 3) + 3167LL) && (v10 & 4) != 0 )
      goto LABEL_13;
    if ( *(_DWORD *)(v7 + 1336) != 1 && !v8 && !*(_BYTE *)(*((_QWORD *)this + 2) + 1880LL) )
      return 0;
  }
  if ( (v10 & 4) == 0 )
    goto LABEL_17;
LABEL_13:
  if ( (*(_BYTE *)(v7 + 1349) & 4) == 0 )
    return 0;
  if ( (unsigned int)(dword_140087498 - 1) > 0x3D )
  {
    WdLogSingleEntry1(1, (unsigned int)dword_140087498);
    WdLogGlobalForLineNumber = 10633;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      v11,
      (unsigned int)L"Invalid _Config.PagingProcessVaSpaceBitCount",
      (unsigned int)dword_140087498,
      0,
      0,
      0);
    return 3221225485LL;
  }
LABEL_17:
  if ( !a2 )
  {
    if ( (*((_BYTE *)this + 37225) & 0x10) != 0 )
    {
      inited = VidMmQueueInitPagingProcessWorkItemAndWait(*(struct VIDMM_WORKER_THREAD2 **)this, v105, a4);
    }
    else
    {
      memset(&v102[1], 0, 0x50u);
      HIDWORD(v102[0]) = v105;
      LODWORD(v102[0]) = 118;
      inited = VIDMM_GLOBAL::QueueSystemCommandAndWait(this, (struct VIDMM_SYSTEM_COMMAND *)v102, 1);
    }
    v14 = inited;
    if ( inited < 0 )
    {
      v15 = inited;
      WdLogSingleEntry1(1, inited);
      WdLogGlobalForLineNumber = 10661;
      DxgkLogInternalTriageEvent(
        v16,
        0x40000,
        v17,
        (unsigned int)L"Failed to initialize paging process VA space. Status=0x%.8x",
        v15,
        0,
        0,
        0);
      return v14;
    }
    return 0;
  }
  HwQueue = 0;
  v19 = v105;
  v20 = *(_QWORD *)(*((_QWORD *)a2 + 3) + 8LL * v105);
  *((_BYTE *)this + 37229) = 1;
  v21 = (*(_BYTE *)(v7 + 1348) & 4) == 0;
  v22 = (CVirtualAddressAllocator *)*((_QWORD *)this + v19 + 4588);
  v100 = v20;
  v23 = *(_QWORD *)(*((_QWORD *)this + 2) + 744LL);
  v96 = v23;
  if ( !v21 )
  {
    if ( v106 )
    {
      CVirtualAddressAllocator::EvictRootPageTable(v22, v104, v19, 0);
      LODWORD(v19) = v105;
    }
    if ( !*((_QWORD *)this + 4656) )
    {
      v94 = 0;
      LOBYTE(v103) = 0;
      v91 = 0;
      v92[0] = 0;
      v93[0] = 0;
      VIDMM_GLOBAL::QueryPagingProcessInfo(this, &v94, (bool *)&v103, &v91, v92, v93);
      v25 = 0;
      if ( v92[0] )
      {
        v30 = (unsigned __int64)v92[0] << 20;
      }
      else
      {
        v26 = *((_QWORD *)this + 2);
        v27 = 0x800000;
        if ( *(_BYTE *)(v26 + 1880) )
        {
          v27 = (unsigned int)VidSchGetSchedulingLogSize(*(_QWORD *)(v26 + 744)) + 0x800000LL;
          v25 = 0;
        }
        if ( v91 )
          v27 += v93[0];
        v28 = v27 + (v94 >> 2);
        v29 = 1LL << dword_140087498;
        if ( v28 < 1LL << dword_140087498 )
          v29 = v28;
        v30 = (v29 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL;
      }
      if ( (_BYTE)v103 )
      {
        v31 = (*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * (unsigned int)v19) + 1088LL) << 12) - 1LL;
        v30 = ~v31 & (v31 + v30);
        v32 = 2 * v30;
      }
      else
      {
        v32 = v30;
      }
      if ( v8 )
        v32 = v8;
      if ( v32 > *((_QWORD *)v22 + 2) )
      {
        *((_BYTE *)this + 37229) = 0;
        WdLogSingleEntry1(1, v32);
        WdLogGlobalForLineNumber = 10779;
        DxgkLogInternalTriageEvent(
          v33,
          0x40000,
          v34,
          (unsigned int)L"The paging process virtual address space size is too big: 0x%I64x",
          v32,
          0,
          0,
          0);
        return 3221225485LL;
      }
      *((_QWORD *)this + 4659) = v32;
      if ( v91 )
      {
        v94 = 0;
        v35 = CVirtualAddressAllocator::ReserveVirtualAddressRangeNoAccess(v22, v93[0], v24, 0, 0, 0x1000u, &v94);
        if ( v35 < 0 )
        {
          v36 = v93[0];
          WdLogSingleEntry1(1, v93[0]);
          WdLogGlobalForLineNumber = 10805;
          DxgkLogInternalTriageEvent(
            v37,
            0x40000,
            v38,
            (unsigned int)L"Failed to reserve a range for updating page tables: 0x%I64x",
            v36,
            0,
            0,
            0);
LABEL_54:
          *((_BYTE *)this + 37229) = 0;
          return (unsigned int)v35;
        }
        v39 = ExAllocateFromLookasideListEx(&g_VaRangeLookasideList);
        v25 = 0;
        if ( v39 )
          v41 = VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(v39, v40, 0, v94, v94 + v93[0], 0, 0, 0, 0, 1, 0, 0, 0, 0);
        else
          v41 = 0;
        *((_QWORD *)this + 4661) = v41;
        if ( !v41 )
        {
          WdLogSingleEntry1(1, *(unsigned int *)(v7 + 2512));
          WdLogGlobalForLineNumber = 10833;
          DxgkLogInternalTriageEvent(
            v42,
            0x40000,
            v43,
            (unsigned int)L"Failed to reserve a range for updating page tables: 0x%I64x",
            *(unsigned int *)(v7 + 2512),
            0,
            0,
            0);
          v35 = -1073741823;
          goto LABEL_54;
        }
      }
      v44 = (unsigned __int64 *)((char *)this + 37240);
      v92[0] = CVirtualAddressAllocator::ReserveVirtualAddressRangeNoAccess(
                 v22,
                 v32,
                 v24,
                 0,
                 v25,
                 (_BYTE)v103 != 0 ? 0x10000 : 4096,
                 (unsigned __int64 *)this + 4655);
      if ( (v92[0] & 0x80000000) != 0 )
      {
        WdLogSingleEntry1(1, v32);
        WdLogGlobalForLineNumber = 10855;
        DxgkLogInternalTriageEvent(
          v45,
          0x40000,
          v46,
          (unsigned int)L"Failed to allocate a range for the paging process VA space: 0x%I64x",
          v32,
          0,
          0,
          0);
        v35 = v92[0];
        goto LABEL_54;
      }
      CVirtualAddressAllocator::FreeVirtualAddressRange(v22, *v44);
      v47 = v30 + *v44;
      v21 = (_BYTE)v103 == 0;
      *((_QWORD *)this + 4656) = v47;
      *((_QWORD *)this + 4660) = v47;
      if ( !v21 )
      {
        *((_QWORD *)this + 4657) = v47;
        *((_QWORD *)this + 4658) = v47 + v30;
        *((_QWORD *)this + 4660) = v47 + v30;
      }
      v48 = v30 >> 2;
      if ( v48 > 0xFFFEFFFF )
        LODWORD(v48) = -65537;
      *((_DWORD *)this + 9324) = (v48 + 0xFFFF) & 0xFFFF0000;
    }
    if ( *(_DWORD *)(v7 + 1340) == 1 )
      v49 = ComputeMaxPageTableSizeForPagingProcess((struct VIDMM_PHYSICAL_ADAPTER *)v7, *((_DWORD *)this + 9318));
    else
      v49 = *(_DWORD *)(v7 + 2512);
    *(_DWORD *)(v7 + 2516) = v49;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 336LL))(v7);
    HwQueue = result;
    if ( (int)result < 0 )
    {
      *((_BYTE *)this + 37229) = 0;
      return result;
    }
    LODWORD(v19) = v105;
    v23 = v96;
  }
  if ( *(_BYTE *)(v23 + 63) )
  {
    v50 = (__int64 *)(*(_QWORD *)(v23 + 344) + 8LL * (unsigned int)v19);
    if ( !*v50 )
    {
      v51 = *(_QWORD *)(v23 + 336);
      memset(v97, 0, 48);
      HwQueue = VidSchCreateHwQueue(0, *(_QWORD *)(v51 + 8LL * (unsigned int)v19), (__int64)v97, v50, 0);
      if ( HwQueue < 0 )
        goto LABEL_120;
      VidSchSetHwQueueProgressFenceObject(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 744LL) + 344LL) + 8LL * v105),
        *((_QWORD *)this + v105 + 261),
        0);
      LODWORD(v19) = v105;
    }
  }
  v52 = 0;
  if ( (*(_BYTE *)(v7 + 1348) & 4) != 0 )
  {
    LOBYTE(v103) = *(_BYTE *)(v7 + 1349);
    v53 = ExAllocateFromLookasideListEx(&g_VaRangeLookasideList);
    if ( !v53
      || ((v54 = *((_QWORD *)this + 4661)) == 0 ? (v55 = *((_QWORD *)this + 4655)) : (v55 = *(_QWORD *)(v54 + 104)),
          (v52 = (_QWORD *)VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(
                             v53,
                             v54,
                             0,
                             v55,
                             *((_QWORD *)this + 4656),
                             v105,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0)) == 0) )
    {
      _InterlockedAdd(&dword_1400877D0, 1u);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 10974;
      DxgkLogInternalTriageEvent(
        v70,
        262145,
        v71,
        (unsigned int)L"Failed to allocate temporary VIDMM_MAPPED_VA_RANGE",
        10974,
        0,
        0,
        0);
      goto LABEL_120;
    }
    *(_QWORD *)v93 = 0;
    memset(v102, 0, 0x40u);
    v56 = v52[14] - v52[13];
    v102[0] = v52;
    v102[1] = v52[13];
    v102[2] = v56 + v102[1];
    v102[3] = v56;
    v102[4] = v52[10];
    v88 = *((_QWORD *)this + 4658) >> 12;
    v57 = v104;
    memset(&v102[5], 0, 24);
    HwQueue = CVirtualAddressAllocator::CommitVirtualAddressRange(v22, v104, v52, v102, v105, -1, 0, v93, 0, 0, v88);
    if ( HwQueue < 0 )
    {
      WdLogSingleEntry2(1, v22, *(_QWORD *)v93);
      v60 = *(_QWORD *)v93;
      WdLogGlobalForLineNumber = 11018;
LABEL_78:
      DxgkLogInternalTriageEvent(
        v58,
        0x40000,
        v59,
        (unsigned int)L"Failed to commit VA space for the paging process. pVaAllocator=0x%p, pFailedAlloc=0x%p",
        (__int64)v22,
        v60,
        0,
        0);
LABEL_119:
      VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(v52);
      goto LABEL_120;
    }
    if ( (v103 & 0x40) != 0 )
    {
      v61 = *((_QWORD *)this + 4657);
      v52[13] = v61;
      v62 = *((_QWORD *)this + 4658);
      v52[14] = v62;
      *(_QWORD *)&v97[16] = v62;
      *(_QWORD *)&v97[24] = v62 - v61;
      *(_QWORD *)&v97[32] = v52[10];
      *(_QWORD *)&v97[8] = v61;
      v103 = 0;
      *(_QWORD *)v97 = v52;
      memset(&v97[40], 0, 24);
      HwQueue = CVirtualAddressAllocator::CommitVirtualAddressRange(v22, v57, v52, v97, v105, -3, 0, &v103, 0, 0, 0);
      if ( HwQueue < 0 )
      {
        WdLogSingleEntry2(1, v22, v103);
        v60 = v103;
        WdLogGlobalForLineNumber = 11058;
        goto LABEL_78;
      }
    }
    HwQueue = VIDMM_PAGE_DIRECTORY::MapPageTablesToVaSpace(
                *(VIDMM_PAGE_DIRECTORY **)(32LL * v105 + *((_QWORD *)v22 + 16)),
                v57,
                v22);
    if ( HwQueue < 0 )
    {
      WdLogSingleEntry1(1, v22);
      WdLogGlobalForLineNumber = 11074;
      DxgkLogInternalTriageEvent(
        v63,
        0x40000,
        v64,
        (unsigned int)L"Failed to map page tables to the VA space of the paging process. pVaAllocator=0x%p",
        (__int64)v22,
        0,
        0,
        0);
      goto LABEL_119;
    }
    LODWORD(v19) = v105;
  }
  v65 = 0;
  v66 = (unsigned __int64)*((unsigned int *)this + (unsigned int)v19 + 33) >> 12;
  v99 = v66;
  while ( 1 )
  {
    LODWORD(v103) = v65;
    if ( v65 >= 2 )
      break;
    v67 = 0;
    v68 = (_QWORD *)(*(_QWORD *)(v100 + 8) + 88LL);
    v69 = (_QWORD *)*v68;
    while ( 1 )
    {
      *(_QWORD *)v92 = v69;
      if ( v69 == v68 )
        break;
      if ( v65 == v67 )
        goto LABEL_93;
      v69 = (_QWORD *)*v69;
      ++v67;
    }
    v69 = 0;
    *(_QWORD *)v92 = 0;
LABEL_93:
    v72 = v69[7];
    v98 = v72;
    if ( v72 )
    {
      if ( !v69[11] )
      {
        LOBYTE(v90) = 0;
        LOBYTE(v89) = 0;
        v73 = CVirtualAddressAllocator::MapVirtualAddressRange(
                v22,
                v69,
                0,
                4,
                v66 << 12,
                0,
                *((_QWORD *)this + 4655),
                *((_QWORD *)this + 4656),
                4096,
                (*((_DWORD *)this + 10) < 0x6000u) | 2LL,
                0,
                v19,
                0,
                v89,
                v90);
        if ( !v73 )
        {
          HwQueue = -1073741823;
          v79 = *(_QWORD *)v92;
          WdLogSingleEntry2(1, v22, *(_QWORD *)v92);
          WdLogGlobalForLineNumber = 11145;
          DxgkLogInternalTriageEvent(
            v80,
            0x40000,
            v81,
            (unsigned int)L"Failed to map virtual address for paging buffer. pVaAllocator=0x%p, pDmaBuffer=0x%p",
            (__int64)v22,
            v79,
            0,
            0);
          goto LABEL_118;
        }
        v69 = *(_QWORD **)v92;
        *(_QWORD *)(*(_QWORD *)v92 + 88LL) = *(_QWORD *)(v73 + 104);
        v72 = v98;
      }
      v74 = v69[6];
      v101 = (_QWORD *)(*(_QWORD *)(v72 + 648) - 32LL);
      LogicalAddress = SysMmGetLogicalAddress(*(void *const *)(v74 + 368));
      v98 = LogicalAddress;
      v76 = *(const struct VIDMM_GLOBAL_ALLOC **)(*(_QWORD *)v92 + 48LL);
      *(_QWORD *)v92 = *(_QWORD *)(*(_QWORD *)v76 + 16LL) >> 12;
      FullPfnArray = VidMmGetFullPfnArray(v76);
      if ( LogicalAddress )
        FullPfnArray = (const unsigned __int64 *)(LogicalAddress >> 12);
      memset(v97, 0, sizeof(v97));
      v78 = v101[14] - v101[13];
      *(_QWORD *)v97 = v101;
      *(_QWORD *)&v97[8] = v101[13];
      *(_QWORD *)&v97[16] = v78 + *(_QWORD *)&v97[8];
      *(_QWORD *)&v97[24] = v78;
      *(_QWORD *)&v97[32] = v101[10];
      *(_DWORD *)&v97[40] = v92[0];
      *(_QWORD *)&v97[48] = FullPfnArray;
      *(_DWORD *)&v97[44] = v98 != 0;
      *(_QWORD *)&v97[56] = 0;
      v94 = 0;
      HwQueue = CVirtualAddressAllocator::CommitVirtualAddressRange(v22, v104, v101, v97, v105, 0, 0, &v94, 0, 0, 0);
      if ( HwQueue < 0 )
      {
        WdLogSingleEntry2(1, v22, v94);
        WdLogGlobalForLineNumber = 11179;
        DxgkLogInternalTriageEvent(
          v82,
          0x40000,
          v83,
          (unsigned int)L"Failed to commit virtual address range for paging buffer. pVaAllocator=0x%p, pFailedAlloc=0x%p",
          (__int64)v22,
          v94,
          0,
          0);
        goto LABEL_118;
      }
      LODWORD(v19) = v105;
      v65 = v103;
      v66 = v99;
    }
    ++v65;
  }
  if ( (**(_DWORD **)(*((_QWORD *)this + 3) + 3136LL) & 0x10000000) != 0 )
  {
    HwQueue = VidSchRecommitSchedulingLogs(*(_QWORD *)(*((_QWORD *)this + 2) + 744LL), v104, (unsigned int)v19);
    if ( HwQueue < 0 )
    {
      WdLogSingleEntry2(1, *((_QWORD *)this + 2), v105);
      WdLogGlobalForLineNumber = 11196;
      DxgkLogInternalTriageEvent(
        v84,
        0x40000,
        v85,
        (unsigned int)L"Failed to recommit virtual address range for scheduling logs, ADAPTER_RENDER=0x%p, PhysicalAdapterIndex=%u",
        *((_QWORD *)this + 2),
        v105,
        0,
        0);
      goto LABEL_118;
    }
    LODWORD(v19) = v105;
  }
  if ( !*(_BYTE *)(v96 + 63) )
    goto LABEL_115;
  if ( *((_QWORD *)this + (unsigned int)v19 + 325) )
  {
    v87 = VIDMM_GLOBAL::RecommitSystemFenceGpuVA(this, v104, v19);
  }
  else
  {
    v86 = v104;
    HwQueue = VIDMM_GLOBAL::MapGpuVA(
                this,
                v104,
                *((struct VIDMM_DEVICE **)this + 4585),
                (struct VIDMM_MONITORED_FENCE_STORAGE *)(*((_QWORD *)this + (unsigned int)v19 + 261) + 64LL),
                (unsigned __int64 *)this + (unsigned int)v19 + 325,
                1 << v19,
                1);
    if ( HwQueue < 0 )
      goto LABEL_118;
    v87 = VIDMM_DEVICE::MapPagingQueueGpuVAs(*((VIDMM_DEVICE **)this + 4585), v86, v105);
  }
  HwQueue = v87;
  if ( v87 >= 0 )
  {
    LODWORD(v19) = v105;
LABEL_115:
    if ( (*(_BYTE *)(v7 + 1348) & 4) != 0 )
    {
      v99 = 0;
      v92[0] = 0;
      LODWORD(v103) = 0;
      v96 = 0;
      CVirtualAddressAllocator::GetPageDirectoryData(v22, v19, &v99, v92, (unsigned int *)&v103, &v96);
      VidSchSetPagingNodePageDirectory(*(_QWORD *)(*((_QWORD *)this + 2) + 744LL), v105, v92[0], v103, v96);
    }
    *(_BYTE *)(v7 + 1349) &= 0xF3u;
  }
LABEL_118:
  if ( v52 )
    goto LABEL_119;
LABEL_120:
  *((_BYTE *)this + 37229) = 0;
  return (unsigned int)HwQueue;
}

```

## disassembly

```asm
0x14009edf0  mov     [rsp-8+arg_18], r9b
0x14009edf5  mov     [rsp-8+arg_10], r8d
0x14009edfa  mov     [rsp-8+arg_8], rdx
0x14009edff  push    rbp
0x14009ee00  push    rbx
0x14009ee01  push    rsi
0x14009ee02  push    rdi
0x14009ee03  push    r12
0x14009ee05  push    r13
0x14009ee07  push    r14
0x14009ee09  push    r15
0x14009ee0b  lea     rbp, [rsp-78h]
0x14009ee10  sub     rsp, 178h
0x14009ee17  mov     rax, [rcx+8E80h]
0x14009ee1e  mov     dil, r9b
0x14009ee21  mov     r8d, r8d
0x14009ee24  mov     r15, rdx
0x14009ee27  mov     rsi, rcx
0x14009ee2a  mov     r12, [rax+r8*8]
0x14009ee2e  xor     eax, eax
0x14009ee30  mov     r13d, eax
0x14009ee33  mov     [rbp+0B0h+var_110], eax
0x14009ee36  mov     ecx, cs:Feature_NotifyResidency2__private_featureState
0x14009ee3c  lea     ebx, [rax+1]
0x14009ee3f  mov     [rbp+0B0h+arg_0], rax
0x14009ee46  mov     dword ptr [rbp+0B0h+arg_0], ecx
0x14009ee4c  test    cl, 10h
0x14009ee4f  jnz     short loc_14009EE99
0x14009ee51  mov     rax, [rbp+0B0h+arg_0]
0x14009ee58  lea     r14d, [r13+3]
0x14009ee5c  or      ecx, ebx
0x14009ee5e  mov     [rbp+0B0h+arg_0], rax
0x14009ee65  mov     dword ptr [rbp+0B0h+arg_0], ecx
0x14009ee6b  mov     r8d, r14d
0x14009ee6e  mov     rdx, [rbp+0B0h+arg_0]
0x14009ee75  lea     rcx, Feature_NotifyResidency2__private_descriptor
0x14009ee7c  call    wil_details_FeatureReporting_ReportUsageToService
0x14009ee81  mov     rcx, [rbp+0B0h+arg_0]
0x14009ee88  lea     r8, Feature_NotifyResidency2__private_descriptor
0x14009ee8f  mov     edx, r14d
0x14009ee92  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x14009ee97  xor     eax, eax
0x14009ee99  mov     rcx, [rsi+18h]; this
0x14009ee9d  lea     rdx, [rbp+0B0h+var_100]; struct _DXGKARG_QUERYADAPTERINFO *
0x14009eea1  mov     qword ptr [rbp+0B0h+var_100.Flags], rax
0x14009eea5  mov     r14d, 4
0x14009eeab  mov     dword ptr [rbp+0B0h+var_100.hKmdProcessHandle+4], eax
0x14009eeae  lea     rax, [rbp+0B0h+arg_10]
0x14009eeb5  mov     [rbp+0B0h+var_100.pInputData], rax
0x14009eeb9  lea     rax, [rbp+0B0h+var_110]
0x14009eebd  mov     [rbp+0B0h+var_100.pOutputData], rax
0x14009eec1  mov     qword ptr [rbp+0B0h+var_100.Type], 30h ; '0'
0x14009eec9  mov     qword ptr [rbp+0B0h+var_100.InputDataSize], 4
0x14009eed1  mov     [rbp+0B0h+var_100.OutputDataSize], r14d
0x14009eed5  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x14009eeda  xor     r10d, r10d
0x14009eedd  test    eax, eax
0x14009eedf  js      short loc_14009EEE9
0x14009eee1  mov     r13d, [rbp+0B0h+var_110]
0x14009eee5  shl     r13, 14h
0x14009eee9  mov     cl, [r12+544h]
0x14009eef1  test    cl, cl
0x14009eef3  jns     short loc_14009EEFF
0x14009eef5  test    [r12+545h], bl
0x14009eefd  jnz     short loc_14009EF31
0x14009eeff  mov     rax, [rsi+18h]
0x14009ef03  cmp     [rax+0C5Fh], r10b
0x14009ef0a  jz      short loc_14009EF11
0x14009ef0c  test    r14b, cl
0x14009ef0f  jnz     short loc_14009EF36
0x14009ef11  cmp     [r12+538h], ebx
0x14009ef19  jz      short loc_14009EF31
0x14009ef1b  test    r13, r13
0x14009ef1e  jnz     short loc_14009EF31
0x14009ef20  mov     rax, [rsi+10h]
0x14009ef24  cmp     [rax+758h], r10b
0x14009ef2b  jz      loc_14009F049
0x14009ef31  test    r14b, cl
0x14009ef34  jz      short loc_14009EFA3
0x14009ef36  test    [r12+545h], r14b
0x14009ef3e  jz      loc_14009F049
0x14009ef44  mov     ecx, cs:dword_140087498
0x14009ef4a  lea     eax, [rcx-1]
0x14009ef4d  cmp     eax, 3Dh ; '='
0x14009ef50  jbe     short loc_14009EFA3
0x14009ef52  mov     edx, ecx
0x14009ef54  mov     ecx, ebx
0x14009ef56  call    cs:__imp_WdLogSingleEntry1
0x14009ef5d  nop     dword ptr [rax+rax+00h]
0x14009ef62  mov     eax, cs:dword_140087498
0x14009ef68  lea     r9, aInvalidConfigP; "Invalid _Config.PagingProcessVaSpaceBit"...
0x14009ef6f  xor     ecx, ecx
0x14009ef71  mov     cs:WdLogGlobalForLineNumber, 2989h
0x14009ef7b  mov     [rsp+1B0h+var_178], rcx
0x14009ef80  mov     [rsp+1B0h+var_180], rcx
0x14009ef85  mov     [rsp+1B0h+var_188], rcx
0x14009ef8a  mov     [rsp+1B0h+var_190], rax
0x14009ef8f  mov     edx, 40000h
0x14009ef94  call    DxgkLogInternalTriageEvent
0x14009ef99  mov     eax, 0C000000Dh
0x14009ef9e  jmp     loc_14009FCD7
0x14009efa3  test    r15, r15
0x14009efa6  jnz     loc_14009F050
0x14009efac  test    byte ptr [rsi+9169h], 10h
0x14009efb3  jz      short loc_14009EFC8
0x14009efb5  mov     edx, [rbp+0B0h+arg_10]; unsigned int
0x14009efbb  mov     r8b, dil; bool
0x14009efbe  mov     rcx, [rsi]; struct VIDMM_WORKER_THREAD2 *
0x14009efc1  call    ?VidMmQueueInitPagingProcessWorkItemAndWait@@YAJPEAUVIDMM_WORKER_THREAD2@@I_N@Z; VidMmQueueInitPagingProcessWorkItemAndWait(VIDMM_WORKER_THREAD2 *,uint,bool)
0x14009efc6  jmp     short loc_14009EFF6
0x14009efc8  xor     edx, edx; Val
0x14009efca  lea     rcx, [rbp+0B0h+var_98]; void *
0x14009efce  lea     r8d, [rdx+50h]; Size
0x14009efd2  call    memset
0x14009efd7  mov     eax, [rbp+0B0h+arg_10]
0x14009efdd  lea     rdx, [rbp+0B0h+var_A0]; struct VIDMM_SYSTEM_COMMAND *
0x14009efe1  mov     r8b, bl; bool
0x14009efe4  mov     dword ptr [rbp+0B0h+var_A0+4], eax
0x14009efe7  mov     rcx, rsi; this
0x14009efea  mov     dword ptr [rbp+0B0h+var_A0], 76h ; 'v'
0x14009eff1  call    ?QueueSystemCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x14009eff6  xor     r14d, r14d
0x14009eff9  mov     esi, eax
0x14009effb  test    eax, eax
0x14009effd  jns     short loc_14009F049
0x14009efff  movsxd  rdi, eax
0x14009f002  mov     ecx, ebx
0x14009f004  mov     rdx, rdi
0x14009f007  call    cs:__imp_WdLogSingleEntry1
0x14009f00e  nop     dword ptr [rax+rax+00h]
0x14009f013  mov     [rsp+1B0h+var_178], r14
0x14009f018  lea     r9, aFailedToInitia_19; "Failed to initialize paging process VA "...
0x14009f01f  mov     [rsp+1B0h+var_180], r14
0x14009f024  mov     edx, 40000h
0x14009f029  mov     [rsp+1B0h+var_188], r14
0x14009f02e  mov     [rsp+1B0h+var_190], rdi
0x14009f033  mov     cs:WdLogGlobalForLineNumber, 29A5h
0x14009f03d  call    DxgkLogInternalTriageEvent
0x14009f042  mov     eax, esi
0x14009f044  jmp     loc_14009FCD7
0x14009f049  xor     eax, eax
0x14009f04b  jmp     loc_14009FCD7
0x14009f050  mov     rax, [r15+18h]
0x14009f054  mov     edi, r10d
0x14009f057  mov     r14d, [rbp+0B0h+arg_10]
0x14009f05e  mov     rax, [rax+r14*8]
0x14009f062  mov     [rsi+916Dh], bl
0x14009f068  test    byte ptr [r12+544h], 4
0x14009f071  mov     r15, [rsi+r14*8+8F60h]
0x14009f079  mov     [rbp+0B0h+var_B0], rax
0x14009f07d  mov     rax, [rsi+10h]
0x14009f081  mov     rdx, [rax+2E8h]
0x14009f088  mov     [rbp+0B0h+var_108], rdx
0x14009f08c  jz      loc_14009F4AB
0x14009f092  cmp     [rbp+0B0h+arg_18], r10b
0x14009f099  jz      short loc_14009F0BA
0x14009f09b  mov     rdx, [rbp+0B0h+arg_8]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x14009f0a2  xor     r9d, r9d; bool
0x14009f0a5  mov     r8d, r14d; unsigned int
0x14009f0a8  mov     rcx, r15; this
0x14009f0ab  call    ?EvictRootPageTable@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_N@Z; CVirtualAddressAllocator::EvictRootPageTable(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,bool)
0x14009f0b0  mov     r14d, [rbp+0B0h+arg_10]
0x14009f0b7  xor     r10d, r10d
0x14009f0ba  cmp     [rsi+9180h], r10
0x14009f0c1  jnz     loc_14009F44E
0x14009f0c7  lea     rax, [rbp+0B0h+var_120]
0x14009f0cb  mov     [rbp+0B0h+var_118], r10
0x14009f0cf  mov     [rsp+1B0h+var_188], rax; unsigned int *
0x14009f0d4  lea     r9, [rbp+0B0h+var_130]; bool *
0x14009f0d8  lea     rax, [rbp+0B0h+var_128]
0x14009f0dc  mov     byte ptr [rbp+0B0h+arg_0], r10b
0x14009f0e3  lea     r8, [rbp+0B0h+arg_0]; bool *
0x14009f0ea  mov     [rsp+1B0h+var_190], rax; unsigned int *
0x14009f0ef  lea     rdx, [rbp+0B0h+var_118]; unsigned __int64 *
0x14009f0f3  mov     [rbp+0B0h+var_130], r10b
0x14009f0f7  mov     rcx, rsi; this
0x14009f0fa  mov     [rbp+0B0h+var_128], r10d
0x14009f0fe  mov     [rbp+0B0h+var_120], r10d
0x14009f102  call    ?QueryPagingProcessInfo@VIDMM_GLOBAL@@QEAAXPEA_KPEA_N1PEAI2@Z; VIDMM_GLOBAL::QueryPagingProcessInfo(unsigned __int64 *,bool *,bool *,uint *,uint *)
0x14009f107  mov     eax, [rbp+0B0h+var_128]
0x14009f10a  xor     r10d, r10d
0x14009f10d  test    eax, eax
0x14009f10f  jnz     short loc_14009F171
0x14009f111  mov     rcx, [rsi+10h]
0x14009f115  mov     edi, 800000h
0x14009f11a  cmp     [rcx+758h], r10b
0x14009f121  jz      short loc_14009F137
0x14009f123  mov     rcx, [rcx+2E8h]
0x14009f12a  call    VidSchGetSchedulingLogSize
0x14009f12f  mov     eax, eax
0x14009f131  add     rdi, rax
0x14009f134  xor     r10d, r10d
0x14009f137  cmp     [rbp+0B0h+var_130], r10b
0x14009f13b  jz      short loc_14009F143
0x14009f13d  mov     eax, [rbp+0B0h+var_120]
0x14009f140  add     rdi, rax
0x14009f143  mov     rdx, [rbp+0B0h+var_118]
0x14009f147  mov     ecx, cs:dword_140087498
0x14009f14d  shr     rdx, 2
0x14009f151  add     rdx, rdi
0x14009f154  mov     rdi, rbx
0x14009f157  shl     rdi, cl
0x14009f15a  cmp     rdx, rdi
0x14009f15d  cmovb   rdi, rdx
0x14009f161  add     rdi, 0FFFFh
0x14009f168  and     rdi, 0FFFFFFFFFFFF0000h
0x14009f16f  jmp     short loc_14009F178
0x14009f171  mov     rdi, rax
0x14009f174  shl     rdi, 14h
0x14009f178  cmp     byte ptr [rbp+0B0h+arg_0], r10b
0x14009f17f  jz      short loc_14009F1AC
0x14009f181  mov     rax, [rsi+8E80h]
0x14009f188  mov     ecx, r14d
0x14009f18b  mov     rcx, [rax+rcx*8]
0x14009f18f  mov     rax, [rcx+440h]
0x14009f196  shl     rax, 0Ch
0x14009f19a  dec     rax
0x14009f19d  add     rdi, rax
0x14009f1a0  not     rax
0x14009f1a3  and     rdi, rax
0x14009f1a6  lea     r14, [rdi+rdi]
0x14009f1aa  jmp     short loc_14009F1AF
0x14009f1ac  mov     r14, rdi
0x14009f1af  test    r13, r13
0x14009f1b2  cmovnz  r14, r13
0x14009f1b6  cmp     r14, [r15+10h]
0x14009f1ba  jbe     short loc_14009F200
0x14009f1bc  mov     [rsi+916Dh], r10b
0x14009f1c3  mov     rdx, r14
0x14009f1c6  mov     ecx, ebx
0x14009f1c8  call    cs:__imp_WdLogSingleEntry1
0x14009f1cf  nop     dword ptr [rax+rax+00h]
0x14009f1d4  xor     eax, eax
0x14009f1d6  mov     cs:WdLogGlobalForLineNumber, 2A1Bh
0x14009f1e0  mov     [rsp+1B0h+var_178], rax
0x14009f1e5  lea     r9, aThePagingProce; "The paging process virtual address spac"...
0x14009f1ec  mov     [rsp+1B0h+var_180], rax
0x14009f1f1  mov     [rsp+1B0h+var_188], rax
0x14009f1f6  mov     [rsp+1B0h+var_190], r14
0x14009f1fb  jmp     loc_14009EF8F
0x14009f200  mov     [rsi+9198h], r14
0x14009f207  cmp     [rbp+0B0h+var_130], r10b
0x14009f20b  jz      loc_14009F356
0x14009f211  mov     edx, [rbp+0B0h+var_120]; unsigned __int64
0x14009f214  lea     rcx, [rbp+0B0h+var_118]
0x14009f218  mov     [rsp+1B0h+var_180], rcx; unsigned __int64 *
0x14009f21d  xor     r9d, r9d; unsigned __int64
0x14009f220  mov     dword ptr [rsp+1B0h+var_188], 1000h; unsigned int
0x14009f228  mov     rcx, r15; this
0x14009f22b  mov     [rsp+1B0h+var_190], r10; unsigned __int64
0x14009f230  mov     [rbp+0B0h+var_118], r10
0x14009f234  call    ?ReserveVirtualAddressRangeNoAccess@CVirtualAddressAllocator@@QEAAJ_K000IPEA_K@Z; CVirtualAddressAllocator::ReserveVirtualAddressRangeNoAccess(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,unsigned __int64 *)
0x14009f239  mov     r13d, eax
0x14009f23c  test    eax, eax
0x14009f23e  jns     short loc_14009F289
0x14009f240  mov     edi, [rbp+0B0h+var_120]
0x14009f243  mov     ecx, ebx
0x14009f245  mov     edx, edi
0x14009f247  call    cs:__imp_WdLogSingleEntry1
0x14009f24e  nop     dword ptr [rax+rax+00h]
0x14009f253  xor     ebx, ebx
0x14009f255  mov     cs:WdLogGlobalForLineNumber, 2A35h
0x14009f25f  mov     [rsp+1B0h+var_178], rbx
0x14009f264  lea     r9, aFailedToReserv_0; "Failed to reserve a range for updating "...
0x14009f26b  mov     [rsp+1B0h+var_180], rbx
0x14009f270  mov     edx, 40000h
0x14009f275  mov     [rsp+1B0h+var_188], rbx
0x14009f27a  mov     [rsp+1B0h+var_190], rdi
0x14009f27f  call    DxgkLogInternalTriageEvent
0x14009f284  jmp     loc_14009F3DC
0x14009f289  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x14009f290  call    cs:__imp_ExAllocateFromLookasideListEx
0x14009f297  nop     dword ptr [rax+rax+00h]
0x14009f29c  xor     r10d, r10d
0x14009f29f  test    rax, rax
0x14009f2a2  jz      short loc_14009F2ED
0x14009f2a4  mov     r9, [rbp+0B0h+var_118]
0x14009f2a8  xor     r8d, r8d
0x14009f2ab  mov     ecx, [rbp+0B0h+var_120]
0x14009f2ae  mov     [rsp+1B0h+var_148], r10d
0x14009f2b3  add     rcx, r9
0x14009f2b6  mov     [rsp+1B0h+var_150], r10
0x14009f2bb  mov     [rsp+1B0h+var_158], r10
0x14009f2c0  mov     [rsp+1B0h+var_160], r10
0x14009f2c5  mov     [rsp+1B0h+var_168], rbx
0x14009f2ca  mov     dword ptr [rsp+1B0h+var_170], r10d
0x14009f2cf  mov     [rsp+1B0h+var_178], r10
0x14009f2d4  mov     [rsp+1B0h+var_180], r10
0x14009f2d9  mov     dword ptr [rsp+1B0h+var_188], r10d
0x14009f2de  mov     [rsp+1B0h+var_190], rcx
0x14009f2e3  mov     rcx, rax
0x14009f2e6  call    ??0VIDMM_MAPPED_VA_RANGE@@QEAA@PEAVCVirtualAddressAllocator@@PEAUVIDMM_VAD@@_K2IPEAX2W4VIDMM_VAD_OWNER_TYPE@@U_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@222K@Z; VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(CVirtualAddressAllocator *,VIDMM_VAD *,unsigned __int64,unsigned __int64,uint,void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,ulong)
0x14009f2eb  jmp     short loc_14009F2F0
0x14009f2ed  mov     rax, r10
0x14009f2f0  mov     [rsi+91A8h], rax
0x14009f2f7  test    rax, rax
0x14009f2fa  jnz     short loc_14009F356
0x14009f2fc  mov     edx, [r12+9D0h]
0x14009f304  mov     ecx, ebx
0x14009f306  call    cs:__imp_WdLogSingleEntry1
  ... truncated ...
```
