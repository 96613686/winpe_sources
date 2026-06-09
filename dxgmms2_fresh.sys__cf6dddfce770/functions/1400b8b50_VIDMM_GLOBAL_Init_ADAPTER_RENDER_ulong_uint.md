# VIDMM_GLOBAL::Init(ADAPTER_RENDER *,ulong,uint)

- ea: `0x1400b8b50`
- end: `0x1400b961f`
- name: `?Init@VIDMM_GLOBAL@@QEAAJPEAVADAPTER_RENDER@@KI@Z`
- size: `2767`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this, struct ADAPTER_RENDER *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c2a08`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002bf50`
- `0x14002c680`
- `0x14002e760`
- `0x14002ed58`
- `0x14002f528`
- `0x14002fbe8`
- `0x140046a78`
- `0x140046b50`
- `0x140046c24`
- `0x140058cc8`
- `0x140058f50`
- `0x1400b49a0`
- `0x1400b8b50`
- `0x1400b9628`
- `0x1400b9740`
- `0x1400be13c`
- `0x1400c3a64`
- `0x1400c5eb4`
- `0x1400c6044`
- `0x1400c9ef8`
- `0x1400ca46c`
- `0x1400ca8d4`
- `0x1400cb1e8`
- `0x1400d1928`
- `0x1400d283c`
- `0x140102cf4`
- `0x140103074`

## import_xrefs

- `ntoskrnl!KeInitializeTimer` at `0x1400b939c`
- `ntoskrnl!KeInitializeTimer` at `0x1400b939c`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1400b93b9`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1400b93b9`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400b9523`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400b9523`
- `watchdog!WdLogSingleEntry3` at `0x1400b957d`
- `watchdog!WdLogSingleEntry3` at `0x1400b957d`
- `watchdog!WdLogSingleEntry2` at `0x1400b91a7`
- `watchdog!WdLogSingleEntry2` at `0x1400b9420`
- `watchdog!WdLogSingleEntry2` at `0x1400b91a7`
- `watchdog!WdLogSingleEntry2` at `0x1400b9420`
- `watchdog!WdLogSingleEntry0` at `0x1400b8dd3`
- `watchdog!WdLogSingleEntry0` at `0x1400b8ec2`
- `watchdog!WdLogSingleEntry0` at `0x1400b8f83`
- `watchdog!WdLogSingleEntry0` at `0x1400b909e`
- `watchdog!WdLogSingleEntry0` at `0x1400b9298`
- `watchdog!WdLogSingleEntry0` at `0x1400b93d6`
- `watchdog!WdLogSingleEntry0` at `0x1400b8dd3`
- `watchdog!WdLogSingleEntry0` at `0x1400b8ec2`
- `watchdog!WdLogSingleEntry0` at `0x1400b8f83`
- `watchdog!WdLogSingleEntry0` at `0x1400b909e`
- `watchdog!WdLogSingleEntry0` at `0x1400b9298`
- `watchdog!WdLogSingleEntry0` at `0x1400b93d6`
- `watchdog!WdLogSingleEntry1` at `0x1400b8c3d`
- `watchdog!WdLogSingleEntry1` at `0x1400b8ff3`
- `watchdog!WdLogSingleEntry1` at `0x1400b92e8`
- `watchdog!WdLogSingleEntry1` at `0x1400b9368`
- `watchdog!WdLogSingleEntry1` at `0x1400b8c3d`
- `watchdog!WdLogSingleEntry1` at `0x1400b8ff3`
- `watchdog!WdLogSingleEntry1` at `0x1400b92e8`
- `watchdog!WdLogSingleEntry1` at `0x1400b9368`
- `dxgkrnl!DpiGetLocalNumaNode` at `0x1400b9553`
- `dxgkrnl!DpiGetLocalNumaNode` at `0x1400b9553`

## string_xrefs

- `0x1400b8de4`: `DMA remapping requires the driver to support the MapAperture2 paging buffer command`
- `0x1400b93e7`: `Failed to start the worker thread`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::Init(VIDMM_GLOBAL *this, struct ADAPTER_RENDER *a2, unsigned int a3, char a4)
{
  __int64 v5; // rax
  unsigned int v7; // r12d
  __int64 v9; // rbx
  char IsDrtEnabled; // al
  __int64 v11; // rdx
  __int64 v12; // r8
  char v13; // al
  unsigned __int8 v14; // cl
  unsigned int v15; // eax
  int v16; // ecx
  int v17; // r8d
  unsigned __int64 v19; // r13
  unsigned int v20; // ecx
  char v21; // al
  char v22; // cl
  unsigned __int8 IsGpuVaIoMmuGlobalSupported; // al
  char v24; // cl
  int v25; // ecx
  char v26; // al
  int v27; // ecx
  int v28; // r8d
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // ecx
  int v33; // r8d
  __int64 v34; // rax
  const wchar_t *v35; // r9
  __int64 v36; // r14
  __int64 v37; // rax
  __int64 v38; // rax
  int v39; // ecx
  int v40; // r8d
  __int64 v41; // rax
  const wchar_t *v42; // r9
  unsigned __int16 v43; // r15
  int v44; // eax
  ADAPTER_RENDER *v45; // rcx
  const struct DXGK_PHYSICALADAPTERINFO *v46; // r14
  const struct DXGADAPTER_GPUMMUCAPS *GpuMmuCaps; // r13
  VIDMM_PHYSICAL_ADAPTER *v48; // rax
  VIDMM_PHYSICAL_ADAPTER *v49; // rbx
  VIDMM_PHYSICAL_ADAPTER *v50; // rax
  int v51; // eax
  unsigned __int64 v52; // rdx
  bool v53; // al
  int v54; // eax
  CVirtualAddressAllocator *v55; // rax
  CVirtualAddressAllocator *v56; // rax
  int (*v57)(unsigned __int64, unsigned __int64, void *); // rdx
  int v58; // ecx
  int v59; // r8d
  const wchar_t *v60; // r9
  __int64 v61; // rax
  __int64 v62; // rcx
  unsigned __int64 v63; // rax
  int v64; // eax
  int v65; // ecx
  int v66; // r8d
  struct _RTL_BALANCED_NODE *v67; // rax
  VIDMM_PARTITION *v68; // r15
  int v69; // eax
  VIDMM_PARTITION **v70; // rax
  VIDMM_PARTITION *v71; // rcx
  VIDMM_PARTITION *v72; // rax
  unsigned __int16 i; // bx
  unsigned __int16 LocalNumaNode; // ax
  int v75; // ecx
  int v76; // r8d
  unsigned __int16 v77; // [rsp+50h] [rbp-30h]
  unsigned __int64 v79[3]; // [rsp+58h] [rbp-28h] BYREF

  *((_QWORD *)this + 2) = a2;
  v5 = *((_QWORD *)a2 + 2);
  *((_QWORD *)this + 3) = v5;
  v7 = a3;
  *((_DWORD *)this + 10) = a3;
  byte_1400875EC |= (*(_DWORD *)(v5 + 444) & 0x200) != 0;
  v9 = *((_QWORD *)this + 3);
  if ( a3 >= 0x6000 )
    *((_BYTE *)this + 37225) |= 2u;
  IsDrtEnabled = DxgkpIsDrtEnabled();
  v12 = *((_QWORD *)this + 3);
  v13 = *((_BYTE *)this + 37225) ^ (*((_BYTE *)this + 37225) ^ (IsDrtEnabled << 6)) & 0x40;
  *((_BYTE *)this + 37225) = v13;
  v14 = v13 ^ (v13 ^ (32 * *(_BYTE *)(v12 + 5168))) & 0x20;
  *((_BYTE *)this + 37225) = v14 ^ (v14 ^ (v14 >> 1)) & 0x10;
  *((_BYTE *)this + 37226) ^= (*(_BYTE *)(v12 + 5196) ^ *((_BYTE *)this + 37226)) & 1;
  v15 = *(_DWORD *)(v12 + 296);
  *((_DWORD *)this + 778) = v15;
  if ( v15 > 0x40 )
  {
    WdLogSingleEntry1(1, 64);
    WdLogGlobalForLineNumber = 1802;
    DxgkLogInternalTriageEvent(
      v16,
      0x40000,
      v17,
      (unsigned int)L"Total number of engine on logical adapter can't exceed %I64d",
      64,
      0,
      0,
      0);
    return 3221225485LL;
  }
  v19 = *((unsigned __int16 *)this + 1556);
  v20 = *(_DWORD *)(v9 + 2596);
  v77 = *((_WORD *)this + 1556);
  if ( (v20 & 0x20) != 0 )
  {
    v21 = *((_BYTE *)this + 37224) & 0xFD;
    LODWORD(v79[0]) = 0;
    v22 = v21 | (v20 >> 5) & 2;
    *((_BYTE *)this + 37224) = v22;
    *((_BYTE *)this + 37224) = v22 & 0xDF | (*(_DWORD *)(v9 + 2596) >> 2) & 0x20;
    SysMmQueryIommuState(*(const struct SYSMM_ADAPTER **)(v12 + 224), (union SYSMM_IOMMU_STATE *)v79);
    *((_BYTE *)this + 37224) = *((_BYTE *)this + 37224) & 0xFB | (4 * ((v79[0] & 4) != 0));
    IsGpuVaIoMmuGlobalSupported = DXGADAPTER::IsGpuVaIoMmuGlobalSupported(*((DXGADAPTER **)this + 3));
    v24 = *((_BYTE *)this + 37224) & 0xE7 | (IsGpuVaIoMmuGlobalSupported != 0 ? 8 : 0);
    LOBYTE(v11) = v24 | ((*((_BYTE *)this + 37224) & 6 | (IsGpuVaIoMmuGlobalSupported != 0 ? 8 : 0)) != 0 ? 0x10 : 0);
    *((_BYTE *)this + 37224) = v11;
    if ( (v24 & 0x20) != 0 )
    {
      if ( (VIDMM_GLOBAL::_Config & 0x20) != 0
        || (v25 = *(_DWORD *)(*((_QWORD *)this + 3) + 444LL), (v25 & 4) != 0)
        || (v26 = 64, (v25 & 8) != 0) )
      {
        v26 = 0;
      }
      *((_BYTE *)this + 37224) = v26 | v11 & 0xBF;
    }
    if ( v7 >= 0x5017 || (VIDMM_GLOBAL::_Config & 0x100) != 0 )
      *((_BYTE *)this + 37225) |= 1u;
  }
  LOBYTE(v11) = *((_BYTE *)this + 37224);
  if ( (v11 & 0xC) == 0 )
  {
    if ( (a4 & 1) != 0 )
    {
      *((_BYTE *)this + 36258) = 1;
      *((_BYTE *)this + 36260) = 1;
      *((_BYTE *)this + 36304) = 1;
    }
    if ( (a4 & 2) != 0 )
    {
      if ( (*(_DWORD *)(v9 + 2596) & 0x4000) == 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1861;
        DxgkLogInternalTriageEvent(
          v27,
          0x40000,
          v28,
          (unsigned int)L"DMA remapping requires the driver to support the MapAperture2 paging buffer command",
          1861,
          0,
          0,
          0);
        return 3221225485LL;
      }
      *((_BYTE *)this + 36259) = 1;
    }
  }
  *((_BYTE *)this + 736) = (*(_DWORD *)(v9 + 2592) & 0x20) == 0;
  *((_BYTE *)this + 37225) ^= (*((_BYTE *)this + 37225) ^ (8 * (*(_DWORD *)(v9 + 2596) >> 14))) & 8;
  if ( (v11 & 0x10) != 0 && dword_14008749C )
  {
    v29 = 256;
    if ( (unsigned int)dword_14008749C <= 0x10000 )
      v29 = 64;
    DXGK_LOG::Initialize((char *)this + 37328, v11, v29, (unsigned int)dword_14008749C, (unsigned int)dword_1400874A0);
    v30 = 48LL * (unsigned int)dword_1400874A4;
    if ( !is_mul_ok((unsigned int)dword_1400874A4, 0x30u) )
      v30 = -1;
    v31 = operator new[](v30, 842361174, 256);
    *((_QWORD *)this + 4670) = v31;
    if ( !v31 )
    {
      _InterlockedIncrement(&dword_140087860);
      WdLogSingleEntry0(6);
      v34 = 1904;
      v35 = L"Failed to allocate _PageMappingHistoryEntry";
LABEL_31:
      WdLogGlobalForLineNumber = v34;
      DxgkLogInternalTriageEvent(v32, 262145, v33, (_DWORD)v35, v34, 0, 0, 0);
      LODWORD(v36) = -1073741801;
      goto LABEL_101;
    }
  }
  if ( (*((_BYTE *)this + 37226) & 1) != 0 )
  {
    *(_OWORD *)v79 = 0;
    ADAPTER_RENDER::DdiIntelligentCarveoutQueryPreferences(
      a2,
      (struct _DXGKARG_FEATURE_INTELLIGENT_CARVEOUT_QUERY_PREFERENCES *)v79);
    if ( !(unsigned __int8)ValidateIntelligentCarveoutPreferences(v79) )
    {
      LODWORD(v36) = -1073741811;
      goto LABEL_101;
    }
    VidMmAdjustIntelligentCarveoutSize(v79[0]);
  }
  v37 = 8 * v19;
  if ( !is_mul_ok(v19, 8u) )
    v37 = -1;
  v38 = operator new[](v37, 808806742, 64);
  *((_QWORD *)this + 4560) = v38;
  if ( v38 )
  {
    v43 = 0;
    if ( (_WORD)v19 )
    {
      while ( 1 )
      {
        v45 = (ADAPTER_RENDER *)*((_QWORD *)this + 2);
        v46 = (const struct DXGK_PHYSICALADAPTERINFO *)(*(_QWORD *)(*((_QWORD *)this + 3) + 3120LL) + 352LL * v43);
        v79[0] = (unsigned __int64)v46;
        GpuMmuCaps = ADAPTER_RENDER::GetGpuMmuCaps(v45, v43);
        if ( (*((_BYTE *)this + 37225) & 0x20) != 0 )
        {
          v48 = (VIDMM_PHYSICAL_ADAPTER *)operator new(2760, 808806742, 64);
          v49 = v48;
          if ( v48 )
          {
            VIDMM_PHYSICAL_ADAPTER::VIDMM_PHYSICAL_ADAPTER(v48, this, v43, v46, GpuMmuCaps);
            *((_BYTE *)v49 + 1348) &= ~1u;
            *(_QWORD *)v49 = &VIDMM_PHYSICAL_ADAPTER_PBMM::`vftable';
          }
          else
          {
            v49 = 0;
          }
          if ( !v49 )
          {
LABEL_49:
            _InterlockedIncrement(&dword_140087848);
            WdLogSingleEntry0(6);
            v41 = 1982;
            v42 = L"Couldn't allocate VIDMM_PHYSICAL_ADAPTER";
            goto LABEL_40;
          }
        }
        else
        {
          v50 = (VIDMM_PHYSICAL_ADAPTER *)operator new(2680, 808806742, 64);
          v49 = v50;
          if ( !v50 )
            goto LABEL_49;
          VIDMM_PHYSICAL_ADAPTER::VIDMM_PHYSICAL_ADAPTER(v50, this, v43, v46, GpuMmuCaps);
          *((_BYTE *)v49 + 1348) |= 1u;
          *(_QWORD *)v49 = &VIDMM_PHYSICAL_ADAPTER_LEGACY::`vftable';
          *((_QWORD *)v49 + 334) = (char *)v49 + 2664;
          *((_QWORD *)v49 + 333) = (char *)v49 + 2664;
        }
        *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * v43) = v49;
        v51 = VidMmInitializePhysicalAdapter(v49);
        LODWORD(v36) = v51;
        if ( v51 < 0 )
          break;
        *((_DWORD *)this + 161) += *((_DWORD *)v49 + 232);
        if ( GpuMmuCaps )
          *((_BYTE *)this + 36256) &= (*((_BYTE *)GpuMmuCaps + 20) & 1) == 0;
        v52 = v79[0];
        LOWORD(v19) = v77;
        *((_BYTE *)this + 37225) = *((_BYTE *)this + 37225)
                                 & 0xFB
                                 ^ (*((_BYTE *)this + 37225) | (4 * (*(_DWORD *)(v79[0] + 16) >> 5)))
                                 & 4;
        *((_BYTE *)v49 + 1350) = *((_BYTE *)v49 + 1350) & 0xEF | (*(_BYTE *)(v52 + 50) != 0 ? 0x10 : 0);
        if ( ++v43 >= v77 )
        {
          v7 = a3;
          goto LABEL_42;
        }
      }
      WdLogSingleEntry2(3, v43, v51);
      WdLogGlobalForLineNumber = 1995;
      goto LABEL_101;
    }
LABEL_42:
    v44 = VIDMM_GLOBAL::InitializeForwardProgressMdl(this);
    LODWORD(v36) = v44;
    if ( v44 < 0 )
    {
      WdLogSingleEntry1(3, v44);
      WdLogGlobalForLineNumber = 2020;
      goto LABEL_101;
    }
    if ( dword_140087450 == 2 )
      v53 = (*(_DWORD *)(*((_QWORD *)this + 3) + 2580LL) & 4) != 0;
    else
      v53 = dword_140087450 == 1;
    *((_BYTE *)this + 3264) = v53;
    *((_QWORD *)this + 5161) = qword_140087560;
    VIDMM_GLOBAL::InitializePagingHistory(this, dword_14008740C);
    if ( (*((_BYTE *)this + 37224) & 0x10) != 0 )
    {
      v54 = v7 >= 0x5023 ? dword_1400874A8 : 4096 << *((_DWORD *)this + 9305);
      *((_DWORD *)this + 9325) = v54;
      LODWORD(v36) = VIDMM_PAGING_PROCESS::CreateVaAllocator((VIDMM_GLOBAL *)((char *)this + 36672), this);
      if ( (int)v36 < 0 )
        goto LABEL_101;
    }
    if ( DXGADAPTER::IsGpuVaIoMmuGlobalSupported(*((DXGADAPTER **)this + 3)) )
    {
      v55 = (CVirtualAddressAllocator *)operator new(160, 1265072196, 256);
      if ( v55 )
        v56 = CVirtualAddressAllocator::CVirtualAddressAllocator(v55);
      else
        v56 = 0;
      *((_QWORD *)this + 5134) = v56;
      if ( !v56 )
      {
        _InterlockedAdd(&dword_140087858, 1u);
        WdLogSingleEntry0(6);
        v34 = 2107;
        v35 = L"Failed to allocate CVirtualAddressAllocator";
        goto LABEL_31;
      }
      LODWORD(v36) = CVirtualAddressAllocator::InitializeVaAllocator(
                       v56,
                       1LL << *((_DWORD *)this + 9304),
                       *((unsigned int *)this + 9325),
                       this,
                       0);
      if ( (int)v36 < 0 )
      {
        WdLogSingleEntry1(1, *((_QWORD *)this + 5134));
        WdLogGlobalForLineNumber = 2122;
        v60 = L"Failed to initialize CVirtualAddressAllocator for GpuVaIoMmuGlobal, _pGpuVaIoMmuAllocator=0x%p";
        v61 = *((_QWORD *)this + 5134);
        goto LABEL_74;
      }
      v62 = *((_QWORD *)this + 3);
      v63 = *((_QWORD *)this + 5134);
      v79[1] = 0;
      v79[0] = v63;
      SysMmIterateHardwareReservedRanges(*(struct SYSMM_ADAPTER **)(v62 + 224), v57, v79);
      LODWORD(v36) = v79[1];
      if ( SLODWORD(v79[1]) < 0 )
      {
        WdLogSingleEntry1(1, *(_QWORD *)(*((_QWORD *)this + 3) + 224LL));
        WdLogGlobalForLineNumber = 2145;
        v60 = L"Failed to initialize hardware reserved ranges for GpuVaIoMmuGlobal. SysMmAdapter=0x%p";
        v61 = *(_QWORD *)(*((_QWORD *)this + 3) + 224LL);
        goto LABEL_74;
      }
    }
    KeInitializeTimer((PKTIMER)((char *)this + 41456));
    KeInitializeThreadedDpc((PRKDPC)((char *)this + 41528), VidMmDelayedEvictionDpc, this);
    LODWORD(v36) = VIDMM_GLOBAL::CreateWorkerThread(this);
    if ( (int)v36 >= 0 )
    {
      if ( g_Feature_ResourcePoolManagement )
      {
        v64 = VidMmOpenAdapterOnAllResourcePools(this);
        v36 = v64;
        if ( v64 >= 0 )
        {
LABEL_96:
          *((_BYTE *)this + 40857) = *(_QWORD *)(*((_QWORD *)this + 3) + 1768LL) != 0;
          *((_QWORD *)this + 503) = MEMORY[0xFFFFF78000000014];
          *((_QWORD *)this + 504) = MEMORY[0xFFFFF78000000014];
          VIDMM_LOCKED_PAGE_HISTORY::Init((VIDMM_GLOBAL *)((char *)this + 41408), dword_1400872F4);
          if ( KeQueryHighestNodeNumber() )
          {
            for ( i = 0; i < (unsigned __int16)v19; ++i )
            {
              LocalNumaNode = DpiGetLocalNumaNode(*(_QWORD *)(*((_QWORD *)this + 3) + 216LL), i);
              if ( i )
              {
                if ( LocalNumaNode != *((_DWORD *)this + 10362) )
                  goto LABEL_105;
              }
              else
              {
                *((_DWORD *)this + 10362) = LocalNumaNode;
              }
            }
          }
          else
          {
LABEL_105:
            *((_DWORD *)this + 10362) = 0;
          }
          VIDMM_GLOBAL::AddToAdapterList(this);
          return (unsigned int)v36;
        }
        WdLogSingleEntry2(1, this, v64);
        WdLogGlobalForLineNumber = 2180;
        DxgkLogInternalTriageEvent(
          v65,
          0x40000,
          v66,
          (unsigned int)L"Failed to initialize adapter info for partitions. VidMmGlobal=0x%p, Status=0x%.8x",
          (__int64)this,
          v36,
          0,
          0);
      }
      else
      {
        DXGAUTOEXPUSHLOCKSHARED::DXGAUTOEXPUSHLOCKSHARED(
          (DXGAUTOEXPUSHLOCKSHARED *)v79,
          (struct _EX_PUSH_LOCK *const)&VIDMM_PARTITION::_PartitionLock);
        v67 = VIDMM_PARTITION::_PartitionTree;
        v68 = 0;
        while ( v67 )
        {
          v68 = (VIDMM_PARTITION *)v67;
          v67 = v67->Children[0];
        }
        while ( 1 )
        {
          if ( !v68 )
          {
            DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v79);
            goto LABEL_96;
          }
          v69 = VIDMM_PARTITION::EnsureAdapter_Legacy(v68, (unsigned int **)this);
          v36 = v69;
          if ( v69 < 0 )
            break;
          v70 = (VIDMM_PARTITION **)*((_QWORD *)v68 + 1);
          if ( v70 )
          {
            v71 = *v70;
            if ( *v70 )
            {
              do
              {
                v68 = v71;
                v71 = *(VIDMM_PARTITION **)v71;
              }
              while ( v71 );
            }
            else
            {
              v68 = (VIDMM_PARTITION *)*((_QWORD *)v68 + 1);
            }
          }
          else
          {
            do
            {
              v72 = v68;
              v68 = (VIDMM_PARTITION *)(*((_QWORD *)v68 + 2) & 0xFFFFFFFFFFFFFFFCuLL);
            }
            while ( v68 && *(VIDMM_PARTITION **)v68 != v72 );
          }
        }
        WdLogSingleEntry3(1, this, v68, v69);
        WdLogGlobalForLineNumber = 2204;
        DxgkLogInternalTriageEvent(
          v75,
          0x40000,
          v76,
          (unsigned int)L"Failed to initialize adapter info for partition. VidMmGlobal=0x%p, VidMmPartition=0x%p, Status=0x%.8x",
          (__int64)this,
          (__int64)v68,
          v36,
          0);
        DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v79);
      }
LABEL_101:
      VIDMM_PAGING_PROCESS::DestroyPagingProcess((VIDMM_GLOBAL *)((char *)this + 36672));
      return (unsigned int)v36;
    }
    WdLogSingleEntry0(1);
    v61 = 2167;
    v60 = L"Failed to start the worker thread";
    WdLogGlobalForLineNumber = 2167;
LABEL_74:
    DxgkLogInternalTriageEvent(v58, 0x40000, v59, (_DWORD)v60, v61, 0, 0, 0);
    goto LABEL_101;
  }
  _InterlockedIncrement(&dword_140087844);
  WdLogSingleEntry0(6);
  v41 = 1945;
  v42 = L"Couldn't allocate VIDMM_PHYSICAL_ADAPTER array";
LABEL_40:
  WdLogGlobalForLineNumber = v41;
  DxgkLogInternalTriageEvent(v39, 262145, v40, (_DWORD)v42, v41, 0, 0, 0);
  return 3221225495LL;
}

```

## disassembly

```asm
0x1400b8b50  mov     [rsp-38h+arg_10], rbx
0x1400b8b55  push    rbp
0x1400b8b56  push    rsi
0x1400b8b57  push    rdi
0x1400b8b58  push    r12
0x1400b8b5a  push    r13
0x1400b8b5c  push    r14
0x1400b8b5e  push    r15
0x1400b8b60  mov     rbp, rsp
0x1400b8b63  sub     rsp, 80h
0x1400b8b6a  mov     rax, cs:__security_cookie
0x1400b8b71  xor     rax, rsp
0x1400b8b74  mov     [rbp+var_10], rax
0x1400b8b78  mov     [rcx+10h], rdx
0x1400b8b7c  mov     rdi, rcx
0x1400b8b7f  mov     rax, [rdx+10h]
0x1400b8b83  mov     r15d, r9d
0x1400b8b86  mov     [rcx+18h], rax
0x1400b8b8a  mov     r12d, r8d
0x1400b8b8d  mov     [rcx+28h], r8d
0x1400b8b91  mov     r14, rdx
0x1400b8b94  mov     [rbp+var_2C], r8d
0x1400b8b98  mov     ecx, [rax+1BCh]
0x1400b8b9e  shr     ecx, 9
0x1400b8ba1  and     cl, 1
0x1400b8ba4  or      cs:byte_1400875EC, cl
0x1400b8baa  mov     rbx, [rdi+18h]
0x1400b8bae  cmp     r8d, 6000h
0x1400b8bb5  jb      short loc_1400B8BBE
0x1400b8bb7  or      byte ptr [rdi+9169h], 2
0x1400b8bbe  call    DxgkpIsDrtEnabled
0x1400b8bc3  mov     cl, [rdi+9169h]
0x1400b8bc9  mov     r10d, 40h ; '@'
0x1400b8bcf  mov     r8, [rdi+18h]
0x1400b8bd3  mov     r11b, 20h ; ' '
0x1400b8bd6  shl     al, 6
0x1400b8bd9  xor     al, cl
0x1400b8bdb  and     al, r10b
0x1400b8bde  lea     r9d, [r10-3Fh]
0x1400b8be2  xor     al, cl
0x1400b8be4  mov     [rdi+9169h], al
0x1400b8bea  mov     cl, [r8+1430h]
0x1400b8bf1  shl     cl, 5
0x1400b8bf4  xor     cl, al
0x1400b8bf6  and     cl, r11b
0x1400b8bf9  xor     cl, al
0x1400b8bfb  mov     al, cl
0x1400b8bfd  shr     al, 1
0x1400b8bff  xor     al, cl
0x1400b8c01  and     al, 10h
0x1400b8c03  xor     al, cl
0x1400b8c05  mov     [rdi+9169h], al
0x1400b8c0b  mov     al, [rdi+916Ah]
0x1400b8c11  mov     cl, al
0x1400b8c13  xor     cl, [r8+144Ch]
0x1400b8c1a  and     cl, r9b
0x1400b8c1d  xor     cl, al
0x1400b8c1f  mov     [rdi+916Ah], cl
0x1400b8c25  mov     eax, [r8+128h]
0x1400b8c2c  mov     [rdi+0C28h], eax
0x1400b8c32  cmp     eax, r10d
0x1400b8c35  jbe     short loc_1400B8C88
0x1400b8c37  mov     edx, r10d
0x1400b8c3a  mov     ecx, r9d
0x1400b8c3d  call    cs:__imp_WdLogSingleEntry1
0x1400b8c44  nop     dword ptr [rax+rax+00h]
0x1400b8c49  xor     esi, esi
0x1400b8c4b  mov     cs:WdLogGlobalForLineNumber, 70Ah
0x1400b8c55  mov     [rsp+80h+var_48], rsi
0x1400b8c5a  lea     r9, aTotalNumberOfE; "Total number of engine on logical adapt"...
0x1400b8c61  mov     [rsp+80h+var_50], rsi
0x1400b8c66  mov     [rsp+80h+var_58], rsi
0x1400b8c6b  mov     [rsp+80h+var_60], 40h ; '@'
0x1400b8c74  mov     edx, 40000h
0x1400b8c79  call    DxgkLogInternalTriageEvent
0x1400b8c7e  mov     eax, 0C000000Dh
0x1400b8c83  jmp     loc_1400B95F7
0x1400b8c88  movzx   r13d, word ptr [rdi+0C28h]
0x1400b8c90  xor     esi, esi
0x1400b8c92  mov     ecx, [rbx+0A24h]
0x1400b8c98  mov     [rbp+var_30], r13w
0x1400b8c9d  test    r11b, cl
0x1400b8ca0  jz      loc_1400B8D99
0x1400b8ca6  mov     al, [rdi+9168h]
0x1400b8cac  lea     rdx, [rbp+var_28]; union SYSMM_IOMMU_STATE *
0x1400b8cb0  and     al, 0FDh
0x1400b8cb2  shr     ecx, 5
0x1400b8cb5  and     cl, 2
0x1400b8cb8  mov     dword ptr [rbp+var_28], esi
0x1400b8cbb  or      cl, al
0x1400b8cbd  mov     [rdi+9168h], cl
0x1400b8cc3  and     cl, 0DFh
0x1400b8cc6  mov     eax, [rbx+0A24h]
0x1400b8ccc  shr     eax, 2
0x1400b8ccf  and     al, r11b
0x1400b8cd2  or      al, cl
0x1400b8cd4  mov     [rdi+9168h], al
0x1400b8cda  mov     rcx, [r8+0E0h]; struct SYSMM_ADAPTER *
0x1400b8ce1  call    ?SysMmQueryIommuState@@YAXPEBUSYSMM_ADAPTER@@PEATSYSMM_IOMMU_STATE@@@Z; SysMmQueryIommuState(SYSMM_ADAPTER const *,SYSMM_IOMMU_STATE *)
0x1400b8ce6  mov     al, [rdi+9168h]
0x1400b8cec  mov     ecx, dword ptr [rbp+var_28]
0x1400b8cef  and     al, 0FBh
0x1400b8cf1  shr     ecx, 2
0x1400b8cf4  and     cl, 1
0x1400b8cf7  shl     cl, 2
0x1400b8cfa  or      cl, al
0x1400b8cfc  mov     [rdi+9168h], cl
0x1400b8d02  mov     rcx, [rdi+18h]; this
0x1400b8d06  call    ?IsGpuVaIoMmuGlobalSupported@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsGpuVaIoMmuGlobalSupported(void)
0x1400b8d0b  neg     al
0x1400b8d0d  mov     r11b, 20h ; ' '
0x1400b8d10  mov     al, [rdi+9168h]
0x1400b8d16  sbb     cl, cl
0x1400b8d18  and     al, 0F7h
0x1400b8d1a  and     cl, 8
0x1400b8d1d  or      cl, al
0x1400b8d1f  mov     al, cl
0x1400b8d21  and     al, 0Eh
0x1400b8d23  neg     al
0x1400b8d25  sbb     dl, dl
0x1400b8d27  and     cl, 0EFh
0x1400b8d2a  and     dl, 10h
0x1400b8d2d  or      dl, cl
0x1400b8d2f  mov     [rdi+9168h], dl
0x1400b8d35  test    r11b, dl
0x1400b8d38  jz      short loc_1400B8D69
0x1400b8d3a  mov     eax, cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x1400b8d40  test    r11b, al
0x1400b8d43  jnz     short loc_1400B8D5B
0x1400b8d45  mov     rax, [rdi+18h]
0x1400b8d49  mov     ecx, [rax+1BCh]
0x1400b8d4f  test    cl, 4
0x1400b8d52  jnz     short loc_1400B8D5B
0x1400b8d54  mov     al, 40h ; '@'
0x1400b8d56  test    cl, 8
0x1400b8d59  jz      short loc_1400B8D5E
0x1400b8d5b  mov     al, sil
0x1400b8d5e  and     dl, 0BFh
0x1400b8d61  or      dl, al
0x1400b8d63  mov     [rdi+9168h], dl
0x1400b8d69  cmp     r12d, 5017h
0x1400b8d70  jnb     short loc_1400B8D7E
0x1400b8d72  test    cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A, 100h; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x1400b8d7c  jz      short loc_1400B8D8D
0x1400b8d7e  mov     r9d, 1
0x1400b8d84  or      [rdi+9169h], r9b
0x1400b8d8b  jmp     short loc_1400B8D93
0x1400b8d8d  mov     r9d, 1
0x1400b8d93  mov     r10d, 40h ; '@'
0x1400b8d99  mov     dl, [rdi+9168h]
0x1400b8d9f  test    dl, 0Ch
0x1400b8da2  jnz     short loc_1400B8E11
0x1400b8da4  test    r9b, r15b
0x1400b8da7  jz      short loc_1400B8DBE
0x1400b8da9  mov     [rdi+8DA2h], r9b
0x1400b8db0  mov     [rdi+8DA4h], r9b
0x1400b8db7  mov     [rdi+8DD0h], r9b
0x1400b8dbe  test    r15b, 2
0x1400b8dc2  jz      short loc_1400B8E11
0x1400b8dc4  test    dword ptr [rbx+0A24h], 4000h
0x1400b8dce  jnz     short loc_1400B8E0A
0x1400b8dd0  mov     ecx, r9d
0x1400b8dd3  call    cs:__imp_WdLogSingleEntry0
0x1400b8dda  nop     dword ptr [rax+rax+00h]
0x1400b8ddf  mov     [rsp+80h+var_48], rsi
0x1400b8de4  lea     r9, aDmaRemappingRe; "DMA remapping requires the driver to su"...
0x1400b8deb  mov     eax, 745h
0x1400b8df0  mov     [rsp+80h+var_50], rsi
0x1400b8df5  mov     [rsp+80h+var_58], rsi
0x1400b8dfa  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b8e00  mov     [rsp+80h+var_60], rax
0x1400b8e05  jmp     loc_1400B8C74
0x1400b8e0a  mov     [rdi+8DA3h], r9b
0x1400b8e11  mov     eax, [rbx+0A20h]
0x1400b8e17  shr     eax, 5
0x1400b8e1a  not     al
0x1400b8e1c  and     al, r9b
0x1400b8e1f  mov     [rdi+2E0h], al
0x1400b8e25  mov     ecx, [rbx+0A24h]
0x1400b8e2b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400b8e2f  mov     al, [rdi+9169h]
0x1400b8e35  shr     ecx, 0Eh
0x1400b8e38  shl     cl, 3
0x1400b8e3b  xor     cl, al
0x1400b8e3d  and     cl, 8
0x1400b8e40  xor     cl, al
0x1400b8e42  mov     [rdi+9169h], cl
0x1400b8e48  test    dl, 10h
0x1400b8e4b  jz      loc_1400B8F0F
0x1400b8e51  mov     ecx, cs:dword_14008749C
0x1400b8e57  test    ecx, ecx
0x1400b8e59  jz      loc_1400B8F0F
0x1400b8e5f  mov     eax, cs:dword_1400874A0
0x1400b8e65  cmp     ecx, 10000h
0x1400b8e6b  mov     r9d, ecx
0x1400b8e6e  mov     [rsp+80h+var_60], rax
0x1400b8e73  mov     r15d, 100h
0x1400b8e79  lea     rcx, [rdi+91D0h]
0x1400b8e80  mov     r8d, r15d
0x1400b8e83  cmovbe  r8, r10
0x1400b8e87  call    ?Initialize@DXGK_LOG@@QEAAJIW4DXGK_POOL_FLAGS@@_K1@Z; DXGK_LOG::Initialize(uint,DXGK_POOL_FLAGS,unsigned __int64,unsigned __int64)
0x1400b8e8c  mov     ecx, cs:dword_1400874A4
0x1400b8e92  lea     eax, [rbx+31h]
0x1400b8e95  mul     rcx
0x1400b8e98  mov     r8d, r15d
0x1400b8e9b  mov     edx, 32356956h
0x1400b8ea0  cmovb   rax, rbx
0x1400b8ea4  mov     rcx, rax
0x1400b8ea7  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400b8eac  mov     [rdi+91F0h], rax
0x1400b8eb3  test    rax, rax
0x1400b8eb6  jnz     short loc_1400B8F09
0x1400b8eb8  lock inc cs:dword_140087860
0x1400b8ebf  lea     ecx, [rbx+7]
0x1400b8ec2  call    cs:__imp_WdLogSingleEntry0
0x1400b8ec9  nop     dword ptr [rax+rax+00h]
0x1400b8ece  mov     eax, 770h
0x1400b8ed3  lea     r9, aFailedToAlloca; "Failed to allocate _PageMappingHistoryE"...
0x1400b8eda  mov     [rsp+80h+var_48], rsi
0x1400b8edf  mov     edx, 40001h
0x1400b8ee4  mov     [rsp+80h+var_50], rsi
0x1400b8ee9  mov     [rsp+80h+var_58], rsi
0x1400b8eee  mov     [rsp+80h+var_60], rax
0x1400b8ef3  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b8ef9  call    DxgkLogInternalTriageEvent
0x1400b8efe  mov     r14d, 0C0000017h
0x1400b8f04  jmp     loc_1400B95C1
0x1400b8f09  mov     r9d, 1
0x1400b8f0f  test    [rdi+916Ah], r9b
0x1400b8f16  jz      short loc_1400B8F4C
0x1400b8f18  xorps   xmm0, xmm0
0x1400b8f1b  lea     rdx, [rbp+var_28]; struct _DXGKARG_FEATURE_INTELLIGENT_CARVEOUT_QUERY_PREFERENCES *
0x1400b8f1f  mov     rcx, r14; this
0x1400b8f22  movups  xmmword ptr [rbp+var_28], xmm0
0x1400b8f26  call    ?DdiIntelligentCarveoutQueryPreferences@ADAPTER_RENDER@@QEAAXPEAU_DXGKARG_FEATURE_INTELLIGENT_CARVEOUT_QUERY_PREFERENCES@@@Z; ADAPTER_RENDER::DdiIntelligentCarveoutQueryPreferences(_DXGKARG_FEATURE_INTELLIGENT_CARVEOUT_QUERY_PREFERENCES *)
0x1400b8f2b  lea     rcx, [rbp+var_28]
0x1400b8f2f  call    ValidateIntelligentCarveoutPreferences
0x1400b8f34  test    al, al
0x1400b8f36  jnz     short loc_1400B8F43
0x1400b8f38  mov     r14d, 0C000000Dh
0x1400b8f3e  jmp     loc_1400B95C1
0x1400b8f43  mov     rcx, [rbp+var_28]; unsigned __int64
0x1400b8f47  call    ?VidMmAdjustIntelligentCarveoutSize@@YAJ_K@Z; VidMmAdjustIntelligentCarveoutSize(unsigned __int64)
0x1400b8f4c  mov     eax, 8
0x1400b8f51  mul     r13
0x1400b8f54  mov     edx, 30356956h
0x1400b8f59  cmovb   rax, rbx
0x1400b8f5d  mov     ebx, 40h ; '@'
0x1400b8f62  mov     r8d, ebx
0x1400b8f65  mov     rcx, rax
0x1400b8f68  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400b8f6d  mov     [rdi+8E80h], rax
0x1400b8f74  test    rax, rax
0x1400b8f77  jnz     short loc_1400B8FC9
0x1400b8f79  lock inc cs:dword_140087844
0x1400b8f80  lea     ecx, [rbx-3Ah]
0x1400b8f83  call    cs:__imp_WdLogSingleEntry0
0x1400b8f8a  nop     dword ptr [rax+rax+00h]
0x1400b8f8f  mov     eax, 799h
0x1400b8f94  lea     r9, aCouldnTAllocat_49; "Couldn't allocate VIDMM_PHYSICAL_ADAPTE"...
0x1400b8f9b  mov     [rsp+80h+var_48], rsi
0x1400b8fa0  mov     edx, 40001h
0x1400b8fa5  mov     [rsp+80h+var_50], rsi
0x1400b8faa  mov     [rsp+80h+var_58], rsi
0x1400b8faf  mov     [rsp+80h+var_60], rax
0x1400b8fb4  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b8fba  call    DxgkLogInternalTriageEvent
0x1400b8fbf  mov     eax, 0C0000017h
0x1400b8fc4  jmp     loc_1400B95F7
0x1400b8fc9  movzx   r15d, si
0x1400b8fcd  cmp     si, r13w
0x1400b8fd1  jb      short loc_1400B9013
0x1400b8fd3  mov     ebx, 1
0x1400b8fd8  mov     rcx, rdi; this
0x1400b8fdb  call    ?InitializeForwardProgressMdl@VIDMM_GLOBAL@@QEAAJXZ; VIDMM_GLOBAL::InitializeForwardProgressMdl(void)
0x1400b8fe0  movsxd  r14, eax
0x1400b8fe3  test    eax, eax
0x1400b8fe5  jns     loc_1400B91C2
0x1400b8feb  mov     rdx, r14
0x1400b8fee  mov     ecx, 3
0x1400b8ff3  call    cs:__imp_WdLogSingleEntry1
0x1400b8ffa  nop     dword ptr [rax+rax+00h]
0x1400b8fff  mov     cs:WdLogGlobalForLineNumber, 7E4h
0x1400b9009  jmp     loc_1400B95C1
0x1400b900e  mov     ebx, 40h ; '@'
0x1400b9013  mov     rax, [rdi+18h]
0x1400b9017  mov     rcx, [rdi+10h]; this
0x1400b901b  movzx   r12d, r15w
0x1400b901f  imul    r14, r12, 160h
0x1400b9026  movzx   edx, r15w; unsigned int
0x1400b902a  add     r14, [rax+0C30h]
0x1400b9031  mov     [rbp+var_28], r14
0x1400b9035  call    ?GetGpuMmuCaps@ADAPTER_RENDER@@QEBAPEBUDXGADAPTER_GPUMMUCAPS@@I@Z; ADAPTER_RENDER::GetGpuMmuCaps(uint)
0x1400b903a  test    byte ptr [rdi+9169h], 20h
0x1400b9041  mov     r13, rax
0x1400b9044  mov     r8, rbx
0x1400b9047  mov     edx, 30356956h
0x1400b904c  jz      short loc_1400B90BB
0x1400b904e  mov     ecx, 0AC8h
0x1400b9053  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
  ... truncated ...
```
