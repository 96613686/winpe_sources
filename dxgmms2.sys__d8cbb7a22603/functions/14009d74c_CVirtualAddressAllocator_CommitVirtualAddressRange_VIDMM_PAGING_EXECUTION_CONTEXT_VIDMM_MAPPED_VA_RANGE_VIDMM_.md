# CVirtualAddressAllocator::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_MAPPED_VA_RANGE *,VIDMM_COMMIT_VA_PACKET const *,uint,uint,VIDMM_FLUSH_TLB_MODE,VIDMM_ALLOC * *,bool *,VIDMM_PAGESIZEUSAGE,unsigned __int64)

- ea: `0x14009d74c`
- end: `0x14009e1f8`
- name: `?CommitVirtualAddressRange@CVirtualAddressAllocator@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_MAPPED_VA_RANGE@@PEBUVIDMM_COMMIT_VA_PACKET@@IIW4VIDMM_FLUSH_TLB_MODE@@PEAPEAUVIDMM_ALLOC@@PEA_NW4VIDMM_PAGESIZEUSAGE@@_K@Z`
- size: `2732`
- prototype: ``
- caller_count: `12`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003aa30`
- `0x1400430ac`
- `0x140099714`
- `0x14009b674`
- `0x14009d524`
- `0x14009edf0`
- `0x1400a0648`
- `0x1400a2698`
- `0x1400a8f0c`
- `0x1400bd6ac`
- `0x1400c220c`
- `0x1400d782c`

## callees

- `0x140004268`
- `0x14000a6d0`
- `0x1400120fc`
- `0x14002bb3c`
- `0x14002bddc`
- `0x14002eebc`
- `0x140031b20`
- `0x14003dfe0`
- `0x14003fb3c`
- `0x140042ad0`
- `0x140058f50`
- `0x140059380`
- `0x140099e9c`
- `0x14009d74c`
- `0x14009ecf4`
- `0x14009ffa0`
- `0x1400a0648`
- `0x14010b070`
- `0x140112580`
- `0x140112c58`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14009d98d`
- `watchdog!WdLogSingleEntry2` at `0x14009d9ef`
- `watchdog!WdLogSingleEntry2` at `0x14009d98d`
- `watchdog!WdLogSingleEntry2` at `0x14009d9ef`
- `watchdog!WdLogSingleEntry5` at `0x14009e1e2`
- `watchdog!WdLogSingleEntry5` at `0x14009e1e2`
- `watchdog!WdLogSingleEntry0` at `0x14009dad9`
- `watchdog!WdLogSingleEntry0` at `0x14009dba0`
- `watchdog!WdLogSingleEntry0` at `0x14009dad9`
- `watchdog!WdLogSingleEntry0` at `0x14009dba0`
- `watchdog!WdLogSingleEntry1` at `0x14009d857`
- `watchdog!WdLogSingleEntry1` at `0x14009d8c3`
- `watchdog!WdLogSingleEntry1` at `0x14009dccc`
- `watchdog!WdLogSingleEntry1` at `0x14009e17e`
- `watchdog!WdLogSingleEntry1` at `0x14009d857`
- `watchdog!WdLogSingleEntry1` at `0x14009d8c3`
- `watchdog!WdLogSingleEntry1` at `0x14009dccc`
- `watchdog!WdLogSingleEntry1` at `0x14009e17e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14009e1bf`

## string_xrefs

- `0x14009dae7`: `Cannot grow the root page directory of the paging process`
- `0x14009dce9`: `RecommitGpuVirtualAddresses failed. Status=0x%.8x`
- `0x14009dbb1`: `Failed to create page directory`

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
  v22 = *(_BYTE *)(v21 + 1348);
  if ( (v22 & 0x10) != 0 )
  {
    RenderAdapterInfo = DXGPROCESS::GetRenderAdapterInfo(
                          *(DXGPROCESS **)(*(_QWORD *)(a1 + 104) + 80LL),
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
  if ( (*(_BYTE *)(v21 + 1348) & 4) == 0 )
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
  v40 = *(_DWORD **)(v21 + 1352);
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
  v44 = (((v30 - 1) & *(_QWORD *)(v21 + 48LL * *(unsigned int *)(v21 + 1340) + 1016)) >> *(_QWORD *)(v21 + 48LL * *(unsigned int *)(v21 + 1340) + 1024))
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
    WdLogSingleEntry5(0, 270, 72, a1, v42, v44);
    WdLogGlobalForLineNumber = 227;
    JUMPOUT(0x14009E1F8LL);
  }
  PageDirectory = CreatePageDirectory((struct CVirtualAddressAllocator *)a1, v19, *(_DWORD *)(v21 + 1340));
  *(_QWORD *)v42 = PageDirectory;
  if ( !PageDirectory )
  {
    _InterlockedIncrement(&dword_1400877D4);
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
    if ( byte_140087202 < 0 )
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
    if ( (*(_BYTE *)(v21 + 1350) & 8) != 0 )
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
          if ( (*(_BYTE *)(v21 + 1350) & 8) != 0 )
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
        if ( byte_140087202 < 0 )
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
      if ( (_WORD)v89 || (*(_BYTE *)(v21 + 1350) & 0x20) == 0 || (v72 & 0xF) != 0 || *(_WORD *)(a3 + 120) )
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
          && (!v71 || (**(_DWORD **)(v71 + 392) & 0x80u) == 0)
          && (*(_DWORD *)(a1 + 152) & 4) == 0
          && (*(_DWORD *)(a4 + 44) & 1) != 0
          && (v65 || (*v88 & 0x800) != 0 && *(_BYTE *)(*(_QWORD *)(a1 + 96) + 36259LL)) )
        {
          LOBYTE(v98[5]) = 1;
        }
        if ( (*v88 & 0x10) != 0 && (v59 == 2 || v59 == 7 || v71 && (**(_DWORD **)(v71 + 392) & 4) != 0) )
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
                                  + 2544LL)
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
0x14009d74c  push    rbp
0x14009d74e  push    rbx
0x14009d74f  push    rsi
0x14009d750  push    rdi
0x14009d751  push    r12
0x14009d753  push    r13
0x14009d755  push    r14
0x14009d757  push    r15
0x14009d759  lea     rbp, [rsp-58h]
0x14009d75e  sub     rsp, 158h
0x14009d765  mov     rax, cs:__security_cookie
0x14009d76c  xor     rax, rsp
0x14009d76f  mov     [rbp+90h+var_50], rax
0x14009d773  mov     r11, [rbp+90h+arg_40]
0x14009d77a  mov     rsi, rcx
0x14009d77d  mov     ecx, [r8+48h]
0x14009d781  mov     rdi, r8
0x14009d784  mov     r10d, ecx
0x14009d787  mov     [rsp+190h+var_128], rdx
0x14009d78c  mov     edx, [rbp+90h+arg_28]
0x14009d792  mov     r14, r9
0x14009d795  mov     r8, [rsi+60h]
0x14009d799  xor     r12d, r12d
0x14009d79c  mov     r9, [rbp+90h+arg_38]
0x14009d7a3  mov     ebx, 1
0x14009d7a8  shr     r10d, 4
0x14009d7ac  and     r10d, 3Fh
0x14009d7b0  mov     [rsp+190h+var_140], edx
0x14009d7b4  mov     rax, [r8+8E80h]
0x14009d7bb  mov     [rsp+190h+var_118], r9
0x14009d7c0  mov     [rbp+90h+var_E8], r11
0x14009d7c4  mov     qword ptr [rsp+190h+var_138], r10
0x14009d7c9  mov     r13, [rax+r10*8]
0x14009d7cd  bt      ecx, 0Bh
0x14009d7d1  jb      loc_14009D939
0x14009d7d7  mov     al, [r13+544h]
0x14009d7de  test    al, 10h
0x14009d7e0  jz      loc_14009D86F
0x14009d7e6  mov     rdx, [r8+18h]
0x14009d7ea  mov     rcx, [rsi+68h]
0x14009d7ee  mov     edx, [rdx+0F0h]; unsigned int
0x14009d7f4  mov     rcx, [rcx+50h]; this
0x14009d7f8  call    ?GetRenderAdapterInfo@DXGPROCESS@@QEBAPEAUDXGPROCESS_RENDER_ADAPTER_INFO@@I@Z; DXGPROCESS::GetRenderAdapterInfo(uint)
0x14009d7fd  mov     r8b, [rdi+60h]
0x14009d801  lea     rdx, [r14+28h]
0x14009d805  mov     r9, [r14+8]; unsigned __int64
0x14009d809  not     r8b
0x14009d80c  and     r8b, bl
0x14009d80f  mov     rcx, [rax+50h]
0x14009d813  mov     [rsp+190h+var_158], r8b; bool
0x14009d818  mov     r8, [rax+28h]; struct _IOMMU_DMA_DOMAIN *
0x14009d81c  mov     [rsp+190h+var_160], rdx; struct _DXGK_ADL *
0x14009d821  mov     r10, [rcx+10h]
0x14009d825  mov     rcx, [r14+38h]
0x14009d829  mov     rdx, [r14+18h]
0x14009d82d  mov     [rsp+190h+var_168], rcx; unsigned __int64
0x14009d832  mov     rcx, [r10+0E0h]; struct SYSMM_ADAPTER *
0x14009d839  mov     [rsp+190h+var_170], rdx; unsigned __int64
0x14009d83e  mov     edx, [rsp+190h+var_138]; unsigned int
0x14009d842  call    ?SysMmMapLogicalAddressRange@@YAJPEAUSYSMM_ADAPTER@@IPEAU_IOMMU_DMA_DOMAIN@@_K22PEBU_DXGK_ADL@@_N@Z; SysMmMapLogicalAddressRange(SYSMM_ADAPTER *,uint,_IOMMU_DMA_DOMAIN *,unsigned __int64,unsigned __int64,unsigned __int64,_DXGK_ADL const *,bool)
0x14009d847  movsxd  r15, eax
0x14009d84a  test    eax, eax
0x14009d84c  jns     loc_14009D922
0x14009d852  mov     rdx, r15
0x14009d855  mov     ecx, ebx
0x14009d857  call    cs:__imp_WdLogSingleEntry1
0x14009d85e  nop     dword ptr [rax+rax+00h]
0x14009d863  mov     cs:WdLogGlobalForLineNumber, 0FCCh
0x14009d86d  jmp     short loc_14009D8D9
0x14009d86f  test    al, 20h
0x14009d871  jz      loc_14009D939
0x14009d877  mov     dl, [rdi+60h]
0x14009d87a  lea     rax, [r14+28h]
0x14009d87e  mov     rcx, [r8+18h]
0x14009d882  not     dl
0x14009d884  mov     r9, [r14+8]; unsigned __int64
0x14009d888  and     dl, bl
0x14009d88a  mov     [rsp+190h+var_158], dl; bool
0x14009d88e  xor     r8d, r8d; struct _IOMMU_DMA_DOMAIN *
0x14009d891  mov     [rsp+190h+var_160], rax; struct _DXGK_ADL *
0x14009d896  mov     edx, r10d; unsigned int
0x14009d899  mov     rax, [r14+38h]
0x14009d89d  mov     rcx, [rcx+0E0h]; struct SYSMM_ADAPTER *
0x14009d8a4  mov     [rsp+190h+var_168], rax; unsigned __int64
0x14009d8a9  mov     rax, [r14+18h]
0x14009d8ad  mov     [rsp+190h+var_170], rax; unsigned __int64
0x14009d8b2  call    ?SysMmMapLogicalAddressRange@@YAJPEAUSYSMM_ADAPTER@@IPEAU_IOMMU_DMA_DOMAIN@@_K22PEBU_DXGK_ADL@@_N@Z; SysMmMapLogicalAddressRange(SYSMM_ADAPTER *,uint,_IOMMU_DMA_DOMAIN *,unsigned __int64,unsigned __int64,unsigned __int64,_DXGK_ADL const *,bool)
0x14009d8b7  movsxd  r15, eax
0x14009d8ba  test    eax, eax
0x14009d8bc  jns     short loc_14009D922
0x14009d8be  mov     rdx, r15
0x14009d8c1  mov     ecx, ebx
0x14009d8c3  call    cs:__imp_WdLogSingleEntry1
0x14009d8ca  nop     dword ptr [rax+rax+00h]
0x14009d8cf  mov     cs:WdLogGlobalForLineNumber, 0FE1h
0x14009d8d9  mov     qword ptr [rsp+190h+var_158], r12
0x14009d8de  lea     r9, aSysmmmaplogica; "SysMmMapLogicalAddressRange failed: 0x%"...
0x14009d8e5  mov     [rsp+190h+var_160], r12
0x14009d8ea  mov     edx, 40000h
0x14009d8ef  mov     [rsp+190h+var_168], r12
0x14009d8f4  mov     [rsp+190h+var_170], r15
0x14009d8f9  call    DxgkLogInternalTriageEvent
0x14009d8fe  mov     eax, r15d
0x14009d901  mov     rcx, [rbp+90h+var_50]
0x14009d905  xor     rcx, rsp; StackCookie
0x14009d908  call    __security_check_cookie
0x14009d90d  add     rsp, 158h
0x14009d914  pop     r15
0x14009d916  pop     r14
0x14009d918  pop     r13
0x14009d91a  pop     r12
0x14009d91c  pop     rdi
0x14009d91d  pop     rsi
0x14009d91e  pop     rbx
0x14009d91f  pop     rbp
0x14009d920  retn
0x14009d922  mov     r11, [rbp+90h+var_E8]
0x14009d926  mov     r9, [rsp+190h+var_118]
0x14009d92b  mov     edx, [rsp+190h+var_140]
0x14009d92f  mov     r10, qword ptr [rsp+190h+var_138]
0x14009d934  bts     dword ptr [rdi+48h], 0Bh
0x14009d939  test    byte ptr [r13+544h], 4
0x14009d941  jnz     short loc_14009D947
0x14009d943  xor     eax, eax
0x14009d945  jmp     short loc_14009D901
0x14009d947  cmp     [rbp+90h+arg_30], 2
0x14009d94e  jnz     short loc_14009D953
0x14009d950  mov     [r11], r12b
0x14009d953  mov     rbx, [rbp+90h+arg_50]
0x14009d95a  mov     [r9], r12
0x14009d95d  mov     rax, [r14+8]
0x14009d961  mov     r12, [r14+18h]
0x14009d965  mov     r15, rax
0x14009d968  shr     r15, 0Ch
0x14009d96c  shr     r12, 0Ch
0x14009d970  mov     [rbp+90h+var_110], rax
0x14009d974  test    rbx, rbx
0x14009d977  jnz     short loc_14009D97D
0x14009d979  lea     rbx, [r15+r12]
0x14009d97d  cmp     rbx, r15
0x14009d980  ja      short loc_14009D9DA
0x14009d982  mov     r8, r15
0x14009d985  mov     rdx, rbx
0x14009d988  mov     ecx, 1
0x14009d98d  call    cs:__imp_WdLogSingleEntry2
0x14009d994  nop     dword ptr [rax+rax+00h]
0x14009d999  mov     qword ptr [rsp+190h+var_158], 0
0x14009d9a2  lea     r9, aLastpageindexF; "LastPageIndex <= FirstPageIndex (%I64u "...
0x14009d9a9  mov     [rsp+190h+var_160], 0
0x14009d9b2  mov     [rsp+190h+var_168], r15
0x14009d9b7  mov     cs:WdLogGlobalForLineNumber, 1010h
0x14009d9c1  mov     edx, 40000h
0x14009d9c6  mov     [rsp+190h+var_170], rbx
0x14009d9cb  call    DxgkLogInternalTriageEvent
0x14009d9d0  mov     eax, 0C000000Dh
0x14009d9d5  jmp     loc_14009D901
0x14009d9da  mov     r8, [rsi+10h]
0x14009d9de  shr     r8, 0Ch
0x14009d9e2  cmp     rbx, r8
0x14009d9e5  jbe     short loc_14009DA2D
0x14009d9e7  mov     rdx, rbx
0x14009d9ea  mov     ecx, 1
0x14009d9ef  call    cs:__imp_WdLogSingleEntry2
0x14009d9f6  nop     dword ptr [rax+rax+00h]
0x14009d9fb  mov     qword ptr [rsp+190h+var_158], 0
0x14009da04  lea     r9, aLastpageindexM; "LastPageIndex >= m_VirtualAddressSize ("...
0x14009da0b  mov     cs:WdLogGlobalForLineNumber, 1019h
0x14009da15  mov     rax, [rsi+10h]
0x14009da19  shr     rax, 0Ch
0x14009da1d  mov     [rsp+190h+var_160], 0
0x14009da26  mov     [rsp+190h+var_168], rax
0x14009da2b  jmp     short loc_14009D9C1
0x14009da2d  mov     eax, [rdi+48h]
0x14009da30  mov     rcx, r10
0x14009da33  test    byte ptr [rdi+60h], 4
0x14009da37  mov     r15, [rsi+80h]
0x14009da3e  mov     r9, [r13+548h]
0x14009da45  mov     [rbp+90h+var_108], eax
0x14009da48  mov     rax, [rdi+40h]
0x14009da4c  mov     [rbp+90h+var_F0], rax
0x14009da50  mov     rax, [r14+20h]
0x14009da54  mov     [rbp+90h+var_D8], rax
0x14009da58  mov     eax, 0FFFFFFFEh
0x14009da5d  cmovz   eax, edx
0x14009da60  mov     [rsp+190h+var_120], r9
0x14009da65  shl     rcx, 5
0x14009da69  add     r15, rcx
0x14009da6c  mov     dword ptr [rbp+90h+var_E0], eax
0x14009da6f  mov     r8, [r15]
0x14009da72  mov     [rbp+90h+var_F8], r8
0x14009da76  test    r8, r8
0x14009da79  jz      short loc_14009DA86
0x14009da7b  mov     eax, [r8]
0x14009da7e  test    al, 8
0x14009da80  jz      loc_14009DD10
0x14009da86  mov     eax, [r13+53Ch]
0x14009da8d  mov     edx, [r15+10h]
0x14009da91  mov     [rsp+190h+var_130], edx
0x14009da95  lea     rcx, [rax+rax*2]
0x14009da99  lea     rax, [rbx-1]
0x14009da9d  add     rcx, rcx
0x14009daa0  mov     rbx, [r13+rcx*8+3F8h]
0x14009daa8  mov     rcx, [r13+rcx*8+400h]
0x14009dab0  and     rbx, rax
0x14009dab3  shr     rbx, cl
0x14009dab6  inc     ebx
0x14009dab8  cmp     ebx, edx
0x14009daba  ja      short loc_14009DAC5
0x14009dabc  test    r8, r8
0x14009dabf  jnz     loc_14009DD10
0x14009dac5  test    r8, r8
0x14009dac8  jz      short loc_14009DB21
0x14009daca  mov     eax, [rsi+98h]
0x14009dad0  test    al, 4
0x14009dad2  jz      short loc_14009DB21
0x14009dad4  mov     ecx, 1
0x14009dad9  call    cs:__imp_WdLogSingleEntry0
0x14009dae0  nop     dword ptr [rax+rax+00h]
0x14009dae5  xor     ecx, ecx
0x14009dae7  lea     r9, aCannotGrowTheR; "Cannot grow the root page directory of "...
0x14009daee  mov     qword ptr [rsp+190h+var_158], rcx
0x14009daf3  mov     eax, 1041h
0x14009daf8  mov     [rsp+190h+var_160], rcx
0x14009dafd  mov     edx, 40000h
0x14009db02  mov     [rsp+190h+var_168], rcx
0x14009db07  mov     [rsp+190h+var_170], rax
0x14009db0c  mov     cs:WdLogGlobalForLineNumber, eax
0x14009db12  call    DxgkLogInternalTriageEvent
0x14009db17  mov     eax, 0C0000001h
0x14009db1c  jmp     loc_14009D901
0x14009db21  cmp     dword ptr [r9+10h], 2
0x14009db26  mov     eax, edx
0x14009db28  mov     ecx, [r15+14h]
0x14009db2c  mov     edx, ecx
0x14009db2e  mov     [rsp+190h+var_140], ecx
0x14009db32  jnz     short loc_14009DB67
0x14009db34  mov     [r15+10h], ebx
0x14009db38  lea     rdx, [rbp+90h+var_100]; struct _DXGKARG_GETROOTPAGETABLESIZE *
0x14009db3c  mov     rcx, [rsi+60h]
0x14009db40  mov     [rbp+90h+var_100.NumberOfPte], ebx
0x14009db43  mov     [rbp+90h+var_100.PhysicalAdapterIndex], r10d
0x14009db47  mov     rcx, [rcx+10h]; this
0x14009db4b  call    ?DdiGetRootPageTableSize@ADAPTER_RENDER@@QEAA_KPEAU_DXGKARG_GETROOTPAGETABLESIZE@@@Z; ADAPTER_RENDER::DdiGetRootPageTableSize(_DXGKARG_GETROOTPAGETABLESIZE *)
0x14009db50  mov     ecx, [rsp+190h+var_140]
0x14009db54  mov     rdx, rax
0x14009db57  mov     r10, qword ptr [rsp+190h+var_138]
0x14009db5c  mov     [r15+14h], eax
0x14009db60  mov     eax, [rbp+90h+var_100.NumberOfPte]
0x14009db63  mov     [r15+10h], eax
0x14009db67  cmp     eax, ebx
0x14009db69  jb      loc_14009E175
0x14009db6f  cmp     edx, ecx
0x14009db71  jb      loc_14009E175
0x14009db77  mov     r8d, [r13+53Ch]; unsigned int
0x14009db7e  mov     edx, r10d; unsigned int
0x14009db81  mov     rcx, rsi; struct CVirtualAddressAllocator *
0x14009db84  call    ?CreatePageDirectory@@YAPEAVVIDMM_PAGE_DIRECTORY@@PEAVCVirtualAddressAllocator@@II@Z; CreatePageDirectory(CVirtualAddressAllocator *,uint,uint)
0x14009db89  xor     ebx, ebx
0x14009db8b  mov     [r15], rax
0x14009db8e  mov     rcx, rax
0x14009db91  test    rax, rax
0x14009db94  jnz     short loc_14009DBFD
0x14009db96  lock inc cs:dword_1400877D4
0x14009db9d  lea     ecx, [rax+6]
0x14009dba0  call    cs:__imp_WdLogSingleEntry0
0x14009dba7  nop     dword ptr [rax+rax+00h]
0x14009dbac  mov     qword ptr [rsp+190h+var_158], rbx
0x14009dbb1  lea     r9, aFailedToCreate_13; "Failed to create page directory"
0x14009dbb8  mov     eax, 1068h
0x14009dbbd  mov     [rsp+190h+var_160], rbx
0x14009dbc2  mov     [rsp+190h+var_168], rbx
0x14009dbc7  mov     edx, 40001h
0x14009dbcc  mov     cs:WdLogGlobalForLineNumber, eax
0x14009dbd2  mov     [rsp+190h+var_170], rax
0x14009dbd7  call    DxgkLogInternalTriageEvent
0x14009dbdc  mov     rax, [rbp+90h+var_F8]
0x14009dbe0  mov     [r15], rax
0x14009dbe3  mov     eax, [rsp+190h+var_130]
0x14009dbe7  mov     [r15+10h], eax
0x14009dbeb  mov     eax, [rsp+190h+var_140]
0x14009dbef  mov     [r15+14h], eax
0x14009dbf3  mov     eax, 0C0000017h
0x14009dbf8  jmp     loc_14009D901
0x14009dbfd  mov     eax, [rsi+98h]
0x14009dc03  test    al, 4
0x14009dc05  jz      short loc_14009DC0B
0x14009dc07  bts     dword ptr [rcx], 14h
0x14009dc0b  cmp     [rbp+90h+var_F8], rbx
0x14009dc0f  jz      loc_14009DD10
0x14009dc15  mov     rax, [rsi+60h]
0x14009dc19  mov     r8b, 1; bool
0x14009dc1c  mov     rcx, [rsi+68h]; this
0x14009dc20  mov     rdx, [rax+18h]
0x14009dc24  mov     edx, [rdx+0F0h]; unsigned int
0x14009dc2a  call    ?SuspendResumeProcessGpuMmuContexts@VIDMM_PROCESS@@QEAAXI_N@Z; VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(uint,bool)
0x14009dc2f  mov     eax, [rsp+190h+var_130]
0x14009dc33  xor     r9d, r9d; unsigned __int64
0x14009dc36  mov     ebx, [r15+10h]
0x14009dc3a  mov     r8, rsi; struct CVirtualAddressAllocator *
0x14009dc3d  mov     rdx, [rsp+190h+var_128]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
  ... truncated ...
```
