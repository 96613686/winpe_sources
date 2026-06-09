# VIDMM_GLOBAL::InitPagingProcessVaSpace(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,bool)

- ea: `0x14009b2a8`
- end: `0x14009c1a4`
- name: `?InitPagingProcessVaSpace@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_N@Z`
- size: `3836`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, unsigned int, bool)`
- caller_count: `6`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140047610`
- `0x1400bafc0`
- `0x1400d1000`
- `0x1400d14a0`
- `0x1400dfa00`
- `0x1400e8d90`

## callees

- `0x1400045ec`
- `0x140008fc0`
- `0x14003180c`
- `0x140032d3c`
- `0x140034ad8`
- `0x14003aca4`
- `0x14003f8b8`
- `0x140047e0c`
- `0x140048090`
- `0x140058760`
- `0x140058ac0`
- `0x14009990c`
- `0x140099c04`
- `0x14009b214`
- `0x14009b2a8`
- `0x14009c3ec`
- `0x1400a7a58`
- `0x1400aae14`
- `0x1400be078`
- `0x1400bf6dc`
- `0x1400c2c84`
- `0x1400c3064`
- `0x1400d13f4`
- `0x1400da9ac`
- `0x1400dfe1c`
- `0x1400ea1dc`
- `0x1400ec028`
- `0x14010f0f8`
- `0x1401139a4`
- `0x140120350`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009b748`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009ba15`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009b748`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009ba15`
- `watchdog!WdLogSingleEntry2` at `0x14009bb4c`
- `watchdog!WdLogSingleEntry2` at `0x14009bc3c`
- `watchdog!WdLogSingleEntry2` at `0x14009bf33`
- `watchdog!WdLogSingleEntry2` at `0x14009bf84`
- `watchdog!WdLogSingleEntry2` at `0x14009c00b`
- `watchdog!WdLogSingleEntry2` at `0x14009bb4c`
- `watchdog!WdLogSingleEntry2` at `0x14009bc3c`
- `watchdog!WdLogSingleEntry2` at `0x14009bf33`
- `watchdog!WdLogSingleEntry2` at `0x14009bf84`
- `watchdog!WdLogSingleEntry2` at `0x14009c00b`
- `watchdog!WdLogSingleEntry0` at `0x14009bd21`
- `watchdog!WdLogSingleEntry0` at `0x14009bd21`
- `watchdog!WdLogSingleEntry1` at `0x14009b40e`
- `watchdog!WdLogSingleEntry1` at `0x14009b4bf`
- `watchdog!WdLogSingleEntry1` at `0x14009b680`
- `watchdog!WdLogSingleEntry1` at `0x14009b6ff`
- `watchdog!WdLogSingleEntry1` at `0x14009b7be`
- `watchdog!WdLogSingleEntry1` at `0x14009b853`
- `watchdog!WdLogSingleEntry1` at `0x14009bc8c`
- `watchdog!WdLogSingleEntry1` at `0x14009b40e`
- `watchdog!WdLogSingleEntry1` at `0x14009b4bf`
- `watchdog!WdLogSingleEntry1` at `0x14009b680`
- `watchdog!WdLogSingleEntry1` at `0x14009b6ff`
- `watchdog!WdLogSingleEntry1` at `0x14009b7be`
- `watchdog!WdLogSingleEntry1` at `0x14009b853`
- `watchdog!WdLogSingleEntry1` at `0x14009bc8c`

## string_xrefs

- `0x14009bd32`: `Failed to allocate temporary VIDMM_MAPPED_VA_RANGE`
- `0x14009b420`: `Invalid _Config.PagingProcessVaSpaceBitCount`
- `0x14009bb69`: `Failed to commit VA space for the paging process. pVaAllocator=0x%p, pFailedAlloc=0x%p`
- `0x14009bf94`: `Failed to commit virtual address range for paging buffer. pVaAllocator=0x%p, pFailedAlloc=0x%p`
- `0x14009c01d`: `Failed to recommit virtual address range for scheduling logs, ADAPTER_RENDER=0x%p, PhysicalAdapterIndex=%u`

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
  _QWORD *v50; // r9
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
  v10 = *(_BYTE *)(v7 + 1084);
  if ( v10 >= 0 || (*(_BYTE *)(v7 + 1085) & 1) == 0 )
  {
    if ( *(_BYTE *)(*((_QWORD *)this + 3) + 3151LL) && (v10 & 4) != 0 )
      goto LABEL_13;
    if ( *(_DWORD *)(v7 + 1072) != 1 && !v8 && !*(_BYTE *)(*((_QWORD *)this + 2) + 1880LL) )
      return 0;
  }
  if ( (v10 & 4) == 0 )
    goto LABEL_17;
LABEL_13:
  if ( (*(_BYTE *)(v7 + 1085) & 4) == 0 )
    return 0;
  if ( (unsigned int)(dword_1400864C8 - 1) > 0x3D )
  {
    WdLogSingleEntry1(1, (unsigned int)dword_1400864C8);
    WdLogGlobalForLineNumber = 10632;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      v11,
      (unsigned int)L"Invalid _Config.PagingProcessVaSpaceBitCount",
      (unsigned int)dword_1400864C8,
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
      WdLogGlobalForLineNumber = 10660;
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
  v21 = (*(_BYTE *)(v7 + 1084) & 4) == 0;
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
        v29 = 1LL << dword_1400864C8;
        if ( v28 < 1LL << dword_1400864C8 )
          v29 = v28;
        v30 = (v29 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL;
      }
      if ( (_BYTE)v103 )
      {
        v31 = (*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * (unsigned int)v19) + 824LL) << 12) - 1LL;
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
        WdLogGlobalForLineNumber = 10778;
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
          WdLogGlobalForLineNumber = 10804;
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
          WdLogSingleEntry1(1, *(unsigned int *)(v7 + 2248));
          WdLogGlobalForLineNumber = 10832;
          DxgkLogInternalTriageEvent(
            v42,
            0x40000,
            v43,
            (unsigned int)L"Failed to reserve a range for updating page tables: 0x%I64x",
            *(unsigned int *)(v7 + 2248),
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
        WdLogGlobalForLineNumber = 10854;
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
    if ( *(_DWORD *)(v7 + 1076) == 1 )
      v49 = ComputeMaxPageTableSizeForPagingProcess((struct VIDMM_PHYSICAL_ADAPTER *)v7, *((_DWORD *)this + 9318));
    else
      v49 = *(_DWORD *)(v7 + 2248);
    *(_DWORD *)(v7 + 2252) = v49;
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
    v50 = (_QWORD *)(*(_QWORD *)(v23 + 344) + 8LL * (unsigned int)v19);
    if ( !*v50 )
    {
      v51 = *(_QWORD *)(v23 + 336);
      memset(v97, 0, 48);
      HwQueue = VidSchCreateHwQueue(0, *(_QWORD *)(v51 + 8LL * (unsigned int)v19), (unsigned int)v97, (_DWORD)v50, 0);
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
  if ( (*(_BYTE *)(v7 + 1084) & 4) != 0 )
  {
    LOBYTE(v103) = *(_BYTE *)(v7 + 1085);
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
      _InterlockedAdd(&dword_1400867F0, 1u);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 10973;
      DxgkLogInternalTriageEvent(
        v70,
        262145,
        v71,
        (unsigned int)L"Failed to allocate temporary VIDMM_MAPPED_VA_RANGE",
        10973,
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
      WdLogGlobalForLineNumber = 11017;
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
        WdLogGlobalForLineNumber = 11057;
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
      WdLogGlobalForLineNumber = 11073;
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
          WdLogGlobalForLineNumber = 11144;
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
      LogicalAddress = SysMmGetLogicalAddress(*(void *const *)(v74 + 360));
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
        WdLogGlobalForLineNumber = 11178;
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
  if ( (**(_DWORD **)(*((_QWORD *)this + 3) + 3120LL) & 0x10000000) != 0 )
  {
    HwQueue = VidSchRecommitSchedulingLogs(*(_QWORD *)(*((_QWORD *)this + 2) + 744LL), v104, (unsigned int)v19);
    if ( HwQueue < 0 )
    {
      WdLogSingleEntry2(1, *((_QWORD *)this + 2), v105);
      WdLogGlobalForLineNumber = 11195;
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
    if ( (*(_BYTE *)(v7 + 1084) & 4) != 0 )
    {
      v99 = 0;
      v92[0] = 0;
      LODWORD(v103) = 0;
      v96 = 0;
      CVirtualAddressAllocator::GetPageDirectoryData(v22, v19, &v99, v92, (unsigned int *)&v103, &v96);
      VidSchSetPagingNodePageDirectory(*(_QWORD *)(*((_QWORD *)this + 2) + 744LL), v105, v92[0], v103, v96);
    }
    *(_BYTE *)(v7 + 1085) &= 0xF3u;
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
0x14009b2a8  mov     [rsp-8+arg_18], r9b
0x14009b2ad  mov     [rsp-8+arg_10], r8d
0x14009b2b2  mov     [rsp-8+arg_8], rdx
0x14009b2b7  push    rbp
0x14009b2b8  push    rbx
0x14009b2b9  push    rsi
0x14009b2ba  push    rdi
0x14009b2bb  push    r12
0x14009b2bd  push    r13
0x14009b2bf  push    r14
0x14009b2c1  push    r15
0x14009b2c3  lea     rbp, [rsp-78h]
0x14009b2c8  sub     rsp, 178h
0x14009b2cf  mov     rax, [rcx+8E80h]
0x14009b2d6  mov     dil, r9b
0x14009b2d9  mov     r8d, r8d
0x14009b2dc  mov     r15, rdx
0x14009b2df  mov     rsi, rcx
0x14009b2e2  mov     r12, [rax+r8*8]
0x14009b2e6  xor     eax, eax
0x14009b2e8  mov     r13d, eax
0x14009b2eb  mov     [rbp+0B0h+var_110], eax
0x14009b2ee  mov     ecx, cs:Feature_NotifyResidency2__private_featureState
0x14009b2f4  lea     ebx, [rax+1]
0x14009b2f7  mov     [rbp+0B0h+arg_0], rax
0x14009b2fe  mov     dword ptr [rbp+0B0h+arg_0], ecx
0x14009b304  test    cl, 10h
0x14009b307  jnz     short loc_14009B351
0x14009b309  mov     rax, [rbp+0B0h+arg_0]
0x14009b310  lea     r14d, [r13+3]
0x14009b314  or      ecx, ebx
0x14009b316  mov     [rbp+0B0h+arg_0], rax
0x14009b31d  mov     dword ptr [rbp+0B0h+arg_0], ecx
0x14009b323  mov     r8d, r14d
0x14009b326  mov     rdx, [rbp+0B0h+arg_0]
0x14009b32d  lea     rcx, Feature_NotifyResidency2__private_descriptor
0x14009b334  call    wil_details_FeatureReporting_ReportUsageToService
0x14009b339  mov     rcx, [rbp+0B0h+arg_0]
0x14009b340  lea     r8, Feature_NotifyResidency2__private_descriptor
0x14009b347  mov     edx, r14d
0x14009b34a  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x14009b34f  xor     eax, eax
0x14009b351  mov     rcx, [rsi+18h]; this
0x14009b355  lea     rdx, [rbp+0B0h+var_100]; struct _DXGKARG_QUERYADAPTERINFO *
0x14009b359  mov     qword ptr [rbp+0B0h+var_100.Flags], rax
0x14009b35d  mov     r14d, 4
0x14009b363  mov     dword ptr [rbp+0B0h+var_100.hKmdProcessHandle+4], eax
0x14009b366  lea     rax, [rbp+0B0h+arg_10]
0x14009b36d  mov     [rbp+0B0h+var_100.pInputData], rax
0x14009b371  lea     rax, [rbp+0B0h+var_110]
0x14009b375  mov     [rbp+0B0h+var_100.pOutputData], rax
0x14009b379  mov     qword ptr [rbp+0B0h+var_100.Type], 30h ; '0'
0x14009b381  mov     qword ptr [rbp+0B0h+var_100.InputDataSize], 4
0x14009b389  mov     [rbp+0B0h+var_100.OutputDataSize], r14d
0x14009b38d  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x14009b392  xor     r10d, r10d
0x14009b395  test    eax, eax
0x14009b397  js      short loc_14009B3A1
0x14009b399  mov     r13d, [rbp+0B0h+var_110]
0x14009b39d  shl     r13, 14h
0x14009b3a1  mov     cl, [r12+43Ch]
0x14009b3a9  test    cl, cl
0x14009b3ab  jns     short loc_14009B3B7
0x14009b3ad  test    [r12+43Dh], bl
0x14009b3b5  jnz     short loc_14009B3E9
0x14009b3b7  mov     rax, [rsi+18h]
0x14009b3bb  cmp     [rax+0C4Fh], r10b
0x14009b3c2  jz      short loc_14009B3C9
0x14009b3c4  test    r14b, cl
0x14009b3c7  jnz     short loc_14009B3EE
0x14009b3c9  cmp     [r12+430h], ebx
0x14009b3d1  jz      short loc_14009B3E9
0x14009b3d3  test    r13, r13
0x14009b3d6  jnz     short loc_14009B3E9
0x14009b3d8  mov     rax, [rsi+10h]
0x14009b3dc  cmp     [rax+758h], r10b
0x14009b3e3  jz      loc_14009B501
0x14009b3e9  test    r14b, cl
0x14009b3ec  jz      short loc_14009B45B
0x14009b3ee  test    [r12+43Dh], r14b
0x14009b3f6  jz      loc_14009B501
0x14009b3fc  mov     ecx, cs:dword_1400864C8
0x14009b402  lea     eax, [rcx-1]
0x14009b405  cmp     eax, 3Dh ; '='
0x14009b408  jbe     short loc_14009B45B
0x14009b40a  mov     edx, ecx
0x14009b40c  mov     ecx, ebx
0x14009b40e  call    cs:__imp_WdLogSingleEntry1
0x14009b415  nop     dword ptr [rax+rax+00h]
0x14009b41a  mov     eax, cs:dword_1400864C8
0x14009b420  lea     r9, aInvalidConfigP; "Invalid _Config.PagingProcessVaSpaceBit"...
0x14009b427  xor     ecx, ecx
0x14009b429  mov     cs:WdLogGlobalForLineNumber, 2988h
0x14009b433  mov     [rsp+1B0h+var_178], rcx
0x14009b438  mov     [rsp+1B0h+var_180], rcx
0x14009b43d  mov     [rsp+1B0h+var_188], rcx
0x14009b442  mov     [rsp+1B0h+var_190], rax
0x14009b447  mov     edx, 40000h
0x14009b44c  call    DxgkLogInternalTriageEvent
0x14009b451  mov     eax, 0C000000Dh
0x14009b456  jmp     loc_14009C18F
0x14009b45b  test    r15, r15
0x14009b45e  jnz     loc_14009B508
0x14009b464  test    byte ptr [rsi+9169h], 10h
0x14009b46b  jz      short loc_14009B480
0x14009b46d  mov     edx, [rbp+0B0h+arg_10]; unsigned int
0x14009b473  mov     r8b, dil; bool
0x14009b476  mov     rcx, [rsi]; struct VIDMM_WORKER_THREAD2 *
0x14009b479  call    ?VidMmQueueInitPagingProcessWorkItemAndWait@@YAJPEAUVIDMM_WORKER_THREAD2@@I_N@Z; VidMmQueueInitPagingProcessWorkItemAndWait(VIDMM_WORKER_THREAD2 *,uint,bool)
0x14009b47e  jmp     short loc_14009B4AE
0x14009b480  xor     edx, edx; Val
0x14009b482  lea     rcx, [rbp+0B0h+var_98]; void *
0x14009b486  lea     r8d, [rdx+50h]; Size
0x14009b48a  call    memset
0x14009b48f  mov     eax, [rbp+0B0h+arg_10]
0x14009b495  lea     rdx, [rbp+0B0h+var_A0]; struct VIDMM_SYSTEM_COMMAND *
0x14009b499  mov     r8b, bl; bool
0x14009b49c  mov     dword ptr [rbp+0B0h+var_A0+4], eax
0x14009b49f  mov     rcx, rsi; this
0x14009b4a2  mov     dword ptr [rbp+0B0h+var_A0], 76h ; 'v'
0x14009b4a9  call    ?QueueSystemCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x14009b4ae  xor     r14d, r14d
0x14009b4b1  mov     esi, eax
0x14009b4b3  test    eax, eax
0x14009b4b5  jns     short loc_14009B501
0x14009b4b7  movsxd  rdi, eax
0x14009b4ba  mov     ecx, ebx
0x14009b4bc  mov     rdx, rdi
0x14009b4bf  call    cs:__imp_WdLogSingleEntry1
0x14009b4c6  nop     dword ptr [rax+rax+00h]
0x14009b4cb  mov     [rsp+1B0h+var_178], r14
0x14009b4d0  lea     r9, aFailedToInitia_15; "Failed to initialize paging process VA "...
0x14009b4d7  mov     [rsp+1B0h+var_180], r14
0x14009b4dc  mov     edx, 40000h
0x14009b4e1  mov     [rsp+1B0h+var_188], r14
0x14009b4e6  mov     [rsp+1B0h+var_190], rdi
0x14009b4eb  mov     cs:WdLogGlobalForLineNumber, 29A4h
0x14009b4f5  call    DxgkLogInternalTriageEvent
0x14009b4fa  mov     eax, esi
0x14009b4fc  jmp     loc_14009C18F
0x14009b501  xor     eax, eax
0x14009b503  jmp     loc_14009C18F
0x14009b508  mov     rax, [r15+18h]
0x14009b50c  mov     edi, r10d
0x14009b50f  mov     r14d, [rbp+0B0h+arg_10]
0x14009b516  mov     rax, [rax+r14*8]
0x14009b51a  mov     [rsi+916Dh], bl
0x14009b520  test    byte ptr [r12+43Ch], 4
0x14009b529  mov     r15, [rsi+r14*8+8F60h]
0x14009b531  mov     [rbp+0B0h+var_B0], rax
0x14009b535  mov     rax, [rsi+10h]
0x14009b539  mov     rdx, [rax+2E8h]
0x14009b540  mov     [rbp+0B0h+var_108], rdx
0x14009b544  jz      loc_14009B963
0x14009b54a  cmp     [rbp+0B0h+arg_18], r10b
0x14009b551  jz      short loc_14009B572
0x14009b553  mov     rdx, [rbp+0B0h+arg_8]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x14009b55a  xor     r9d, r9d; bool
0x14009b55d  mov     r8d, r14d; unsigned int
0x14009b560  mov     rcx, r15; this
0x14009b563  call    ?EvictRootPageTable@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_N@Z; CVirtualAddressAllocator::EvictRootPageTable(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,bool)
0x14009b568  mov     r14d, [rbp+0B0h+arg_10]
0x14009b56f  xor     r10d, r10d
0x14009b572  cmp     [rsi+9180h], r10
0x14009b579  jnz     loc_14009B906
0x14009b57f  lea     rax, [rbp+0B0h+var_120]
0x14009b583  mov     [rbp+0B0h+var_118], r10
0x14009b587  mov     [rsp+1B0h+var_188], rax; unsigned int *
0x14009b58c  lea     r9, [rbp+0B0h+var_130]; bool *
0x14009b590  lea     rax, [rbp+0B0h+var_128]
0x14009b594  mov     byte ptr [rbp+0B0h+arg_0], r10b
0x14009b59b  lea     r8, [rbp+0B0h+arg_0]; bool *
0x14009b5a2  mov     [rsp+1B0h+var_190], rax; unsigned int *
0x14009b5a7  lea     rdx, [rbp+0B0h+var_118]; unsigned __int64 *
0x14009b5ab  mov     [rbp+0B0h+var_130], r10b
0x14009b5af  mov     rcx, rsi; this
0x14009b5b2  mov     [rbp+0B0h+var_128], r10d
0x14009b5b6  mov     [rbp+0B0h+var_120], r10d
0x14009b5ba  call    ?QueryPagingProcessInfo@VIDMM_GLOBAL@@QEAAXPEA_KPEA_N1PEAI2@Z; VIDMM_GLOBAL::QueryPagingProcessInfo(unsigned __int64 *,bool *,bool *,uint *,uint *)
0x14009b5bf  mov     eax, [rbp+0B0h+var_128]
0x14009b5c2  xor     r10d, r10d
0x14009b5c5  test    eax, eax
0x14009b5c7  jnz     short loc_14009B629
0x14009b5c9  mov     rcx, [rsi+10h]
0x14009b5cd  mov     edi, 800000h
0x14009b5d2  cmp     [rcx+758h], r10b
0x14009b5d9  jz      short loc_14009B5EF
0x14009b5db  mov     rcx, [rcx+2E8h]
0x14009b5e2  call    VidSchGetSchedulingLogSize
0x14009b5e7  mov     eax, eax
0x14009b5e9  add     rdi, rax
0x14009b5ec  xor     r10d, r10d
0x14009b5ef  cmp     [rbp+0B0h+var_130], r10b
0x14009b5f3  jz      short loc_14009B5FB
0x14009b5f5  mov     eax, [rbp+0B0h+var_120]
0x14009b5f8  add     rdi, rax
0x14009b5fb  mov     rdx, [rbp+0B0h+var_118]
0x14009b5ff  mov     ecx, cs:dword_1400864C8
0x14009b605  shr     rdx, 2
0x14009b609  add     rdx, rdi
0x14009b60c  mov     rdi, rbx
0x14009b60f  shl     rdi, cl
0x14009b612  cmp     rdx, rdi
0x14009b615  cmovb   rdi, rdx
0x14009b619  add     rdi, 0FFFFh
0x14009b620  and     rdi, 0FFFFFFFFFFFF0000h
0x14009b627  jmp     short loc_14009B630
0x14009b629  mov     rdi, rax
0x14009b62c  shl     rdi, 14h
0x14009b630  cmp     byte ptr [rbp+0B0h+arg_0], r10b
0x14009b637  jz      short loc_14009B664
0x14009b639  mov     rax, [rsi+8E80h]
0x14009b640  mov     ecx, r14d
0x14009b643  mov     rcx, [rax+rcx*8]
0x14009b647  mov     rax, [rcx+338h]
0x14009b64e  shl     rax, 0Ch
0x14009b652  dec     rax
0x14009b655  add     rdi, rax
0x14009b658  not     rax
0x14009b65b  and     rdi, rax
0x14009b65e  lea     r14, [rdi+rdi]
0x14009b662  jmp     short loc_14009B667
0x14009b664  mov     r14, rdi
0x14009b667  test    r13, r13
0x14009b66a  cmovnz  r14, r13
0x14009b66e  cmp     r14, [r15+10h]
0x14009b672  jbe     short loc_14009B6B8
0x14009b674  mov     [rsi+916Dh], r10b
0x14009b67b  mov     rdx, r14
0x14009b67e  mov     ecx, ebx
0x14009b680  call    cs:__imp_WdLogSingleEntry1
0x14009b687  nop     dword ptr [rax+rax+00h]
0x14009b68c  xor     eax, eax
0x14009b68e  mov     cs:WdLogGlobalForLineNumber, 2A1Ah
0x14009b698  mov     [rsp+1B0h+var_178], rax
0x14009b69d  lea     r9, aThePagingProce; "The paging process virtual address spac"...
0x14009b6a4  mov     [rsp+1B0h+var_180], rax
0x14009b6a9  mov     [rsp+1B0h+var_188], rax
0x14009b6ae  mov     [rsp+1B0h+var_190], r14
0x14009b6b3  jmp     loc_14009B447
0x14009b6b8  mov     [rsi+9198h], r14
0x14009b6bf  cmp     [rbp+0B0h+var_130], r10b
0x14009b6c3  jz      loc_14009B80E
0x14009b6c9  mov     edx, [rbp+0B0h+var_120]; unsigned __int64
0x14009b6cc  lea     rcx, [rbp+0B0h+var_118]
0x14009b6d0  mov     [rsp+1B0h+var_180], rcx; unsigned __int64 *
0x14009b6d5  xor     r9d, r9d; unsigned __int64
0x14009b6d8  mov     dword ptr [rsp+1B0h+var_188], 1000h; unsigned int
0x14009b6e0  mov     rcx, r15; this
0x14009b6e3  mov     [rsp+1B0h+var_190], r10; unsigned __int64
0x14009b6e8  mov     [rbp+0B0h+var_118], r10
0x14009b6ec  call    ?ReserveVirtualAddressRangeNoAccess@CVirtualAddressAllocator@@QEAAJ_K000IPEA_K@Z; CVirtualAddressAllocator::ReserveVirtualAddressRangeNoAccess(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,unsigned __int64 *)
0x14009b6f1  mov     r13d, eax
0x14009b6f4  test    eax, eax
0x14009b6f6  jns     short loc_14009B741
0x14009b6f8  mov     edi, [rbp+0B0h+var_120]
0x14009b6fb  mov     ecx, ebx
0x14009b6fd  mov     edx, edi
0x14009b6ff  call    cs:__imp_WdLogSingleEntry1
0x14009b706  nop     dword ptr [rax+rax+00h]
0x14009b70b  xor     ebx, ebx
0x14009b70d  mov     cs:WdLogGlobalForLineNumber, 2A34h
0x14009b717  mov     [rsp+1B0h+var_178], rbx
0x14009b71c  lea     r9, aFailedToReserv_0; "Failed to reserve a range for updating "...
0x14009b723  mov     [rsp+1B0h+var_180], rbx
0x14009b728  mov     edx, 40000h
0x14009b72d  mov     [rsp+1B0h+var_188], rbx
0x14009b732  mov     [rsp+1B0h+var_190], rdi
0x14009b737  call    DxgkLogInternalTriageEvent
0x14009b73c  jmp     loc_14009B894
0x14009b741  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x14009b748  call    cs:__imp_ExAllocateFromLookasideListEx
0x14009b74f  nop     dword ptr [rax+rax+00h]
0x14009b754  xor     r10d, r10d
0x14009b757  test    rax, rax
0x14009b75a  jz      short loc_14009B7A5
0x14009b75c  mov     r9, [rbp+0B0h+var_118]
0x14009b760  xor     r8d, r8d
0x14009b763  mov     ecx, [rbp+0B0h+var_120]
0x14009b766  mov     [rsp+1B0h+var_148], r10d
0x14009b76b  add     rcx, r9
0x14009b76e  mov     [rsp+1B0h+var_150], r10
0x14009b773  mov     [rsp+1B0h+var_158], r10
0x14009b778  mov     [rsp+1B0h+var_160], r10
0x14009b77d  mov     [rsp+1B0h+var_168], rbx
0x14009b782  mov     dword ptr [rsp+1B0h+var_170], r10d
0x14009b787  mov     [rsp+1B0h+var_178], r10
0x14009b78c  mov     [rsp+1B0h+var_180], r10
0x14009b791  mov     dword ptr [rsp+1B0h+var_188], r10d
0x14009b796  mov     [rsp+1B0h+var_190], rcx
0x14009b79b  mov     rcx, rax
0x14009b79e  call    ??0VIDMM_MAPPED_VA_RANGE@@QEAA@PEAVCVirtualAddressAllocator@@PEAUVIDMM_VAD@@_K2IPEAX2W4VIDMM_VAD_OWNER_TYPE@@U_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@222K@Z; VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(CVirtualAddressAllocator *,VIDMM_VAD *,unsigned __int64,unsigned __int64,uint,void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,ulong)
0x14009b7a3  jmp     short loc_14009B7A8
0x14009b7a5  mov     rax, r10
0x14009b7a8  mov     [rsi+91A8h], rax
0x14009b7af  test    rax, rax
0x14009b7b2  jnz     short loc_14009B80E
0x14009b7b4  mov     edx, [r12+8C8h]
0x14009b7bc  mov     ecx, ebx
0x14009b7be  call    cs:__imp_WdLogSingleEntry1
  ... truncated ...
```
