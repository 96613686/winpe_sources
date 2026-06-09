# VIDMM_GLOBAL::Init(ADAPTER_RENDER *,ulong,uint)

- ea: `0x1400b514c`
- end: `0x1400b5c48`
- name: `?Init@VIDMM_GLOBAL@@QEAAJPEAVADAPTER_RENDER@@KI@Z`
- size: `2812`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this, struct ADAPTER_RENDER *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400be918`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14002ee90`
- `0x14002f5c0`
- `0x140030b80`
- `0x140031178`
- `0x1400316ac`
- `0x140031d4c`
- `0x140032898`
- `0x140046768`
- `0x140046840`
- `0x140046914`
- `0x140047768`
- `0x1400583f8`
- `0x140058680`
- `0x1400b514c`
- `0x1400b5c50`
- `0x1400b5d68`
- `0x1400ba754`
- `0x1400bf974`
- `0x1400c1d08`
- `0x1400c1e98`
- `0x1400c4a70`
- `0x1400c4f1c`
- `0x1400cba18`
- `0x1400cc9ac`
- `0x1400ed184`
- `0x1400ed504`

## import_xrefs

- `ntoskrnl!KeInitializeTimer` at `0x1400b59df`
- `ntoskrnl!KeInitializeTimer` at `0x1400b59df`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1400b59fc`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1400b59fc`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400b5b09`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400b5b09`
- `watchdog!WdLogSingleEntry3` at `0x1400b5b63`
- `watchdog!WdLogSingleEntry3` at `0x1400b5b63`
- `watchdog!WdLogSingleEntry2` at `0x1400b57ea`
- `watchdog!WdLogSingleEntry2` at `0x1400b57ea`
- `watchdog!WdLogSingleEntry0` at `0x1400b53c4`
- `watchdog!WdLogSingleEntry0` at `0x1400b54b2`
- `watchdog!WdLogSingleEntry0` at `0x1400b55ce`
- `watchdog!WdLogSingleEntry0` at `0x1400b56b0`
- `watchdog!WdLogSingleEntry0` at `0x1400b58db`
- `watchdog!WdLogSingleEntry0` at `0x1400b5a19`
- `watchdog!WdLogSingleEntry0` at `0x1400b53c4`
- `watchdog!WdLogSingleEntry0` at `0x1400b54b2`
- `watchdog!WdLogSingleEntry0` at `0x1400b55ce`
- `watchdog!WdLogSingleEntry0` at `0x1400b56b0`
- `watchdog!WdLogSingleEntry0` at `0x1400b58db`
- `watchdog!WdLogSingleEntry0` at `0x1400b5a19`
- `watchdog!WdLogSingleEntry1` at `0x1400b5237`
- `watchdog!WdLogSingleEntry1` at `0x1400b5575`
- `watchdog!WdLogSingleEntry1` at `0x1400b57c4`
- `watchdog!WdLogSingleEntry1` at `0x1400b592b`
- `watchdog!WdLogSingleEntry1` at `0x1400b59ab`
- `watchdog!WdLogSingleEntry1` at `0x1400b5237`
- `watchdog!WdLogSingleEntry1` at `0x1400b5575`
- `watchdog!WdLogSingleEntry1` at `0x1400b57c4`
- `watchdog!WdLogSingleEntry1` at `0x1400b592b`
- `watchdog!WdLogSingleEntry1` at `0x1400b59ab`
- `dxgkrnl!DpiGetLocalNumaNode` at `0x1400b5b39`
- `dxgkrnl!DpiGetLocalNumaNode` at `0x1400b5b39`

## string_xrefs

- `0x1400b53d5`: `DMA remapping requires the driver to support the MapAperture2 paging buffer command`
- `0x1400b5a2a`: `Failed to start the worker thread`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::Init(VIDMM_GLOBAL *this, struct ADAPTER_RENDER *a2, unsigned int a3, char a4)
{
  __int64 v5; // rax
  unsigned int v7; // r12d
  __int64 v9; // rbx
  char IsDrtEnabled; // al
  __int64 v11; // r8
  char v12; // al
  unsigned __int8 v13; // cl
  unsigned int v14; // eax
  int v15; // ecx
  int v16; // r8d
  unsigned __int64 v18; // r13
  __int64 v19; // rdx
  char v20; // al
  char v21; // dl
  unsigned __int8 IsGpuVaIoMmuGlobalSupported; // al
  char v23; // cl
  int v24; // ecx
  char v25; // al
  int v26; // ecx
  int v27; // r8d
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // ecx
  int v32; // r8d
  __int64 v33; // rax
  const wchar_t *v34; // r9
  __int64 v35; // r14
  VIDMM_GLOBAL *v36; // rcx
  __int64 v37; // rbx
  int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rax
  int v41; // ecx
  int v42; // r8d
  __int64 v43; // rax
  const wchar_t *v44; // r9
  unsigned __int16 v45; // r15
  ADAPTER_RENDER *v46; // rcx
  const struct DXGK_PHYSICALADAPTERINFO *v47; // r14
  const struct DXGADAPTER_GPUMMUCAPS *GpuMmuCaps; // r13
  VIDMM_PHYSICAL_ADAPTER *v49; // rax
  VIDMM_PHYSICAL_ADAPTER *v50; // rbx
  VIDMM_PHYSICAL_ADAPTER *v51; // rax
  int v52; // eax
  __int64 v53; // rdx
  int v54; // eax
  bool v55; // al
  int v56; // eax
  CVirtualAddressAllocator *v57; // rax
  CVirtualAddressAllocator *v58; // rax
  int (*v59)(unsigned __int64, unsigned __int64, void *); // rdx
  int v60; // ecx
  int v61; // r8d
  const wchar_t *v62; // r9
  __int64 v63; // rax
  __int64 v64; // rcx
  struct _RTL_BALANCED_NODE *v65; // rax
  VIDMM_PARTITION *v66; // r15
  int v67; // eax
  VIDMM_PARTITION **v68; // rax
  VIDMM_PARTITION *v69; // rcx
  VIDMM_PARTITION *v70; // rax
  unsigned __int16 i; // bx
  unsigned __int16 LocalNumaNode; // ax
  int v73; // ecx
  int v74; // r8d
  _QWORD *v75; // rcx
  unsigned __int16 v76; // [rsp+50h] [rbp-19h]
  _BYTE v78[24]; // [rsp+58h] [rbp-11h] BYREF
  __int128 v79; // [rsp+70h] [rbp+7h] BYREF

  *((_QWORD *)this + 2) = a2;
  v5 = *((_QWORD *)a2 + 2);
  *((_QWORD *)this + 3) = v5;
  v7 = a3;
  *((_DWORD *)this + 10) = a3;
  byte_14008661C |= (*(_DWORD *)(v5 + 444) & 0x200) != 0;
  v9 = *((_QWORD *)this + 3);
  if ( a3 >= 0x6000 )
    *((_BYTE *)this + 37225) |= 2u;
  IsDrtEnabled = DxgkpIsDrtEnabled();
  v11 = *((_QWORD *)this + 3);
  v12 = *((_BYTE *)this + 37225) ^ (*((_BYTE *)this + 37225) ^ (IsDrtEnabled << 6)) & 0x40;
  *((_BYTE *)this + 37225) = v12;
  v13 = v12 ^ (v12 ^ (32 * *(_BYTE *)(v11 + 5152))) & 0x20;
  *((_BYTE *)this + 37225) = v13 ^ (v13 ^ (v13 >> 1)) & 0x10;
  *((_BYTE *)this + 37226) ^= (*(_BYTE *)(v11 + 5180) ^ *((_BYTE *)this + 37226)) & 1;
  v14 = *(_DWORD *)(v11 + 296);
  *((_DWORD *)this + 778) = v14;
  if ( v14 > 0x40 )
  {
    WdLogSingleEntry1(1, 64);
    WdLogGlobalForLineNumber = 1745;
    DxgkLogInternalTriageEvent(
      v15,
      0x40000,
      v16,
      (unsigned int)L"Total number of engine on logical adapter can't exceed %I64d",
      64,
      0,
      0,
      0);
    return 3221225485LL;
  }
  v18 = *((unsigned __int16 *)this + 1556);
  v19 = *(unsigned int *)(v9 + 2580);
  v76 = *((_WORD *)this + 1556);
  if ( (v19 & 0x20) != 0 )
  {
    v20 = *((_BYTE *)this + 37224) & 0xFD;
    LODWORD(v79) = 0;
    v21 = v20 | ((unsigned int)v19 >> 5) & 2;
    *((_BYTE *)this + 37224) = v21;
    *((_BYTE *)this + 37224) = v21 & 0xDF | (*(_DWORD *)(v9 + 2580) >> 2) & 0x20;
    SysMmQueryIommuState(*(const struct SYSMM_ADAPTER **)(v11 + 224), (union SYSMM_IOMMU_STATE *)&v79);
    *((_BYTE *)this + 37224) = *((_BYTE *)this + 37224) & 0xFB | (4 * ((v79 & 4) != 0));
    IsGpuVaIoMmuGlobalSupported = DXGADAPTER::IsGpuVaIoMmuGlobalSupported(*((DXGADAPTER **)this + 3));
    v23 = *((_BYTE *)this + 37224) & 0xE7 | (IsGpuVaIoMmuGlobalSupported != 0 ? 8 : 0);
    LOBYTE(v19) = v23 | ((*((_BYTE *)this + 37224) & 6 | (IsGpuVaIoMmuGlobalSupported != 0 ? 8 : 0)) != 0 ? 0x10 : 0);
    *((_BYTE *)this + 37224) = v19;
    if ( (v23 & 0x20) != 0 )
    {
      if ( (VIDMM_GLOBAL::_Config & 0x20) != 0
        || (v24 = *(_DWORD *)(*((_QWORD *)this + 3) + 444LL), (v24 & 4) != 0)
        || (v25 = 64, (v24 & 8) != 0) )
      {
        v25 = 0;
      }
      *((_BYTE *)this + 37224) = v25 | v19 & 0xBF;
    }
    if ( v7 >= 0x5017 || (VIDMM_GLOBAL::_Config & 0x100) != 0 )
      *((_BYTE *)this + 37225) |= 1u;
  }
  LOBYTE(v19) = *((_BYTE *)this + 37224);
  if ( (v19 & 0xC) == 0 )
  {
    if ( (a4 & 1) != 0 )
    {
      *((_BYTE *)this + 36258) = 1;
      *((_BYTE *)this + 36260) = 1;
      *((_BYTE *)this + 36304) = 1;
    }
    if ( (a4 & 2) != 0 )
    {
      if ( (*(_DWORD *)(v9 + 2580) & 0x4000) == 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1804;
        DxgkLogInternalTriageEvent(
          v26,
          0x40000,
          v27,
          (unsigned int)L"DMA remapping requires the driver to support the MapAperture2 paging buffer command",
          1804,
          0,
          0,
          0);
        return 3221225485LL;
      }
      *((_BYTE *)this + 36259) = 1;
    }
  }
  *((_BYTE *)this + 736) = (*(_DWORD *)(v9 + 2576) & 0x20) == 0;
  *((_BYTE *)this + 37225) ^= (*((_BYTE *)this + 37225) ^ (8 * (*(_DWORD *)(v9 + 2580) >> 14))) & 8;
  if ( (v19 & 0x10) != 0 && dword_1400864CC )
  {
    v28 = 256;
    if ( (unsigned int)dword_1400864CC <= 0x10000 )
      v28 = 64;
    DXGK_LOG::Initialize((char *)this + 37328, v19, v28, (unsigned int)dword_1400864CC, (unsigned int)dword_1400864D0);
    v29 = 48LL * (unsigned int)dword_1400864D4;
    if ( !is_mul_ok((unsigned int)dword_1400864D4, 0x30u) )
      v29 = -1;
    v30 = operator new[](v29, 842361174, 256);
    *((_QWORD *)this + 4670) = v30;
    if ( !v30 )
    {
      _InterlockedIncrement(&dword_140086880);
      WdLogSingleEntry0(6);
      v33 = 1847;
      v34 = L"Failed to allocate _PageMappingHistoryEntry";
LABEL_31:
      WdLogGlobalForLineNumber = v33;
      DxgkLogInternalTriageEvent(v31, 262145, v32, (_DWORD)v34, v33, 0, 0, 0);
      LODWORD(v35) = -1073741801;
LABEL_101:
      VIDMM_PAGING_PROCESS::DestroyPagingProcess((VIDMM_GLOBAL *)((char *)this + 36672));
      return (unsigned int)v35;
    }
  }
  if ( (*((_BYTE *)this + 37226) & 1) != 0 )
  {
    v79 = 0;
    ADAPTER_RENDER::DdiIntelligentCarveoutQueryPreferences(
      a2,
      (struct _DXGKARG_FEATURE_INTELLIGENT_CARVEOUT_QUERY_PREFERENCES *)&v79);
    if ( !(unsigned __int8)ValidateIntelligentCarveoutPreferences(&v79) )
    {
      LODWORD(v35) = -1073741811;
      goto LABEL_101;
    }
    DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(
      (DXGAUTOEXPUSHLOCKEXCLUSIVE *)v78,
      (struct _EX_PUSH_LOCK *const)&VIDMM_GLOBAL::_DedicatedPartitionLock);
    if ( (unsigned __int64)v79 > VIDMM_GLOBAL::_DedicatedPartitionCurrentSize )
    {
      v37 = v79 - VIDMM_GLOBAL::_DedicatedPartitionCurrentSize;
      v38 = VIDMM_GLOBAL::TransferPagesToDedicatedPartition(v36, v79 - VIDMM_GLOBAL::_DedicatedPartitionCurrentSize);
      if ( v38 < 0 )
      {
        WdLogSingleEntry1(3, v38);
        WdLogGlobalForLineNumber = 1898;
      }
      else
      {
        VIDMM_GLOBAL::_DedicatedPartitionCurrentSize += v37;
      }
    }
    DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v78);
  }
  v39 = 8 * v18;
  if ( !is_mul_ok(v18, 8u) )
    v39 = -1;
  v40 = operator new[](v39, 808806742, 64);
  *((_QWORD *)this + 4560) = v40;
  if ( v40 )
  {
    v45 = 0;
    if ( (_WORD)v18 )
    {
      while ( 1 )
      {
        v46 = (ADAPTER_RENDER *)*((_QWORD *)this + 2);
        v47 = (const struct DXGK_PHYSICALADAPTERINFO *)(*(_QWORD *)(*((_QWORD *)this + 3) + 3104LL) + 352LL * v45);
        *(_QWORD *)&v79 = v47;
        GpuMmuCaps = ADAPTER_RENDER::GetGpuMmuCaps(v46, v45);
        if ( (*((_BYTE *)this + 37225) & 0x20) != 0 )
        {
          v49 = (VIDMM_PHYSICAL_ADAPTER *)operator new(2496, 808806742, 64);
          v50 = v49;
          if ( v49 )
          {
            VIDMM_PHYSICAL_ADAPTER::VIDMM_PHYSICAL_ADAPTER(v49, this, v45, v47, GpuMmuCaps);
            *((_BYTE *)v50 + 1084) &= ~1u;
            *(_QWORD *)v50 = &VIDMM_PHYSICAL_ADAPTER_PBMM::`vftable';
          }
          else
          {
            v50 = 0;
          }
          if ( !v50 )
          {
LABEL_51:
            _InterlockedIncrement(&dword_140086868);
            WdLogSingleEntry0(6);
            v43 = 1948;
            v44 = L"Couldn't allocate VIDMM_PHYSICAL_ADAPTER";
            goto LABEL_44;
          }
        }
        else
        {
          v51 = (VIDMM_PHYSICAL_ADAPTER *)operator new(2416, 808806742, 64);
          v50 = v51;
          if ( !v51 )
            goto LABEL_51;
          VIDMM_PHYSICAL_ADAPTER::VIDMM_PHYSICAL_ADAPTER(v51, this, v45, v47, GpuMmuCaps);
          *((_BYTE *)v50 + 1084) |= 1u;
          *(_QWORD *)v50 = &VIDMM_PHYSICAL_ADAPTER_LEGACY::`vftable';
          *((_QWORD *)v50 + 301) = (char *)v50 + 2400;
          *((_QWORD *)v50 + 300) = (char *)v50 + 2400;
        }
        *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * v45) = v50;
        v52 = VidMmInitializePhysicalAdapter(v50);
        LODWORD(v35) = v52;
        if ( v52 < 0 )
          break;
        *((_DWORD *)this + 161) += *((_DWORD *)v50 + 166);
        if ( GpuMmuCaps )
          *((_BYTE *)this + 36256) &= (*((_BYTE *)GpuMmuCaps + 20) & 1) == 0;
        v53 = v79;
        LOWORD(v18) = v76;
        *((_BYTE *)this + 37225) = *((_BYTE *)this + 37225)
                                 & 0xFB
                                 ^ (*((_BYTE *)this + 37225) | (4 * (*(_DWORD *)(v79 + 16) >> 5)))
                                 & 4;
        *((_BYTE *)v50 + 1086) = *((_BYTE *)v50 + 1086) & 0xEF | (*(_BYTE *)(v53 + 50) != 0 ? 0x10 : 0);
        if ( ++v45 >= v76 )
        {
          v7 = a3;
          goto LABEL_59;
        }
      }
      WdLogSingleEntry2(3, v45, v52);
      WdLogGlobalForLineNumber = 1961;
      goto LABEL_101;
    }
LABEL_59:
    v54 = VIDMM_GLOBAL::InitializeForwardProgressMdl(this);
    LODWORD(v35) = v54;
    if ( v54 < 0 )
    {
      WdLogSingleEntry1(3, v54);
      WdLogGlobalForLineNumber = 1986;
      goto LABEL_101;
    }
    if ( dword_140086480 == 2 )
      v55 = (*(_DWORD *)(*((_QWORD *)this + 3) + 2564LL) & 4) != 0;
    else
      v55 = dword_140086480 == 1;
    *((_BYTE *)this + 3264) = v55;
    *((_QWORD *)this + 5161) = qword_140086590;
    VIDMM_GLOBAL::InitializePagingHistory(this, dword_14008643C);
    if ( (*((_BYTE *)this + 37224) & 0x10) != 0 )
    {
      v56 = v7 >= 0x5023 ? dword_1400864D8 : 4096 << *((_DWORD *)this + 9305);
      *((_DWORD *)this + 9325) = v56;
      LODWORD(v35) = VIDMM_PAGING_PROCESS::CreateVaAllocator((VIDMM_GLOBAL *)((char *)this + 36672), this);
      if ( (int)v35 < 0 )
        goto LABEL_101;
    }
    if ( DXGADAPTER::IsGpuVaIoMmuGlobalSupported(*((DXGADAPTER **)this + 3)) )
    {
      v57 = (CVirtualAddressAllocator *)operator new(160, 1265072196, 256);
      if ( v57 )
        v58 = CVirtualAddressAllocator::CVirtualAddressAllocator(v57);
      else
        v58 = 0;
      *((_QWORD *)this + 5134) = v58;
      if ( !v58 )
      {
        _InterlockedAdd(&dword_140086878, 1u);
        WdLogSingleEntry0(6);
        v33 = 2073;
        v34 = L"Failed to allocate CVirtualAddressAllocator";
        goto LABEL_31;
      }
      LODWORD(v35) = CVirtualAddressAllocator::InitializeVaAllocator(
                       v58,
                       1LL << *((_DWORD *)this + 9304),
                       *((unsigned int *)this + 9325),
                       this,
                       0);
      if ( (int)v35 < 0 )
      {
        WdLogSingleEntry1(1, *((_QWORD *)this + 5134));
        WdLogGlobalForLineNumber = 2088;
        v62 = L"Failed to initialize CVirtualAddressAllocator for GpuVaIoMmuGlobal, _pGpuVaIoMmuAllocator=0x%p";
        v63 = *((_QWORD *)this + 5134);
LABEL_78:
        DxgkLogInternalTriageEvent(v60, 0x40000, v61, (_DWORD)v62, v63, 0, 0, 0);
        goto LABEL_101;
      }
      v64 = *((_QWORD *)this + 3);
      v79 = *((unsigned __int64 *)this + 5134);
      SysMmIterateHardwareReservedRanges(*(struct SYSMM_ADAPTER **)(v64 + 224), v59, &v79);
      LODWORD(v35) = DWORD2(v79);
      if ( SDWORD2(v79) < 0 )
      {
        WdLogSingleEntry1(1, *(_QWORD *)(*((_QWORD *)this + 3) + 224LL));
        WdLogGlobalForLineNumber = 2111;
        v62 = L"Failed to initialize hardware reserved ranges for GpuVaIoMmuGlobal. SysMmAdapter=0x%p";
        v63 = *(_QWORD *)(*((_QWORD *)this + 3) + 224LL);
        goto LABEL_78;
      }
    }
    KeInitializeTimer((PKTIMER)((char *)this + 41456));
    KeInitializeThreadedDpc((PRKDPC)((char *)this + 41528), VidMmDelayedEvictionDpc, this);
    LODWORD(v35) = VIDMM_GLOBAL::CreateWorkerThread(this);
    if ( (int)v35 >= 0 )
    {
      DXGAUTOEXPUSHLOCKSHARED::DXGAUTOEXPUSHLOCKSHARED(
        (DXGAUTOEXPUSHLOCKSHARED *)&v79,
        (struct _EX_PUSH_LOCK *const)&VIDMM_PARTITION::_PartitionLock);
      v65 = VIDMM_PARTITION::_PartitionTree;
      v66 = 0;
      while ( v65 )
      {
        v66 = (VIDMM_PARTITION *)v65;
        v65 = v65->Children[0];
      }
      while ( v66 )
      {
        v67 = VIDMM_PARTITION::EnsureAdapter(v66, (unsigned int **)this);
        v35 = v67;
        if ( v67 < 0 )
        {
          WdLogSingleEntry3(1, this, v66, v67);
          WdLogGlobalForLineNumber = 2154;
          DxgkLogInternalTriageEvent(
            v73,
            0x40000,
            v74,
            (unsigned int)L"Failed to initialize adapter info for partition. VidMmGlobal=0x%p, VidMmPartition=0x%p, Status=0x%.8x",
            (__int64)this,
            (__int64)v66,
            v35,
            0);
          DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)&v79);
          goto LABEL_101;
        }
        v68 = (VIDMM_PARTITION **)*((_QWORD *)v66 + 1);
        if ( v68 )
        {
          v69 = *v68;
          if ( *v68 )
          {
            do
            {
              v66 = v69;
              v69 = *(VIDMM_PARTITION **)v69;
            }
            while ( v69 );
          }
          else
          {
            v66 = (VIDMM_PARTITION *)*((_QWORD *)v66 + 1);
          }
        }
        else
        {
          do
          {
            v70 = v66;
            v66 = (VIDMM_PARTITION *)(*((_QWORD *)v66 + 2) & 0xFFFFFFFFFFFFFFFCuLL);
          }
          while ( v66 && *(VIDMM_PARTITION **)v66 != v70 );
        }
      }
      DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)&v79);
      *((_BYTE *)this + 40857) = *(_QWORD *)(*((_QWORD *)this + 3) + 1768LL) != 0;
      *((_QWORD *)this + 503) = MEMORY[0xFFFFF78000000014];
      *((_QWORD *)this + 504) = MEMORY[0xFFFFF78000000014];
      VIDMM_LOCKED_PAGE_HISTORY::Init((VIDMM_GLOBAL *)((char *)this + 41408), dword_140086324);
      if ( KeQueryHighestNodeNumber() )
      {
        for ( i = 0; i < (unsigned __int16)v18; ++i )
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
      DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(
        (DXGAUTOEXPUSHLOCKEXCLUSIVE *)v78,
        (struct _EX_PUSH_LOCK *const)&VIDMM_GLOBAL::_AdapterListLock);
      v75 = (_QWORD *)qword_1400862B8;
      if ( *(PVOID **)qword_1400862B8 != &VIDMM_GLOBAL::_AdapterListHead )
        __fastfail(3u);
      *((_QWORD *)this + 5175) = qword_1400862B8;
      *((_QWORD *)this + 5174) = &VIDMM_GLOBAL::_AdapterListHead;
      *v75 = (char *)this + 41392;
      qword_1400862B8 = (__int64)this + 41392;
      DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v78);
      return (unsigned int)v35;
    }
    WdLogSingleEntry0(1);
    v63 = 2133;
    v62 = L"Failed to start the worker thread";
    WdLogGlobalForLineNumber = 2133;
    goto LABEL_78;
  }
  _InterlockedAdd(&dword_140086864, 1u);
  WdLogSingleEntry0(6);
  v43 = 1911;
  v44 = L"Couldn't allocate VIDMM_PHYSICAL_ADAPTER array";
LABEL_44:
  WdLogGlobalForLineNumber = v43;
  DxgkLogInternalTriageEvent(v41, 262145, v42, (_DWORD)v44, v43, 0, 0, 0);
  return 3221225495LL;
}

```

## disassembly

```asm
0x1400b514c  mov     [rsp-8+arg_10], rbx
0x1400b5151  push    rbp
0x1400b5152  push    rsi
0x1400b5153  push    rdi
0x1400b5154  push    r12
0x1400b5156  push    r13
0x1400b5158  push    r14
0x1400b515a  push    r15
0x1400b515c  lea     rbp, [rsp-27h]
0x1400b5161  sub     rsp, 90h
0x1400b5168  mov     rax, cs:__security_cookie
0x1400b516f  xor     rax, rsp
0x1400b5172  mov     [rbp+57h+var_38], rax
0x1400b5176  mov     [rcx+10h], rdx
0x1400b517a  mov     r14, rdx
0x1400b517d  mov     rax, [rdx+10h]
0x1400b5181  mov     r15d, r9d
0x1400b5184  mov     [rcx+18h], rax
0x1400b5188  mov     r12d, r8d
0x1400b518b  mov     [rcx+28h], r8d
0x1400b518f  mov     rdi, rcx
0x1400b5192  mov     [rbp+57h+var_6C], r8d
0x1400b5196  mov     edx, [rax+1BCh]
0x1400b519c  shr     edx, 9
0x1400b519f  and     dl, 1
0x1400b51a2  or      cs:byte_14008661C, dl
0x1400b51a8  mov     rbx, [rcx+18h]
0x1400b51ac  cmp     r8d, 6000h
0x1400b51b3  jb      short loc_1400B51BC
0x1400b51b5  or      byte ptr [rcx+9169h], 2
0x1400b51bc  call    DxgkpIsDrtEnabled
0x1400b51c1  mov     cl, [rdi+9169h]
0x1400b51c7  mov     r9d, 40h ; '@'
0x1400b51cd  mov     r8, [rdi+18h]
0x1400b51d1  mov     r10b, 20h ; ' '
0x1400b51d4  shl     al, 6
0x1400b51d7  xor     al, cl
0x1400b51d9  and     al, r9b
0x1400b51dc  xor     al, cl
0x1400b51de  mov     [rdi+9169h], al
0x1400b51e4  mov     cl, [r8+1420h]
0x1400b51eb  shl     cl, 5
0x1400b51ee  xor     cl, al
0x1400b51f0  and     cl, r10b
0x1400b51f3  xor     cl, al
0x1400b51f5  mov     al, cl
0x1400b51f7  shr     al, 1
0x1400b51f9  xor     al, cl
0x1400b51fb  and     al, 10h
0x1400b51fd  xor     al, cl
0x1400b51ff  lea     ecx, [r9-3Fh]
0x1400b5203  mov     [rdi+9169h], al
0x1400b5209  mov     al, [rdi+916Ah]
0x1400b520f  mov     dl, al
0x1400b5211  xor     dl, [r8+143Ch]
0x1400b5218  and     dl, cl
0x1400b521a  xor     dl, al
0x1400b521c  mov     [rdi+916Ah], dl
0x1400b5222  mov     eax, [r8+128h]
0x1400b5229  mov     [rdi+0C28h], eax
0x1400b522f  cmp     eax, r9d
0x1400b5232  jbe     short loc_1400B5282
0x1400b5234  mov     edx, r9d
0x1400b5237  call    cs:__imp_WdLogSingleEntry1
0x1400b523e  nop     dword ptr [rax+rax+00h]
0x1400b5243  xor     esi, esi
0x1400b5245  mov     cs:WdLogGlobalForLineNumber, 6D1h
0x1400b524f  mov     [rsp+0C0h+var_88], rsi
0x1400b5254  lea     r9, aTotalNumberOfE; "Total number of engine on logical adapt"...
0x1400b525b  mov     [rsp+0C0h+var_90], rsi
0x1400b5260  mov     [rsp+0C0h+var_98], rsi
0x1400b5265  mov     [rsp+0C0h+var_A0], 40h ; '@'
0x1400b526e  mov     edx, 40000h
0x1400b5273  call    DxgkLogInternalTriageEvent
0x1400b5278  mov     eax, 0C000000Dh
0x1400b527d  jmp     loc_1400B5C20
0x1400b5282  movzx   r13d, word ptr [rdi+0C28h]
0x1400b528a  xor     esi, esi
0x1400b528c  mov     edx, [rbx+0A14h]
0x1400b5292  mov     [rbp+57h+var_70], r13w
0x1400b5297  test    r10b, dl
0x1400b529a  jz      loc_1400B5390
0x1400b52a0  mov     al, [rdi+9168h]
0x1400b52a6  and     al, 0FDh
0x1400b52a8  shr     edx, 5
0x1400b52ab  and     dl, 2
0x1400b52ae  mov     dword ptr [rbp+57h+var_50], esi
0x1400b52b1  or      dl, al
0x1400b52b3  mov     [rdi+9168h], dl
0x1400b52b9  and     dl, 0DFh
0x1400b52bc  mov     eax, [rbx+0A14h]
0x1400b52c2  shr     eax, 2
0x1400b52c5  and     al, r10b
0x1400b52c8  or      al, dl
0x1400b52ca  lea     rdx, [rbp+57h+var_50]; union SYSMM_IOMMU_STATE *
0x1400b52ce  mov     [rdi+9168h], al
0x1400b52d4  mov     rcx, [r8+0E0h]; struct SYSMM_ADAPTER *
0x1400b52db  call    ?SysMmQueryIommuState@@YAXPEBUSYSMM_ADAPTER@@PEATSYSMM_IOMMU_STATE@@@Z; SysMmQueryIommuState(SYSMM_ADAPTER const *,SYSMM_IOMMU_STATE *)
0x1400b52e0  mov     al, [rdi+9168h]
0x1400b52e6  mov     ecx, dword ptr [rbp+57h+var_50]
0x1400b52e9  and     al, 0FBh
0x1400b52eb  shr     ecx, 2
0x1400b52ee  and     cl, 1
0x1400b52f1  shl     cl, 2
0x1400b52f4  or      cl, al
0x1400b52f6  mov     [rdi+9168h], cl
0x1400b52fc  mov     rcx, [rdi+18h]; this
0x1400b5300  call    ?IsGpuVaIoMmuGlobalSupported@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsGpuVaIoMmuGlobalSupported(void)
0x1400b5305  neg     al
0x1400b5307  mov     r10b, 20h ; ' '
0x1400b530a  mov     al, [rdi+9168h]
0x1400b5310  sbb     cl, cl
0x1400b5312  and     al, 0F7h
0x1400b5314  and     cl, 8
0x1400b5317  or      cl, al
0x1400b5319  mov     al, cl
0x1400b531b  and     al, 0Eh
0x1400b531d  neg     al
0x1400b531f  sbb     dl, dl
0x1400b5321  and     cl, 0EFh
0x1400b5324  and     dl, 10h
0x1400b5327  or      dl, cl
0x1400b5329  mov     [rdi+9168h], dl
0x1400b532f  test    r10b, dl
0x1400b5332  jz      short loc_1400B5363
0x1400b5334  mov     eax, cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x1400b533a  test    r10b, al
0x1400b533d  jnz     short loc_1400B5355
0x1400b533f  mov     rax, [rdi+18h]
0x1400b5343  mov     ecx, [rax+1BCh]
0x1400b5349  test    cl, 4
0x1400b534c  jnz     short loc_1400B5355
0x1400b534e  mov     al, 40h ; '@'
0x1400b5350  test    cl, 8
0x1400b5353  jz      short loc_1400B5358
0x1400b5355  mov     al, sil
0x1400b5358  and     dl, 0BFh
0x1400b535b  or      dl, al
0x1400b535d  mov     [rdi+9168h], dl
0x1400b5363  cmp     r12d, 5017h
0x1400b536a  jnb     short loc_1400B5378
0x1400b536c  test    cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A, 100h; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x1400b5376  jz      short loc_1400B5385
0x1400b5378  mov     ecx, 1
0x1400b537d  or      [rdi+9169h], cl
0x1400b5383  jmp     short loc_1400B538A
0x1400b5385  mov     ecx, 1
0x1400b538a  mov     r9d, 40h ; '@'
0x1400b5390  mov     dl, [rdi+9168h]
0x1400b5396  test    dl, 0Ch
0x1400b5399  jnz     short loc_1400B5401
0x1400b539b  test    cl, r15b
0x1400b539e  jz      short loc_1400B53B2
0x1400b53a0  mov     [rdi+8DA2h], cl
0x1400b53a6  mov     [rdi+8DA4h], cl
0x1400b53ac  mov     [rdi+8DD0h], cl
0x1400b53b2  test    r15b, 2
0x1400b53b6  jz      short loc_1400B5401
0x1400b53b8  test    dword ptr [rbx+0A14h], 4000h
0x1400b53c2  jnz     short loc_1400B53FB
0x1400b53c4  call    cs:__imp_WdLogSingleEntry0
0x1400b53cb  nop     dword ptr [rax+rax+00h]
0x1400b53d0  mov     [rsp+0C0h+var_88], rsi
0x1400b53d5  lea     r9, aDmaRemappingRe; "DMA remapping requires the driver to su"...
0x1400b53dc  mov     eax, 70Ch
0x1400b53e1  mov     [rsp+0C0h+var_90], rsi
0x1400b53e6  mov     [rsp+0C0h+var_98], rsi
0x1400b53eb  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b53f1  mov     [rsp+0C0h+var_A0], rax
0x1400b53f6  jmp     loc_1400B526E
0x1400b53fb  mov     [rdi+8DA3h], cl
0x1400b5401  mov     eax, [rbx+0A10h]
0x1400b5407  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400b540b  shr     eax, 5
0x1400b540e  not     al
0x1400b5410  and     al, cl
0x1400b5412  mov     [rdi+2E0h], al
0x1400b5418  mov     al, [rdi+9169h]
0x1400b541e  mov     ecx, [rbx+0A14h]
0x1400b5424  shr     ecx, 0Eh
0x1400b5427  shl     cl, 3
0x1400b542a  xor     cl, al
0x1400b542c  and     cl, 8
0x1400b542f  xor     cl, al
0x1400b5431  mov     [rdi+9169h], cl
0x1400b5437  test    dl, 10h
0x1400b543a  jz      loc_1400B54F9
0x1400b5440  mov     ecx, cs:dword_1400864CC
0x1400b5446  test    ecx, ecx
0x1400b5448  jz      loc_1400B54F9
0x1400b544e  mov     eax, cs:dword_1400864D0
0x1400b5454  cmp     ecx, 10000h
0x1400b545a  mov     r8d, 100h
0x1400b5460  mov     [rsp+0C0h+var_A0], rax
0x1400b5465  cmovbe  r8, r9
0x1400b5469  mov     r9d, ecx
0x1400b546c  lea     rcx, [rdi+91D0h]
0x1400b5473  call    ?Initialize@DXGK_LOG@@QEAAJIW4DXGK_POOL_FLAGS@@_K1@Z; DXGK_LOG::Initialize(uint,DXGK_POOL_FLAGS,unsigned __int64,unsigned __int64)
0x1400b5478  mov     ecx, cs:dword_1400864D4
0x1400b547e  lea     eax, [r15+31h]
0x1400b5482  mul     rcx
0x1400b5485  mov     edx, 32356956h
0x1400b548a  mov     r8d, 100h
0x1400b5490  cmovb   rax, r15
0x1400b5494  mov     rcx, rax
0x1400b5497  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400b549c  mov     [rdi+91F0h], rax
0x1400b54a3  test    rax, rax
0x1400b54a6  jnz     short loc_1400B54F9
0x1400b54a8  lock inc cs:dword_140086880
0x1400b54af  lea     ecx, [rax+6]
0x1400b54b2  call    cs:__imp_WdLogSingleEntry0
0x1400b54b9  nop     dword ptr [rax+rax+00h]
0x1400b54be  mov     eax, 737h
0x1400b54c3  lea     r9, aFailedToAlloca; "Failed to allocate _PageMappingHistoryE"...
0x1400b54ca  mov     [rsp+0C0h+var_88], rsi
0x1400b54cf  mov     edx, 40001h
0x1400b54d4  mov     [rsp+0C0h+var_90], rsi
0x1400b54d9  mov     [rsp+0C0h+var_98], rsi
0x1400b54de  mov     [rsp+0C0h+var_A0], rax
0x1400b54e3  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b54e9  call    DxgkLogInternalTriageEvent
0x1400b54ee  mov     r14d, 0C0000017h
0x1400b54f4  jmp     loc_1400B5BA7
0x1400b54f9  mov     ebx, 1
0x1400b54fe  test    [rdi+916Ah], bl
0x1400b5504  jz      loc_1400B5599
0x1400b550a  xorps   xmm0, xmm0
0x1400b550d  lea     rdx, [rbp+57h+var_50]; struct _DXGKARG_FEATURE_INTELLIGENT_CARVEOUT_QUERY_PREFERENCES *
0x1400b5511  mov     rcx, r14; this
0x1400b5514  movups  [rbp+57h+var_50], xmm0
0x1400b5518  call    ?DdiIntelligentCarveoutQueryPreferences@ADAPTER_RENDER@@QEAAXPEAU_DXGKARG_FEATURE_INTELLIGENT_CARVEOUT_QUERY_PREFERENCES@@@Z; ADAPTER_RENDER::DdiIntelligentCarveoutQueryPreferences(_DXGKARG_FEATURE_INTELLIGENT_CARVEOUT_QUERY_PREFERENCES *)
0x1400b551d  lea     rcx, [rbp+57h+var_50]
0x1400b5521  call    ValidateIntelligentCarveoutPreferences
0x1400b5526  test    al, al
0x1400b5528  jnz     short loc_1400B5535
0x1400b552a  mov     r14d, 0C000000Dh
0x1400b5530  jmp     loc_1400B5BA7
0x1400b5535  lea     rdx, ?_DedicatedPartitionLock@VIDMM_GLOBAL@@2U_EX_PUSH_LOCK@@A; struct _EX_PUSH_LOCK *
0x1400b553c  lea     rcx, [rbp+57h+var_68]; this
0x1400b5540  call    ??0DXGAUTOEXPUSHLOCKEXCLUSIVE@@QEAA@QEAU_EX_PUSH_LOCK@@@Z; DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(_EX_PUSH_LOCK * const)
0x1400b5545  mov     rax, cs:?_DedicatedPartitionCurrentSize@VIDMM_GLOBAL@@2_KA; unsigned __int64 VIDMM_GLOBAL::_DedicatedPartitionCurrentSize
0x1400b554c  mov     rbx, qword ptr [rbp+57h+var_50]
0x1400b5550  cmp     rbx, rax
0x1400b5553  jbe     short loc_1400B558B
0x1400b5555  sub     rbx, rax
0x1400b5558  mov     rdx, rbx; unsigned __int64
0x1400b555b  call    ?TransferPagesToDedicatedPartition@VIDMM_GLOBAL@@QEAAJ_K@Z; VIDMM_GLOBAL::TransferPagesToDedicatedPartition(unsigned __int64)
0x1400b5560  test    eax, eax
0x1400b5562  js      short loc_1400B556D
0x1400b5564  add     cs:?_DedicatedPartitionCurrentSize@VIDMM_GLOBAL@@2_KA, rbx; unsigned __int64 VIDMM_GLOBAL::_DedicatedPartitionCurrentSize
0x1400b556b  jmp     short loc_1400B558B
0x1400b556d  movsxd  rdx, eax
0x1400b5570  mov     ecx, 3
0x1400b5575  call    cs:__imp_WdLogSingleEntry1
0x1400b557c  nop     dword ptr [rax+rax+00h]
0x1400b5581  mov     cs:WdLogGlobalForLineNumber, 76Ah
0x1400b558b  lea     rcx, [rbp+57h+var_68]; this
0x1400b558f  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x1400b5594  mov     ebx, 1
0x1400b5599  mov     eax, 8
0x1400b559e  mov     r8d, 40h ; '@'
0x1400b55a4  mul     r13
0x1400b55a7  mov     edx, 30356956h
0x1400b55ac  cmovb   rax, r15
0x1400b55b0  mov     rcx, rax
0x1400b55b3  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400b55b8  mov     [rdi+8E80h], rax
0x1400b55bf  test    rax, rax
0x1400b55c2  jnz     short loc_1400B5614
0x1400b55c4  lock add cs:dword_140086864, ebx
0x1400b55cb  lea     ecx, [rax+6]
0x1400b55ce  call    cs:__imp_WdLogSingleEntry0
0x1400b55d5  nop     dword ptr [rax+rax+00h]
0x1400b55da  mov     eax, 777h
0x1400b55df  lea     r9, aCouldnTAllocat_45; "Couldn't allocate VIDMM_PHYSICAL_ADAPTE"...
0x1400b55e6  mov     [rsp+0C0h+var_88], rsi
0x1400b55eb  mov     edx, 40001h
0x1400b55f0  mov     [rsp+0C0h+var_90], rsi
0x1400b55f5  mov     [rsp+0C0h+var_98], rsi
0x1400b55fa  mov     [rsp+0C0h+var_A0], rax
0x1400b55ff  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b5605  call    DxgkLogInternalTriageEvent
0x1400b560a  mov     eax, 0C0000017h
0x1400b560f  jmp     loc_1400B5C20
0x1400b5614  movzx   r15d, si
0x1400b5618  cmp     si, r13w
0x1400b561c  jnb     loc_1400B57AD
0x1400b5622  mov     rax, [rdi+18h]
0x1400b5626  mov     rcx, [rdi+10h]; this
0x1400b562a  movzx   r12d, r15w
0x1400b562e  imul    r14, r12, 160h
0x1400b5635  movzx   edx, r15w; unsigned int
0x1400b5639  add     r14, [rax+0C20h]
0x1400b5640  mov     qword ptr [rbp+57h+var_50], r14
0x1400b5644  call    ?GetGpuMmuCaps@ADAPTER_RENDER@@QEBAPEBUDXGADAPTER_GPUMMUCAPS@@I@Z; ADAPTER_RENDER::GetGpuMmuCaps(uint)
0x1400b5649  test    byte ptr [rdi+9169h], 20h
0x1400b5650  mov     r13, rax
0x1400b5653  mov     edx, 30356956h
0x1400b5658  mov     r8d, 40h ; '@'
  ... truncated ...
```
