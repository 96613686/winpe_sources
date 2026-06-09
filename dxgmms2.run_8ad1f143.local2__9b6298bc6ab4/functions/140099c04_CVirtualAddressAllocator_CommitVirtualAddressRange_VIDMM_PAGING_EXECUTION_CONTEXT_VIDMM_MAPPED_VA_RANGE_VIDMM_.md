# CVirtualAddressAllocator::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_MAPPED_VA_RANGE *,VIDMM_COMMIT_VA_PACKET const *,uint,uint,VIDMM_FLUSH_TLB_MODE,VIDMM_ALLOC * *,bool *,VIDMM_PAGESIZEUSAGE,unsigned __int64)

- ea: `0x140099c04`
- end: `0x14009a6b0`
- name: `?CommitVirtualAddressRange@CVirtualAddressAllocator@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_MAPPED_VA_RANGE@@PEBUVIDMM_COMMIT_VA_PACKET@@IIW4VIDMM_FLUSH_TLB_MODE@@PEAPEAUVIDMM_ALLOC@@PEA_NW4VIDMM_PAGESIZEUSAGE@@_K@Z`
- size: `2732`
- prototype: ``
- caller_count: `12`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003bd20`
- `0x140042f3c`
- `0x140095bc4`
- `0x140097b2c`
- `0x1400999dc`
- `0x14009b2a8`
- `0x14009f4ac`
- `0x1400a14f8`
- `0x1400a7acc`
- `0x1400b9cc4`
- `0x1400be11c`
- `0x1400d080c`

## callees

- `0x1400045ec`
- `0x14000a980`
- `0x14001265c`
- `0x14002ea7c`
- `0x14002ed1c`
- `0x1400311ac`
- `0x140033730`
- `0x14003f664`
- `0x1400411bc`
- `0x140042960`
- `0x140058680`
- `0x140058ac0`
- `0x14009634c`
- `0x140099c04`
- `0x14009b1ac`
- `0x14009c458`
- `0x14009f4ac`
- `0x140103230`
- `0x14010fdf4`
- `0x1401104b8`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x140099e45`
- `watchdog!WdLogSingleEntry2` at `0x140099ea7`
- `watchdog!WdLogSingleEntry2` at `0x140099e45`
- `watchdog!WdLogSingleEntry2` at `0x140099ea7`
- `watchdog!WdLogSingleEntry5` at `0x14009a69a`
- `watchdog!WdLogSingleEntry5` at `0x14009a69a`
- `watchdog!WdLogSingleEntry0` at `0x140099f91`
- `watchdog!WdLogSingleEntry0` at `0x14009a058`
- `watchdog!WdLogSingleEntry0` at `0x140099f91`
- `watchdog!WdLogSingleEntry0` at `0x14009a058`
- `watchdog!WdLogSingleEntry1` at `0x140099d0f`
- `watchdog!WdLogSingleEntry1` at `0x140099d7b`
- `watchdog!WdLogSingleEntry1` at `0x14009a184`
- `watchdog!WdLogSingleEntry1` at `0x14009a636`
- `watchdog!WdLogSingleEntry1` at `0x140099d0f`
- `watchdog!WdLogSingleEntry1` at `0x140099d7b`
- `watchdog!WdLogSingleEntry1` at `0x14009a184`
- `watchdog!WdLogSingleEntry1` at `0x14009a636`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14009a677`

## string_xrefs

- `0x140099f9f`: `Cannot grow the root page directory of the paging process`
- `0x14009a1a1`: `RecommitGpuVirtualAddresses failed. Status=0x%.8x`
- `0x14009a069`: `Failed to create page directory`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall CVirtualAddressAllocator::CommitVirtualAddressRange(
        __int64 a1,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        int a6,
        int a7,
        struct VIDMM_ALLOC **a8,
        _BYTE *a9,
        int a10,
        unsigned __int64 a11)
{
  _BYTE *v11; // r11
  unsigned int v13; // ecx
  int v15; // edx
  __int64 v17; // r8
  struct VIDMM_ALLOC **v18; // r9
  __int64 v19; // r10
  __int64 v20; // rax
  __int64 v21; // r13
  char v22; // al
  struct DXGPROCESS_RENDER_ADAPTER_INFO *RenderAdapterInfo; // rax
  int v24; // eax
  __int64 v25; // r15
  int v26; // ecx
  int v27; // r8d
  int v28; // eax
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // r15
  unsigned __int64 v32; // r12
  int v33; // ecx
  int v34; // r8d
  unsigned __int64 v35; // r8
  int v36; // ecx
  int v37; // r8d
  bool v38; // zf
  __int64 v39; // r15
  _DWORD *v40; // r9
  int v41; // eax
  __int64 v42; // r15
  VIDMM_PAGE_DIRECTORY *v43; // r8
  UINT v44; // ebx
  int v45; // r8d
  UINT NumberOfPte; // eax
  unsigned int v47; // ecx
  unsigned int v48; // edx
  __int64 v49; // rcx
  unsigned int RootPageTableSize; // eax
  struct VIDMM_PAGE_DIRECTORY *PageDirectory; // rax
  int v52; // ecx
  int v53; // r8d
  int v54; // ebx
  VIDMM_PAGE_DIRECTORY *v55; // rcx
  __int64 v56; // rbx
  int v57; // ecx
  int v58; // r8d
  int v59; // ebx
  int v60; // ecx
  int v61; // r8d
  __int64 v62; // r9
  int v63; // r8d
  char v64; // al
  int v65; // r10d
  __int64 v66; // rax
  char v67; // al
  __int64 VidMmGlobalAllocFromOwner; // rax
  int v69; // ecx
  _DWORD *v70; // r11
  __int64 v71; // r8
  char v72; // r9
  unsigned __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // rax
  char v76; // al
  int v77; // ecx
  __int64 v78; // rcx
  __int64 v79; // r8
  unsigned int v80; // r10d
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v81; // r15
  int v82; // ecx
  int v83; // r8d
  unsigned int v84; // [rsp+50h] [rbp-B0h]
  unsigned int v85[2]; // [rsp+58h] [rbp-A8h]
  UINT v86; // [rsp+60h] [rbp-A0h]
  _DWORD *v88; // [rsp+70h] [rbp-90h]
  unsigned __int64 v89; // [rsp+80h] [rbp-80h]
  int v90; // [rsp+88h] [rbp-78h]
  _DXGKARG_GETROOTPAGETABLESIZE v91; // [rsp+90h] [rbp-70h] BYREF
  VIDMM_PAGE_DIRECTORY *v92; // [rsp+98h] [rbp-68h]
  _QWORD **v93; // [rsp+A0h] [rbp-60h]
  _BYTE *v94; // [rsp+A8h] [rbp-58h]
  __int64 v95; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v96; // [rsp+B8h] [rbp-48h]
  _BYTE v97[32]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v98[6]; // [rsp+E0h] [rbp-20h] BYREF

  v11 = a9;
  v13 = *(_DWORD *)(a3 + 72);
  v15 = a6;
  v17 = *(_QWORD *)(a1 + 96);
  v18 = a8;
  v19 = (v13 >> 4) & 0x3F;
  v20 = *(_QWORD *)(v17 + 36480);
  v94 = a9;
  *(_QWORD *)v85 = v19;
  v21 = *(_QWORD *)(v20 + 8 * v19);
  if ( (v13 & 0x800) != 0 )
    goto LABEL_10;
  v22 = *(_BYTE *)(v21 + 1084);
  if ( (v22 & 0x10) != 0 )
  {
    RenderAdapterInfo = DXGPROCESS::GetRenderAdapterInfo(
                          *(DXGPROCESS **)(*(_QWORD *)(a1 + 104) + 72LL),
                          *(_DWORD *)(*(_QWORD *)(v17 + 24) + 240LL));
    v24 = SysMmMapLogicalAddressRange(
            *(struct SYSMM_ADAPTER **)(*(_QWORD *)(*((_QWORD *)RenderAdapterInfo + 10) + 16LL) + 224LL),
            v85[0],
            *((struct _IOMMU_DMA_DOMAIN **)RenderAdapterInfo + 5),
            *(_QWORD *)(a4 + 8),
            *(_QWORD *)(a4 + 24),
            *(_QWORD *)(a4 + 56),
            (const struct _DXGK_ADL *)(a4 + 40),
            (*(_BYTE *)(a3 + 96) & 1) == 0);
    v25 = v24;
    if ( v24 < 0 )
    {
      WdLogSingleEntry1(1, v24);
      WdLogGlobalForLineNumber = 4044;
LABEL_8:
      DxgkLogInternalTriageEvent(
        v26,
        0x40000,
        v27,
        (unsigned int)L"SysMmMapLogicalAddressRange failed: 0x%I64x",
        v25,
        0,
        0,
        0);
      return (unsigned int)v25;
    }
LABEL_9:
    v11 = v94;
    v18 = a8;
    v15 = a6;
    v19 = *(_QWORD *)v85;
    *(_DWORD *)(a3 + 72) |= 0x800u;
    goto LABEL_10;
  }
  if ( (v22 & 0x20) != 0 )
  {
    v28 = SysMmMapLogicalAddressRange(
            *(struct SYSMM_ADAPTER **)(*(_QWORD *)(v17 + 24) + 224LL),
            v19,
            0,
            *(_QWORD *)(a4 + 8),
            *(_QWORD *)(a4 + 24),
            *(_QWORD *)(a4 + 56),
            (const struct _DXGK_ADL *)(a4 + 40),
            (*(_BYTE *)(a3 + 96) & 1) == 0);
    v25 = v28;
    if ( v28 < 0 )
    {
      WdLogSingleEntry1(1, v28);
      WdLogGlobalForLineNumber = 4065;
      goto LABEL_8;
    }
    goto LABEL_9;
  }
LABEL_10:
  if ( (*(_BYTE *)(v21 + 1084) & 4) == 0 )
    return 0;
  if ( a7 == 2 )
    *v11 = 0;
  v30 = a11;
  *v18 = 0;
  v31 = *(_QWORD *)(a4 + 8) >> 12;
  v32 = *(_QWORD *)(a4 + 24) >> 12;
  v89 = *(_QWORD *)(a4 + 8);
  if ( !a11 )
    v30 = v31 + v32;
  if ( v30 <= v31 )
  {
    WdLogSingleEntry2(1, v30, v31);
    WdLogGlobalForLineNumber = 4112;
    DxgkLogInternalTriageEvent(
      v33,
      0x40000,
      v34,
      (unsigned int)L"LastPageIndex <= FirstPageIndex (%I64u < %I64u)",
      v30,
      v31,
      0,
      0);
    return 3221225485LL;
  }
  v35 = *(_QWORD *)(a1 + 16) >> 12;
  if ( v30 > v35 )
  {
    WdLogSingleEntry2(1, v30, v35);
    WdLogGlobalForLineNumber = 4121;
    DxgkLogInternalTriageEvent(
      v36,
      0x40000,
      v37,
      (unsigned int)L"LastPageIndex >= m_VirtualAddressSize (%I64u < %I64u)",
      v30,
      *(_QWORD *)(a1 + 16) >> 12,
      0,
      0);
    return 3221225485LL;
  }
  v38 = (*(_BYTE *)(a3 + 96) & 4) == 0;
  v39 = *(_QWORD *)(a1 + 128);
  v40 = *(_DWORD **)(v21 + 1088);
  v90 = *(_DWORD *)(a3 + 72);
  v93 = *(_QWORD ***)(a3 + 64);
  v96 = *(_QWORD *)(a4 + 32);
  v41 = -2;
  if ( v38 )
    v41 = v15;
  v88 = v40;
  v42 = 32 * v19 + v39;
  LODWORD(v95) = v41;
  v43 = *(VIDMM_PAGE_DIRECTORY **)v42;
  v92 = v43;
  if ( v43 && (*(_DWORD *)v43 & 8) == 0 )
    goto LABEL_42;
  v86 = *(_DWORD *)(v42 + 16);
  v44 = (((v30 - 1) & *(_QWORD *)(v21 + 48LL * *(unsigned int *)(v21 + 1076) + 752)) >> *(_QWORD *)(v21
                                                                                                  + 48LL * *(unsigned int *)(v21 + 1076)
                                                                                                  + 760))
      + 1;
  if ( v44 <= v86 )
  {
    if ( v43 )
      goto LABEL_42;
  }
  if ( v43 && (*(_DWORD *)(a1 + 152) & 4) != 0 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4161;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      v45,
      (unsigned int)L"Cannot grow the root page directory of the paging process",
      4161,
      0,
      0,
      0);
    return 3221225473LL;
  }
  NumberOfPte = *(_DWORD *)(v42 + 16);
  v47 = *(_DWORD *)(v42 + 20);
  v48 = v47;
  v84 = v47;
  if ( v40[4] == 2 )
  {
    *(_DWORD *)(v42 + 16) = v44;
    v49 = *(_QWORD *)(a1 + 96);
    v91.NumberOfPte = v44;
    v91.PhysicalAdapterIndex = v19;
    RootPageTableSize = ADAPTER_RENDER::DdiGetRootPageTableSize(*(ADAPTER_RENDER **)(v49 + 16), &v91);
    v47 = v84;
    v48 = RootPageTableSize;
    LODWORD(v19) = v85[0];
    *(_DWORD *)(v42 + 20) = RootPageTableSize;
    NumberOfPte = v91.NumberOfPte;
    *(_DWORD *)(v42 + 16) = v91.NumberOfPte;
  }
  if ( NumberOfPte < v44 || v48 < v47 )
  {
    WdLogSingleEntry1(1, NumberOfPte);
    WdLogGlobalForLineNumber = 4185;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      v83,
      (unsigned int)L"The driver returned invalid number of entries from DdiGetRootPageTableSize: 0x%I64x",
      *(unsigned int *)(v42 + 16),
      0,
      0,
      0);
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 72);
    WdLogGlobalForLineNumber = 222;
    JUMPOUT(0x14009A6B0LL);
  }
  PageDirectory = CreatePageDirectory((struct CVirtualAddressAllocator *)a1, v19, *(_DWORD *)(v21 + 1076));
  *(_QWORD *)v42 = PageDirectory;
  if ( !PageDirectory )
  {
    _InterlockedIncrement(&dword_1400867F4);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 4200;
    DxgkLogInternalTriageEvent(v52, 262145, v53, (unsigned int)L"Failed to create page directory", 4200, 0, 0, 0);
    *(_QWORD *)v42 = v92;
    *(_DWORD *)(v42 + 16) = v86;
    *(_DWORD *)(v42 + 20) = v84;
    return 3221225495LL;
  }
  if ( (*(_DWORD *)(a1 + 152) & 4) != 0 )
    *(_DWORD *)PageDirectory |= 0x100000u;
  if ( !v92 )
    goto LABEL_42;
  VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(
    *(VIDMM_PROCESS **)(a1 + 104),
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 24LL) + 240LL),
    1);
  v54 = *(_DWORD *)(v42 + 16);
  v55 = v92;
  *(_DWORD *)(v42 + 16) = v86;
  VIDMM_PAGE_DIRECTORY::DestroyPageDirectory(v55, a2, (struct CVirtualAddressAllocator *)a1, 0);
  *(_DWORD *)(v42 + 16) = v54;
  v56 = (int)CVirtualAddressAllocator::RecommitVirtualAddressRanges(
               (CVirtualAddressAllocator *)a1,
               a2,
               1LL << SLOBYTE(v85[0]),
               a8);
  CVirtualAddressAllocator::FlushGpuVaTlb((CVirtualAddressAllocator *)a1, a2, v85[0], 0, 0);
  VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(*(VIDMM_GLOBAL **)(a1 + 96), a2, v85[0]);
  VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(
    *(VIDMM_PROCESS **)(a1 + 104),
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 24LL) + 240LL),
    0);
  if ( (int)v56 >= 0 )
  {
LABEL_42:
    v59 = v90 & 0xF;
    DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
      (DXGAUTOPUSHLOCKEXCLUSIVE *)v97,
      (struct DXGPUSHLOCK *const)(a1 + 64),
      *(_QWORD *)(a1 + 72) != (_QWORD)KeGetCurrentThread());
    if ( byte_140086202 < 0 )
      McTemplateK0pqxx_EtwWriteTransfer(v60, (unsigned int)CommitVirtualAddressStart, v61, (_DWORD)v93, v59, v89, v32);
    memset(v98, 0, sizeof(v98));
    v62 = *(_QWORD *)(a3 + 128);
    if ( v62 )
    {
      *((_QWORD *)&v98[1] + 1) = *(_QWORD *)(a3 + 120) >> 12;
      *((_QWORD *)&v98[5] + 1) = v62;
    }
    v63 = 1;
    v64 = BYTE13(v98[4]);
    v65 = v95;
    if ( (*(_BYTE *)(v21 + 1086) & 8) != 0 )
      v64 = 1;
    BYTE13(v98[4]) = v64;
    *(_QWORD *)&v98[1] = *(_QWORD *)(a3 + 88);
    *(_QWORD *)&v98[0] = 1;
    switch ( (_DWORD)v95 )
    {
      case 0xFFFFFFFE:
        v66 = (unsigned __int16)(*(_WORD *)(a4 + 24) | v89);
        *(_QWORD *)&v98[0] = 3;
        if ( !v66 )
        {
          v67 = BYTE12(v98[4]);
          if ( (*(_BYTE *)(v21 + 1086) & 8) != 0 )
            v67 = 1;
          BYTE12(v98[4]) = v67;
        }
        VidMmGlobalAllocFromOwner = GetVidMmGlobalAllocFromOwner(*(_DWORD *)(a3 + 72) & 0xF, *(_QWORD *)(a3 + 64));
        if ( VidMmGlobalAllocFromOwner )
        {
          v69 = *(_DWORD *)(*(_QWORD *)VidMmGlobalAllocFromOwner + 32LL);
          if ( !v69 || (_WORD)v69 )
            BYTE12(v98[4]) = 0;
        }
        goto LABEL_57;
      case 0xFFFFFFFD:
        BYTE12(v98[4]) = 1;
LABEL_57:
        v70 = v88;
LABEL_58:
        DWORD2(v98[4]) = v65;
        *(_QWORD *)&v98[3] = v93;
        DWORD2(v98[3]) = v90 & 0xF;
        v98[2] = *(_OWORD *)(a4 + 40);
        if ( v59 == 3 )
        {
          *(_QWORD *)&v98[4] = v93;
        }
        else if ( v59 == v63 )
        {
          *(_QWORD *)&v98[4] = **v93;
        }
        if ( (*v70 & 0x80u) != 0 )
          HIWORD(v98[4]) = 257;
        LODWORD(v56) = VIDMM_PAGE_DIRECTORY::CommitVirtualAddressRange(
                         *(VIDMM_PAGE_DIRECTORY **)v42,
                         a2,
                         (struct CVirtualAddressAllocator *)a1,
                         (const struct COMMIT_VA_STATE *)v98,
                         v96,
                         v89,
                         v32,
                         *(_QWORD *)(a4 + 56),
                         0,
                         a8);
        if ( byte_140086202 < 0 )
          McTemplateK0x_EtwWriteTransfer(v78, CommitVirtualAddressEnd, v79, v93);
        if ( VIDMM_GLOBAL::MustFlushTlbOnValidTransition(*(VIDMM_GLOBAL **)(a1 + 96), v85[0]) || BYTE4(v98[5]) )
        {
          v81 = a2;
          if ( a7 == 1 )
          {
            CVirtualAddressAllocator::FlushGpuVaTlb((CVirtualAddressAllocator *)a1, a2, v80, v89, v89 + (v32 << 12));
            v80 = v85[0];
          }
          else if ( a7 == 2 )
          {
            *v94 = 1;
          }
        }
        else
        {
          v81 = a2;
        }
        if ( BYTE3(v98[5]) )
        {
          VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(*(VIDMM_GLOBAL **)(a1 + 96), v81, v80);
          VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(
            *(VIDMM_PROCESS **)(a1 + 104),
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 24LL) + 240LL),
            0);
        }
        if ( (int)v56 < 0 )
        {
          *(_DWORD *)(a3 + 72) |= 0x1000u;
        }
        else
        {
          v82 = 1024;
          if ( (*(_BYTE *)(*(_QWORD *)(a1 + 96) + 37225LL) & 0x20) != 0 && *(_QWORD *)(a4 + 16) != *(_QWORD *)(a3 + 112) )
            v82 = 4096;
          *(_DWORD *)(a3 + 72) |= v82;
        }
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v97);
        return (unsigned int)v56;
      case 0xFFFFFFFF:
        goto LABEL_57;
    }
    v71 = GetVidMmGlobalAllocFromOwner(*(_DWORD *)(a3 + 72) & 0xF, *(_QWORD *)(a3 + 64));
    if ( a10 == 2 )
      goto LABEL_74;
    if ( a10 != 1 )
    {
      if ( (_WORD)v89 || (*(_BYTE *)(v21 + 1086) & 0x20) == 0 || (v72 & 0xF) != 0 || *(_WORD *)(a3 + 120) )
        goto LABEL_75;
      if ( !v65 )
      {
        if ( !*(_WORD *)(a4 + 56)
          && (*(_DWORD *)(a1 + 152) & 4) == 0
          && v71
          && (*(_DWORD *)(v71 + 24) & 0x10000000) != 0 )
        {
LABEL_74:
          BYTE12(v98[4]) = 1;
        }
LABEL_75:
        v73 = (32 * (v65 & 0x1F | ((unsigned __int64)(a5 & 0x3F) << 6))) | 1;
        v70 = v88;
        *(_QWORD *)&v98[0] = v73;
        if ( (*v88 & 0x40) != 0
          && (!v71 || (**(_DWORD **)(v71 + 384) & 0x80u) == 0)
          && (*(_DWORD *)(a1 + 152) & 4) == 0
          && (*(_DWORD *)(a4 + 44) & 1) != 0
          && (v65 || (*v88 & 0x800) != 0 && *(_BYTE *)(*(_QWORD *)(a1 + 96) + 36259LL)) )
        {
          LOBYTE(v98[5]) = 1;
        }
        if ( (*v88 & 0x10) != 0 && (v59 == 2 || v59 == 7 || v71 && (**(_DWORD **)(v71 + 384) & 4) != 0) )
        {
          v73 = (32 * (v65 & 0x1F | ((unsigned __int64)(a5 & 0x3F) << 6))) | 5;
          *(_QWORD *)&v98[0] = v73;
        }
        v63 = 1;
        if ( (*v88 & 1) != 0 && (*(_BYTE *)(a3 + 96) & 1) == 0 )
        {
          v73 |= 8u;
          *(_QWORD *)&v98[0] = v73;
        }
        if ( (*v88 & 2) != 0 && (*(_BYTE *)(a3 + 96) & 2) == 0 )
          *(_QWORD *)&v98[0] = v73 | 0x10;
        goto LABEL_58;
      }
      v74 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 36480LL) + 8LL * *(_QWORD *)v85)
                                  + 2280LL)
                      + 8LL * (unsigned int)(v65 - 1));
      v75 = v74 + 132;
      if ( !v74 )
        v75 = 124;
      if ( *(_DWORD *)v75 == 0x10000 && !*(_WORD *)(a4 + 56) )
      {
        v76 = BYTE12(v98[4]);
        if ( (v32 & 0xF) == 0 )
          v76 = 1;
        BYTE12(v98[4]) = v76;
      }
      if ( !v71 )
        goto LABEL_75;
      v77 = *(_DWORD *)(*(_QWORD *)v71 + 32LL);
      if ( v77 )
      {
        if ( !(_WORD)v77 )
          goto LABEL_75;
      }
    }
    BYTE12(v98[4]) = 0;
    goto LABEL_75;
  }
  WdLogSingleEntry1(1, v56);
  WdLogGlobalForLineNumber = 4262;
  DxgkLogInternalTriageEvent(
    v57,
    0x40000,
    v58,
    (unsigned int)L"RecommitGpuVirtualAddresses failed. Status=0x%.8x",
    v56,
    0,
    0,
    0);
  return (unsigned int)v56;
}

```

## disassembly

```asm
0x140099c04  push    rbp
0x140099c06  push    rbx
0x140099c07  push    rsi
0x140099c08  push    rdi
0x140099c09  push    r12
0x140099c0b  push    r13
0x140099c0d  push    r14
0x140099c0f  push    r15
0x140099c11  lea     rbp, [rsp-58h]
0x140099c16  sub     rsp, 158h
0x140099c1d  mov     rax, cs:__security_cookie
0x140099c24  xor     rax, rsp
0x140099c27  mov     [rbp+90h+var_50], rax
0x140099c2b  mov     r11, [rbp+90h+arg_40]
0x140099c32  mov     rsi, rcx
0x140099c35  mov     ecx, [r8+48h]
0x140099c39  mov     rdi, r8
0x140099c3c  mov     r10d, ecx
0x140099c3f  mov     [rsp+190h+var_128], rdx
0x140099c44  mov     edx, [rbp+90h+arg_28]
0x140099c4a  mov     r14, r9
0x140099c4d  mov     r8, [rsi+60h]
0x140099c51  xor     r12d, r12d
0x140099c54  mov     r9, [rbp+90h+arg_38]
0x140099c5b  mov     ebx, 1
0x140099c60  shr     r10d, 4
0x140099c64  and     r10d, 3Fh
0x140099c68  mov     [rsp+190h+var_140], edx
0x140099c6c  mov     rax, [r8+8E80h]
0x140099c73  mov     [rsp+190h+var_118], r9
0x140099c78  mov     [rbp+90h+var_E8], r11
0x140099c7c  mov     qword ptr [rsp+190h+var_138], r10
0x140099c81  mov     r13, [rax+r10*8]
0x140099c85  bt      ecx, 0Bh
0x140099c89  jb      loc_140099DF1
0x140099c8f  mov     al, [r13+43Ch]
0x140099c96  test    al, 10h
0x140099c98  jz      loc_140099D27
0x140099c9e  mov     rdx, [r8+18h]
0x140099ca2  mov     rcx, [rsi+68h]
0x140099ca6  mov     edx, [rdx+0F0h]; unsigned int
0x140099cac  mov     rcx, [rcx+48h]; this
0x140099cb0  call    ?GetRenderAdapterInfo@DXGPROCESS@@QEBAPEAUDXGPROCESS_RENDER_ADAPTER_INFO@@I@Z; DXGPROCESS::GetRenderAdapterInfo(uint)
0x140099cb5  mov     r8b, [rdi+60h]
0x140099cb9  lea     rdx, [r14+28h]
0x140099cbd  mov     r9, [r14+8]; unsigned __int64
0x140099cc1  not     r8b
0x140099cc4  and     r8b, bl
0x140099cc7  mov     rcx, [rax+50h]
0x140099ccb  mov     [rsp+190h+var_158], r8b; bool
0x140099cd0  mov     r8, [rax+28h]; struct _IOMMU_DMA_DOMAIN *
0x140099cd4  mov     [rsp+190h+var_160], rdx; struct _DXGK_ADL *
0x140099cd9  mov     r10, [rcx+10h]
0x140099cdd  mov     rcx, [r14+38h]
0x140099ce1  mov     rdx, [r14+18h]
0x140099ce5  mov     [rsp+190h+var_168], rcx; unsigned __int64
0x140099cea  mov     rcx, [r10+0E0h]; struct SYSMM_ADAPTER *
0x140099cf1  mov     [rsp+190h+var_170], rdx; unsigned __int64
0x140099cf6  mov     edx, [rsp+190h+var_138]; unsigned int
0x140099cfa  call    ?SysMmMapLogicalAddressRange@@YAJPEAUSYSMM_ADAPTER@@IPEAU_IOMMU_DMA_DOMAIN@@_K22PEBU_DXGK_ADL@@_N@Z; SysMmMapLogicalAddressRange(SYSMM_ADAPTER *,uint,_IOMMU_DMA_DOMAIN *,unsigned __int64,unsigned __int64,unsigned __int64,_DXGK_ADL const *,bool)
0x140099cff  movsxd  r15, eax
0x140099d02  test    eax, eax
0x140099d04  jns     loc_140099DDA
0x140099d0a  mov     rdx, r15
0x140099d0d  mov     ecx, ebx
0x140099d0f  call    cs:__imp_WdLogSingleEntry1
0x140099d16  nop     dword ptr [rax+rax+00h]
0x140099d1b  mov     cs:WdLogGlobalForLineNumber, 0FCCh
0x140099d25  jmp     short loc_140099D91
0x140099d27  test    al, 20h
0x140099d29  jz      loc_140099DF1
0x140099d2f  mov     dl, [rdi+60h]
0x140099d32  lea     rax, [r14+28h]
0x140099d36  mov     rcx, [r8+18h]
0x140099d3a  not     dl
0x140099d3c  mov     r9, [r14+8]; unsigned __int64
0x140099d40  and     dl, bl
0x140099d42  mov     [rsp+190h+var_158], dl; bool
0x140099d46  xor     r8d, r8d; struct _IOMMU_DMA_DOMAIN *
0x140099d49  mov     [rsp+190h+var_160], rax; struct _DXGK_ADL *
0x140099d4e  mov     edx, r10d; unsigned int
0x140099d51  mov     rax, [r14+38h]
0x140099d55  mov     rcx, [rcx+0E0h]; struct SYSMM_ADAPTER *
0x140099d5c  mov     [rsp+190h+var_168], rax; unsigned __int64
0x140099d61  mov     rax, [r14+18h]
0x140099d65  mov     [rsp+190h+var_170], rax; unsigned __int64
0x140099d6a  call    ?SysMmMapLogicalAddressRange@@YAJPEAUSYSMM_ADAPTER@@IPEAU_IOMMU_DMA_DOMAIN@@_K22PEBU_DXGK_ADL@@_N@Z; SysMmMapLogicalAddressRange(SYSMM_ADAPTER *,uint,_IOMMU_DMA_DOMAIN *,unsigned __int64,unsigned __int64,unsigned __int64,_DXGK_ADL const *,bool)
0x140099d6f  movsxd  r15, eax
0x140099d72  test    eax, eax
0x140099d74  jns     short loc_140099DDA
0x140099d76  mov     rdx, r15
0x140099d79  mov     ecx, ebx
0x140099d7b  call    cs:__imp_WdLogSingleEntry1
0x140099d82  nop     dword ptr [rax+rax+00h]
0x140099d87  mov     cs:WdLogGlobalForLineNumber, 0FE1h
0x140099d91  mov     qword ptr [rsp+190h+var_158], r12
0x140099d96  lea     r9, aSysmmmaplogica; "SysMmMapLogicalAddressRange failed: 0x%"...
0x140099d9d  mov     [rsp+190h+var_160], r12
0x140099da2  mov     edx, 40000h
0x140099da7  mov     [rsp+190h+var_168], r12
0x140099dac  mov     [rsp+190h+var_170], r15
0x140099db1  call    DxgkLogInternalTriageEvent
0x140099db6  mov     eax, r15d
0x140099db9  mov     rcx, [rbp+90h+var_50]
0x140099dbd  xor     rcx, rsp; StackCookie
0x140099dc0  call    __security_check_cookie
0x140099dc5  add     rsp, 158h
0x140099dcc  pop     r15
0x140099dce  pop     r14
0x140099dd0  pop     r13
0x140099dd2  pop     r12
0x140099dd4  pop     rdi
0x140099dd5  pop     rsi
0x140099dd6  pop     rbx
0x140099dd7  pop     rbp
0x140099dd8  retn
0x140099dda  mov     r11, [rbp+90h+var_E8]
0x140099dde  mov     r9, [rsp+190h+var_118]
0x140099de3  mov     edx, [rsp+190h+var_140]
0x140099de7  mov     r10, qword ptr [rsp+190h+var_138]
0x140099dec  bts     dword ptr [rdi+48h], 0Bh
0x140099df1  test    byte ptr [r13+43Ch], 4
0x140099df9  jnz     short loc_140099DFF
0x140099dfb  xor     eax, eax
0x140099dfd  jmp     short loc_140099DB9
0x140099dff  cmp     [rbp+90h+arg_30], 2
0x140099e06  jnz     short loc_140099E0B
0x140099e08  mov     [r11], r12b
0x140099e0b  mov     rbx, [rbp+90h+arg_50]
0x140099e12  mov     [r9], r12
0x140099e15  mov     rax, [r14+8]
0x140099e19  mov     r12, [r14+18h]
0x140099e1d  mov     r15, rax
0x140099e20  shr     r15, 0Ch
0x140099e24  shr     r12, 0Ch
0x140099e28  mov     [rbp+90h+var_110], rax
0x140099e2c  test    rbx, rbx
0x140099e2f  jnz     short loc_140099E35
0x140099e31  lea     rbx, [r15+r12]
0x140099e35  cmp     rbx, r15
0x140099e38  ja      short loc_140099E92
0x140099e3a  mov     r8, r15
0x140099e3d  mov     rdx, rbx
0x140099e40  mov     ecx, 1
0x140099e45  call    cs:__imp_WdLogSingleEntry2
0x140099e4c  nop     dword ptr [rax+rax+00h]
0x140099e51  mov     qword ptr [rsp+190h+var_158], 0
0x140099e5a  lea     r9, aLastpageindexF; "LastPageIndex <= FirstPageIndex (%I64u "...
0x140099e61  mov     [rsp+190h+var_160], 0
0x140099e6a  mov     [rsp+190h+var_168], r15
0x140099e6f  mov     cs:WdLogGlobalForLineNumber, 1010h
0x140099e79  mov     edx, 40000h
0x140099e7e  mov     [rsp+190h+var_170], rbx
0x140099e83  call    DxgkLogInternalTriageEvent
0x140099e88  mov     eax, 0C000000Dh
0x140099e8d  jmp     loc_140099DB9
0x140099e92  mov     r8, [rsi+10h]
0x140099e96  shr     r8, 0Ch
0x140099e9a  cmp     rbx, r8
0x140099e9d  jbe     short loc_140099EE5
0x140099e9f  mov     rdx, rbx
0x140099ea2  mov     ecx, 1
0x140099ea7  call    cs:__imp_WdLogSingleEntry2
0x140099eae  nop     dword ptr [rax+rax+00h]
0x140099eb3  mov     qword ptr [rsp+190h+var_158], 0
0x140099ebc  lea     r9, aLastpageindexM; "LastPageIndex >= m_VirtualAddressSize ("...
0x140099ec3  mov     cs:WdLogGlobalForLineNumber, 1019h
0x140099ecd  mov     rax, [rsi+10h]
0x140099ed1  shr     rax, 0Ch
0x140099ed5  mov     [rsp+190h+var_160], 0
0x140099ede  mov     [rsp+190h+var_168], rax
0x140099ee3  jmp     short loc_140099E79
0x140099ee5  mov     eax, [rdi+48h]
0x140099ee8  mov     rcx, r10
0x140099eeb  test    byte ptr [rdi+60h], 4
0x140099eef  mov     r15, [rsi+80h]
0x140099ef6  mov     r9, [r13+440h]
0x140099efd  mov     [rbp+90h+var_108], eax
0x140099f00  mov     rax, [rdi+40h]
0x140099f04  mov     [rbp+90h+var_F0], rax
0x140099f08  mov     rax, [r14+20h]
0x140099f0c  mov     [rbp+90h+var_D8], rax
0x140099f10  mov     eax, 0FFFFFFFEh
0x140099f15  cmovz   eax, edx
0x140099f18  mov     [rsp+190h+var_120], r9
0x140099f1d  shl     rcx, 5
0x140099f21  add     r15, rcx
0x140099f24  mov     dword ptr [rbp+90h+var_E0], eax
0x140099f27  mov     r8, [r15]
0x140099f2a  mov     [rbp+90h+var_F8], r8
0x140099f2e  test    r8, r8
0x140099f31  jz      short loc_140099F3E
0x140099f33  mov     eax, [r8]
0x140099f36  test    al, 8
0x140099f38  jz      loc_14009A1C8
0x140099f3e  mov     eax, [r13+434h]
0x140099f45  mov     edx, [r15+10h]
0x140099f49  mov     [rsp+190h+var_130], edx
0x140099f4d  lea     rcx, [rax+rax*2]
0x140099f51  lea     rax, [rbx-1]
0x140099f55  add     rcx, rcx
0x140099f58  mov     rbx, [r13+rcx*8+2F0h]
0x140099f60  mov     rcx, [r13+rcx*8+2F8h]
0x140099f68  and     rbx, rax
0x140099f6b  shr     rbx, cl
0x140099f6e  inc     ebx
0x140099f70  cmp     ebx, edx
0x140099f72  ja      short loc_140099F7D
0x140099f74  test    r8, r8
0x140099f77  jnz     loc_14009A1C8
0x140099f7d  test    r8, r8
0x140099f80  jz      short loc_140099FD9
0x140099f82  mov     eax, [rsi+98h]
0x140099f88  test    al, 4
0x140099f8a  jz      short loc_140099FD9
0x140099f8c  mov     ecx, 1
0x140099f91  call    cs:__imp_WdLogSingleEntry0
0x140099f98  nop     dword ptr [rax+rax+00h]
0x140099f9d  xor     ecx, ecx
0x140099f9f  lea     r9, aCannotGrowTheR; "Cannot grow the root page directory of "...
0x140099fa6  mov     qword ptr [rsp+190h+var_158], rcx
0x140099fab  mov     eax, 1041h
0x140099fb0  mov     [rsp+190h+var_160], rcx
0x140099fb5  mov     edx, 40000h
0x140099fba  mov     [rsp+190h+var_168], rcx
0x140099fbf  mov     [rsp+190h+var_170], rax
0x140099fc4  mov     cs:WdLogGlobalForLineNumber, eax
0x140099fca  call    DxgkLogInternalTriageEvent
0x140099fcf  mov     eax, 0C0000001h
0x140099fd4  jmp     loc_140099DB9
0x140099fd9  cmp     dword ptr [r9+10h], 2
0x140099fde  mov     eax, edx
0x140099fe0  mov     ecx, [r15+14h]
0x140099fe4  mov     edx, ecx
0x140099fe6  mov     [rsp+190h+var_140], ecx
0x140099fea  jnz     short loc_14009A01F
0x140099fec  mov     [r15+10h], ebx
0x140099ff0  lea     rdx, [rbp+90h+var_100]; struct _DXGKARG_GETROOTPAGETABLESIZE *
0x140099ff4  mov     rcx, [rsi+60h]
0x140099ff8  mov     [rbp+90h+var_100.NumberOfPte], ebx
0x140099ffb  mov     [rbp+90h+var_100.PhysicalAdapterIndex], r10d
0x140099fff  mov     rcx, [rcx+10h]; this
0x14009a003  call    ?DdiGetRootPageTableSize@ADAPTER_RENDER@@QEAA_KPEAU_DXGKARG_GETROOTPAGETABLESIZE@@@Z; ADAPTER_RENDER::DdiGetRootPageTableSize(_DXGKARG_GETROOTPAGETABLESIZE *)
0x14009a008  mov     ecx, [rsp+190h+var_140]
0x14009a00c  mov     rdx, rax
0x14009a00f  mov     r10, qword ptr [rsp+190h+var_138]
0x14009a014  mov     [r15+14h], eax
0x14009a018  mov     eax, [rbp+90h+var_100.NumberOfPte]
0x14009a01b  mov     [r15+10h], eax
0x14009a01f  cmp     eax, ebx
0x14009a021  jb      loc_14009A62D
0x14009a027  cmp     edx, ecx
0x14009a029  jb      loc_14009A62D
0x14009a02f  mov     r8d, [r13+434h]; unsigned int
0x14009a036  mov     edx, r10d; unsigned int
0x14009a039  mov     rcx, rsi; struct CVirtualAddressAllocator *
0x14009a03c  call    ?CreatePageDirectory@@YAPEAVVIDMM_PAGE_DIRECTORY@@PEAVCVirtualAddressAllocator@@II@Z; CreatePageDirectory(CVirtualAddressAllocator *,uint,uint)
0x14009a041  xor     ebx, ebx
0x14009a043  mov     [r15], rax
0x14009a046  mov     rcx, rax
0x14009a049  test    rax, rax
0x14009a04c  jnz     short loc_14009A0B5
0x14009a04e  lock inc cs:dword_1400867F4
0x14009a055  lea     ecx, [rax+6]
0x14009a058  call    cs:__imp_WdLogSingleEntry0
0x14009a05f  nop     dword ptr [rax+rax+00h]
0x14009a064  mov     qword ptr [rsp+190h+var_158], rbx
0x14009a069  lea     r9, aFailedToCreate_13; "Failed to create page directory"
0x14009a070  mov     eax, 1068h
0x14009a075  mov     [rsp+190h+var_160], rbx
0x14009a07a  mov     [rsp+190h+var_168], rbx
0x14009a07f  mov     edx, 40001h
0x14009a084  mov     cs:WdLogGlobalForLineNumber, eax
0x14009a08a  mov     [rsp+190h+var_170], rax
0x14009a08f  call    DxgkLogInternalTriageEvent
0x14009a094  mov     rax, [rbp+90h+var_F8]
0x14009a098  mov     [r15], rax
0x14009a09b  mov     eax, [rsp+190h+var_130]
0x14009a09f  mov     [r15+10h], eax
0x14009a0a3  mov     eax, [rsp+190h+var_140]
0x14009a0a7  mov     [r15+14h], eax
0x14009a0ab  mov     eax, 0C0000017h
0x14009a0b0  jmp     loc_140099DB9
0x14009a0b5  mov     eax, [rsi+98h]
0x14009a0bb  test    al, 4
0x14009a0bd  jz      short loc_14009A0C3
0x14009a0bf  bts     dword ptr [rcx], 14h
0x14009a0c3  cmp     [rbp+90h+var_F8], rbx
0x14009a0c7  jz      loc_14009A1C8
0x14009a0cd  mov     rax, [rsi+60h]
0x14009a0d1  mov     r8b, 1; bool
0x14009a0d4  mov     rcx, [rsi+68h]; this
0x14009a0d8  mov     rdx, [rax+18h]
0x14009a0dc  mov     edx, [rdx+0F0h]; unsigned int
0x14009a0e2  call    ?SuspendResumeProcessGpuMmuContexts@VIDMM_PROCESS@@QEAAXI_N@Z; VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(uint,bool)
0x14009a0e7  mov     eax, [rsp+190h+var_130]
0x14009a0eb  xor     r9d, r9d; unsigned __int64
0x14009a0ee  mov     ebx, [r15+10h]
0x14009a0f2  mov     r8, rsi; struct CVirtualAddressAllocator *
0x14009a0f5  mov     rdx, [rsp+190h+var_128]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
  ... truncated ...
```
