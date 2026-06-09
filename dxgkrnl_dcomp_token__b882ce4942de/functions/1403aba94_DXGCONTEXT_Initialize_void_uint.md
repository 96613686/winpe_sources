# DXGCONTEXT::Initialize(void *,uint)

- ea: `0x1403aba94`
- end: `0x1403ad34b`
- name: `?Initialize@DXGCONTEXT@@QEAAJPEAXI@Z`
- size: `6327`
- prototype: `__int64 __fastcall(DXGCONTEXT *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1403ab4a4`

## callees

- `0x140003498`
- `0x14000d7d0`
- `0x140012380`
- `0x14001a7d4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x14002e110`
- `0x14002fdc0`
- `0x140033920`
- `0x1400378f0`
- `0x140043e58`
- `0x140045cf8`
- `0x14004aad8`
- `0x14004af68`
- `0x14004ea54`
- `0x1400522ac`
- `0x140052cc8`
- `0x1400594c8`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140196f20`
- `0x1401e53c4`
- `0x1401e5484`
- `0x140243530`
- `0x14028c94c`
- `0x1403179c4`
- `0x140323854`
- `0x140352dcc`
- `0x1403aba94`
- `0x1403ed68c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403abee2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ad319`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403abee2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ad319`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403abed6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403ad30d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403abed6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403ad30d`
- `ntoskrnl!ExAllocatePool2` at `0x1403abb2d`
- `ntoskrnl!ExAllocatePool2` at `0x1403acf40`
- `ntoskrnl!ExAllocatePool2` at `0x1403ad1d5`
- `ntoskrnl!ExAllocatePool2` at `0x1403abb2d`
- `ntoskrnl!ExAllocatePool2` at `0x1403acf40`
- `ntoskrnl!ExAllocatePool2` at `0x1403ad1d5`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1403ac60d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1403ac60d`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1403ad00d`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1403ad132`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1403ad00d`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1403ad132`
- `watchdog!WdLogSingleEntry2` at `0x1403abc6f`
- `watchdog!WdLogSingleEntry2` at `0x1403ac4c2`
- `watchdog!WdLogSingleEntry2` at `0x1403aca0a`
- `watchdog!WdLogSingleEntry2` at `0x1403acad5`
- `watchdog!WdLogSingleEntry2` at `0x1403acc3c`
- `watchdog!WdLogSingleEntry2` at `0x1403accce`
- `watchdog!WdLogSingleEntry2` at `0x1403ace66`
- `watchdog!WdLogSingleEntry2` at `0x1403ace9a`
- `watchdog!WdLogSingleEntry2` at `0x1403ad056`
- `watchdog!WdLogSingleEntry2` at `0x1403ad076`
- `watchdog!WdLogSingleEntry2` at `0x1403ad184`
- `watchdog!WdLogSingleEntry2` at `0x1403ad21c`
- `watchdog!WdLogSingleEntry2` at `0x1403abc6f`
- `watchdog!WdLogSingleEntry2` at `0x1403ac4c2`
- `watchdog!WdLogSingleEntry2` at `0x1403aca0a`
- `watchdog!WdLogSingleEntry2` at `0x1403acad5`
- `watchdog!WdLogSingleEntry2` at `0x1403acc3c`
- `watchdog!WdLogSingleEntry2` at `0x1403accce`
- `watchdog!WdLogSingleEntry2` at `0x1403ace66`
- `watchdog!WdLogSingleEntry2` at `0x1403ace9a`
- `watchdog!WdLogSingleEntry2` at `0x1403ad056`
- `watchdog!WdLogSingleEntry2` at `0x1403ad076`
- `watchdog!WdLogSingleEntry2` at `0x1403ad184`
- `watchdog!WdLogSingleEntry2` at `0x1403ad21c`
- `watchdog!WdLogSingleEntry3` at `0x1403acdec`
- `watchdog!WdLogSingleEntry3` at `0x1403acef7`
- `watchdog!WdLogSingleEntry3` at `0x1403acf64`
- `watchdog!WdLogSingleEntry3` at `0x1403acfe5`
- `watchdog!WdLogSingleEntry3` at `0x1403ad10a`
- `watchdog!WdLogSingleEntry3` at `0x1403ad1fc`
- `watchdog!WdLogSingleEntry3` at `0x1403acdec`
- `watchdog!WdLogSingleEntry3` at `0x1403acef7`
- `watchdog!WdLogSingleEntry3` at `0x1403acf64`
- `watchdog!WdLogSingleEntry3` at `0x1403acfe5`
- `watchdog!WdLogSingleEntry3` at `0x1403ad10a`
- `watchdog!WdLogSingleEntry3` at `0x1403ad1fc`
- `watchdog!WdLogSingleEntry0` at `0x1403abbbf`
- `watchdog!WdLogSingleEntry0` at `0x1403abda1`
- `watchdog!WdLogSingleEntry0` at `0x1403abe77`
- `watchdog!WdLogSingleEntry0` at `0x1403ac0ff`
- `watchdog!WdLogSingleEntry0` at `0x1403ac131`
- `watchdog!WdLogSingleEntry0` at `0x1403ac15a`
- `watchdog!WdLogSingleEntry0` at `0x1403ac181`
- `watchdog!WdLogSingleEntry0` at `0x1403ac205`
- `watchdog!WdLogSingleEntry0` at `0x1403ac59c`
- `watchdog!WdLogSingleEntry0` at `0x1403ac711`
- `watchdog!WdLogSingleEntry0` at `0x1403ac752`
- `watchdog!WdLogSingleEntry0` at `0x1403ac785`
- `watchdog!WdLogSingleEntry0` at `0x1403ac7e4`
- `watchdog!WdLogSingleEntry0` at `0x1403ac83f`
- `watchdog!WdLogSingleEntry0` at `0x1403acbc4`
- `watchdog!WdLogSingleEntry0` at `0x1403acd32`
- `watchdog!WdLogSingleEntry0` at `0x1403ad2b1`
- `watchdog!WdLogSingleEntry0` at `0x1403abbbf`
- `watchdog!WdLogSingleEntry0` at `0x1403abda1`
- `watchdog!WdLogSingleEntry0` at `0x1403abe77`
- `watchdog!WdLogSingleEntry0` at `0x1403ac0ff`
- `watchdog!WdLogSingleEntry0` at `0x1403ac131`
- `watchdog!WdLogSingleEntry0` at `0x1403ac15a`
- `watchdog!WdLogSingleEntry0` at `0x1403ac181`
- `watchdog!WdLogSingleEntry0` at `0x1403ac205`
- `watchdog!WdLogSingleEntry0` at `0x1403ac59c`
- `watchdog!WdLogSingleEntry0` at `0x1403ac711`
- `watchdog!WdLogSingleEntry0` at `0x1403ac752`
- `watchdog!WdLogSingleEntry0` at `0x1403ac785`
- `watchdog!WdLogSingleEntry0` at `0x1403ac7e4`
- `watchdog!WdLogSingleEntry0` at `0x1403ac83f`
- `watchdog!WdLogSingleEntry0` at `0x1403acbc4`
- `watchdog!WdLogSingleEntry0` at `0x1403acd32`
- `watchdog!WdLogSingleEntry0` at `0x1403ad2b1`
- `watchdog!WdLogSingleEntry1` at `0x1403abb4e`
- `watchdog!WdLogSingleEntry1` at `0x1403ac25d`
- `watchdog!WdLogSingleEntry1` at `0x1403ac625`
- `watchdog!WdLogSingleEntry1` at `0x1403abb4e`
- `watchdog!WdLogSingleEntry1` at `0x1403ac25d`
- `watchdog!WdLogSingleEntry1` at `0x1403ac625`

## string_xrefs

- `0x1403acd62`: `NULL == m_pCommandDmaBuffer`
- `0x1403abbef`: `The physical adapter requres GpuVaIoMmu but a non-virtual context is created`
- `0x1403abdb2`: `Failed to create context on the host`
- `0x1403ac5cc`: `Failed to allocate lookaside list for private driver data`
- `0x1403ac28c`: `DdiCreateContext() failed with status 0x%I64x`
- `0x1403ac654`: `Failed to initialize lookaside list for private driver data 0x%x`

## pseudocode

```c
__int64 __fastcall DXGCONTEXT::Initialize(DXGCONTEXT *this, void *a2, unsigned int a3)
{
  __int64 v4; // r14
  char *v6; // r15
  unsigned int *v7; // rbx
  _QWORD *Pool2; // rax
  __int64 result; // rax
  struct DXGPROCESS *Current; // rax
  unsigned int v11; // r8d
  __int64 v12; // r9
  __int64 v13; // rcx
  int v15; // edx
  enum _D3DKMT_CLIENTHINT v16; // r15d
  struct _D3DDDI_CREATECONTEXTFLAGS v17; // ebx
  unsigned int v18; // esi
  unsigned int v19; // r14d
  unsigned int v20; // edi
  unsigned int HostProcess; // eax
  unsigned int ContextVirtual; // eax
  __int64 v23; // rax
  const wchar_t *v24; // r9
  _QWORD *v25; // rdi
  __int64 v26; // rsi
  _DWORD *v27; // r15
  unsigned __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // rbx
  int v32; // ecx
  int v33; // r8d
  DXGCONTEXT *v34; // rax
  __int64 v35; // r8
  __int64 v36; // r11
  int v37; // eax
  unsigned int v38; // ebx
  ADAPTER_RENDER **v39; // rdi
  __int64 v40; // rcx
  int v41; // eax
  ADAPTER_RENDER *v42; // rcx
  __int64 v43; // r14
  int v44; // r10d
  __int64 v45; // r9
  bool v46; // al
  int v47; // eax
  int v48; // r9d
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rax
  struct _LOOKASIDE_LIST_EX *v53; // rax
  NTSTATUS v54; // eax
  __int64 v55; // rax
  char v56; // al
  __int64 v57; // rcx
  __int64 v58; // r8
  int v59; // ecx
  struct VIDSCH_HW_CONTEXT *v60; // r8
  __int64 v61; // r9
  unsigned int v62; // edx
  int v63; // edx
  unsigned int v64; // r8d
  __int64 v65; // r9
  struct _VIDSCH_CONTEXT *Context; // rax
  int v67; // r8d
  int v68; // esi
  _QWORD *v69; // rsi
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  int v71; // eax
  __int64 v72; // r14
  unsigned __int64 ULong64FromUser; // rax
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *v74; // rax
  int v75; // eax
  struct DXGGLOBAL *Global; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  unsigned __int64 v79; // rax
  SIZE_T *v80; // rsi
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *v81; // rax
  int v82; // eax
  __int64 v83; // rax
  unsigned __int64 v84; // rax
  SIZE_T *v85; // rsi
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *v86; // rax
  int v87; // eax
  struct DXGGLOBAL *v88; // rax
  __int64 v89; // rax
  __int64 v90; // rsi
  unsigned __int64 v91; // rbx
  __int64 v92; // rax
  __int64 v93; // r8
  __int64 v94; // rbx
  char v95[8]; // [rsp+80h] [rbp-148h] BYREF
  unsigned int *v96; // [rsp+88h] [rbp-140h] BYREF
  int v97; // [rsp+90h] [rbp-138h] BYREF
  unsigned int v98; // [rsp+94h] [rbp-134h]
  char *v99; // [rsp+98h] [rbp-130h]
  __int64 v100; // [rsp+A0h] [rbp-128h] BYREF
  void *v101; // [rsp+A8h] [rbp-120h]
  int v102; // [rsp+B0h] [rbp-118h] BYREF
  int v103; // [rsp+B4h] [rbp-114h] BYREF
  DXGCONTEXT *v104; // [rsp+B8h] [rbp-110h]
  _DWORD *v105; // [rsp+C0h] [rbp-108h]
  unsigned int *v106; // [rsp+C8h] [rbp-100h] BYREF
  _BYTE *v107; // [rsp+D0h] [rbp-F8h] BYREF
  __int64 v108; // [rsp+D8h] [rbp-F0h] BYREF
  _D3DKMT_CREATEHWQUEUE v109; // [rsp+E0h] [rbp-E8h] BYREF
  _DXGKARG_CREATECONTEXT v110; // [rsp+110h] [rbp-B8h] BYREF
  _BYTE v111[36]; // [rsp+160h] [rbp-68h] BYREF

  v98 = a3;
  v4 = (__int64)a2;
  v101 = a2;
  v104 = this;
  v6 = (char *)this + 16;
  v99 = (char *)this + 16;
  v7 = *(unsigned int **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL);
  v96 = v7;
  DXGADAPTER::NotifyContextCreation((DXGADAPTER *)v7, this, 1u, *((_DWORD *)this + 95));
  if ( (int)v7[712] >= 9472 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 16, 1265072196);
    *((_QWORD *)this + 59) = Pool2;
    if ( !Pool2 )
    {
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 905;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"DXGCONTEXT (0x%p) failed to allocate m_pDxgkrnlContextHandle",
        (__int64)this,
        0,
        0,
        0,
        0);
      return 3221225495LL;
    }
    *Pool2 = this;
  }
  if ( *((_BYTE *)this + 433) && !*((_BYTE *)this + 430) )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 914;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"The physical adapter requres GpuVaIoMmu but a non-virtual context is created",
      914,
      0,
      0,
      0,
      0);
    return 3221225485LL;
  }
  Current = DXGPROCESS::GetCurrent();
  DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE((DXGHANDLETABLELOCKEXCLUSIVE *)v111, Current);
  v11 = HMGRTABLE::AllocHandle(*(_QWORD *)(*(_QWORD *)v6 + 40LL) + 280LL, this, 7);
  v105 = (_DWORD *)((char *)this + 24);
  *((_DWORD *)this + 6) = v11;
  if ( !v11 )
  {
    WdLogSingleEntry2(3, this);
    WdLogGlobalForLineNumber = 934;
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v111);
    return 3221225495LL;
  }
  v12 = *(_QWORD *)(*(_QWORD *)v6 + 40LL);
  v13 = 16LL * ((v11 >> 6) & 0xFFFFFF);
  if ( ((v11 >> 6) & 0xFFFFFF) < *(_DWORD *)(v12 + 296) )
  {
    v15 = *(_DWORD *)(*(_QWORD *)(v12 + 280) + v13 + 8);
    if ( ((v11 >> 25) & 0x60) == (*(_BYTE *)(*(_QWORD *)(v12 + 280) + v13 + 8) & 0x60)
      && (v15 & 0x2000) == 0
      && (v15 & 0x1F) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)(v12 + 280) + v13 + 8) |= 0x2000u;
    }
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v111);
  if ( *((_BYTE *)v7 + 209) )
  {
    *((_BYTE *)this + 434) = 1;
    v16 = *((_DWORD *)this + 36);
    v17.0 = (struct _D3DDDI_CREATECONTEXTFLAGS::$95B81DE25B1D554D835F0ED864974D68::$C6DD82D22F896EDD365A25DACAAAF57F)*((_DWORD *)this + 98);
    v18 = *((_DWORD *)this + 96);
    v19 = *((_DWORD *)this + 95);
    v20 = *(_DWORD *)(*(_QWORD *)v99 + 472LL);
    HostProcess = DXGPROCESS::GetHostProcess(*(DXGPROCESS **)(*(_QWORD *)v99 + 40LL));
    ContextVirtual = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendCreateContextVirtual(
                       (DXG_GUEST_VIRTUALGPU_VMBUS *)(v96 + 1194),
                       HostProcess,
                       v20,
                       v19,
                       v18,
                       v17,
                       v16,
                       v98,
                       v101);
    *((_DWORD *)this + 7) = ContextVirtual;
    if ( !ContextVirtual )
    {
      WdLogSingleEntry0(2);
      v23 = 958;
      v24 = L"Failed to create context on the host";
LABEL_21:
      WdLogGlobalForLineNumber = v23;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v24, v23, 0, 0, 0, 0);
      return 3221225473LL;
    }
    v25 = v99;
    v26 = *(_QWORD *)(*(_QWORD *)v99 + 40LL);
    v27 = v105;
    v28 = (unsigned int)*v105;
    DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(v26 + 248));
    v29 = ((unsigned int)v28 >> 6) & 0xFFFFFF;
    if ( (unsigned int)v29 < *(_DWORD *)(v26 + 296) )
    {
      v30 = *(_QWORD *)(v26 + 280);
      if ( (((unsigned int)v28 >> 25) & 0x60) == (*(_BYTE *)(v30 + 16 * v29 + 8) & 0x60)
        && (*(_DWORD *)(v30 + 16 * v29 + 8) & 0x1F) != 0 )
      {
        v31 = 16 * ((v28 >> 6) & 0xFFFFFF);
        if ( (*(_DWORD *)(v30 + v31 + 8) & 0x2000) == 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 224;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"m_pEntryTable[GetIndex(hObject)].Destroyed",
            224,
            0,
            0,
            0,
            0);
        }
        *(_DWORD *)(v31 + *(_QWORD *)(v26 + 280) + 8) &= ~0x2000u;
      }
    }
    *(_QWORD *)(v26 + 256) = 0;
    ExReleasePushLockExclusiveEx(v26 + 248, 0);
    KeLeaveCriticalRegion();
    if ( bTracingEnabled )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x800) != 0 )
        McTemplateK0pqqqqqqqqppp_EtwWriteTransfer(
          v32,
          (unsigned int)EventCreateContext,
          v33,
          *v25,
          *((_DWORD *)this + 95),
          *((_DWORD *)this + 96),
          *((_DWORD *)this + 50),
          *((_DWORD *)this + 51),
          *((_DWORD *)this + 52),
          *((_DWORD *)this + 53),
          *((_DWORD *)this + 54),
          0,
          (char)this,
          *v27,
          0);
    }
    return 0;
  }
  memset(&v110, 0, sizeof(v110));
  if ( (int)v7[712] < 9472 )
    v34 = this;
  else
    v34 = (DXGCONTEXT *)*((_QWORD *)this + 59);
  *((_QWORD *)this + 24) = v34;
  v110.hContext = v34;
  LODWORD(v35) = *((_DWORD *)this + 95);
  v110.NodeOrdinal = v35;
  v110.EngineAffinity = *((_DWORD *)this + 96);
  v110.pPrivateDriverData = (void *)v4;
  v110.PrivateDriverDataSize = a3;
  v36 = *(_QWORD *)v6;
  if ( (*(_BYTE *)(*(_QWORD *)v6 + 1917LL) & 8) != 0 || (v37 = 0, *((_DWORD *)this + 36) == 2) )
    v37 = 2;
  v97 = *((unsigned __int8 *)this + 430);
  v110.Flags.Value = v37 ^ ((unsigned __int8)v37 ^ (unsigned __int8)(4 * v97)) & 4;
  v38 = *((_DWORD *)this + 98);
  if ( (v38 & 0x40) != 0 )
    v110.Flags.Value = v37 ^ ((unsigned __int8)v37 ^ (unsigned __int8)(4 * v97)) & 4 | 0x20;
  v39 = (ADAPTER_RENDER **)(v36 + 16);
  if ( (v38 & 8) != 0 )
  {
    *((_DWORD *)this + 98) = v38 & 0xFFFFFFEF;
  }
  else
  {
    v42 = *v39;
    if ( (v38 & 0x10) != 0 )
    {
      if ( *(int *)(*((_QWORD *)v42 + 2) + 3116LL) < 2500 )
      {
        WdLogSingleEntry0(2);
        v23 = 1031;
        v24 = L"Context passes HwQueueSupported flag set, but the driver WDDM version is < 2.5";
        goto LABEL_21;
      }
      v43 = *((unsigned int *)this + 97);
      if ( !ADAPTER_RENDER::NodeSupportsContextScheduling(v42, *((_DWORD *)this + 97), v35) )
      {
        WdLogSingleEntry0(2);
        v23 = 1037;
        v24 = L"Context passes HwQueueSupported flag set, but GPU node doesn't support context scheduling";
        goto LABEL_21;
      }
      if ( !(_BYTE)v97 )
      {
        WdLogSingleEntry0(2);
        v23 = 1043;
        v24 = L"Only virtual contexts can use HwQueueSupported flag";
        goto LABEL_21;
      }
      if ( v38 >= 0x80 )
      {
        WdLogSingleEntry0(2);
        v23 = 1049;
        v24 = L"Context is setting non-zero Reserved flags at the creation time.";
        goto LABEL_21;
      }
      v110.Flags.Value = v44 | 0x10;
      v45 = *(_QWORD *)(352 * v43 + *(_QWORD *)(*((_QWORD *)*v39 + 2) + 3104LL) + 32);
      if ( v45 )
        v46 = (*(_BYTE *)(74 * v35 + v45 + 68) & 2) != 0;
      else
        v46 = 0;
      *((_BYTE *)this + 296) = v46;
      v4 = (__int64)v101;
    }
    else if ( ADAPTER_RENDER::NodeSupportsContextScheduling(v42, *((_DWORD *)this + 97), v35) )
    {
      WdLogSingleEntry0(2);
      v23 = 1061;
      v24 = L"Context doesn't pass HwQueueSupported flag, but GPU node requires hardware scheduling";
      goto LABEL_21;
    }
  }
  LODWORD(v40) = *(_DWORD *)(*((_QWORD *)*v39 + 2) + 2576LL);
  if ( (v40 & 1) != 0 )
  {
    v41 = *((_DWORD *)this + 98);
    if ( (v41 & 0x20) != 0 )
    {
      result = CheckNoKmdAccessPrivateData(v98, (void *)v4, 0xFF000003);
      LODWORD(v4) = result;
      if ( (int)result < 0 )
        return result;
      v110.hContext = 0;
      v110.ContextInfo.DmaBufferPrivateDataSize = 264;
      v110.ContextInfo.AllocationListSize = 128;
      v110.ContextInfo.PatchLocationListSize = 128;
      v110.ContextInfo.DmaBufferSize = 1024;
    }
    else if ( (v41 & 8) != 0 )
    {
      LODWORD(v4) = 0;
      v110.hContext = 0;
    }
    else
    {
      v47 = ADAPTER_RENDER::DdiCreateContext(*v39, *(void **)(v36 + 616), &v110);
      v4 = v47;
      if ( v47 < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1096;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"DdiCreateContext() failed with status 0x%I64x",
          v4,
          0,
          0,
          0,
          0);
        LODWORD(v35) = (_DWORD)v96;
        v96 = *(unsigned int **)(v96 + 103);
        if ( (unsigned int)dword_14015C6A0 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_14015C6A0, 0x400000000000LL) )
          {
            LOWORD(v97) = 0;
            v49 = *(_QWORD *)v6;
            v50 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 40LL) + 64LL);
            *(_OWORD *)v111 = *(_OWORD *)(v50 + 144);
            v107 = v111;
            v51 = *(_QWORD *)(*(_QWORD *)(v49 + 40) + 64LL);
            if ( v51 )
              v52 = *(_QWORD *)(v51 + 96);
            else
              v52 = 0;
            v108 = v52;
            v95[0] = *((_BYTE *)this + 144);
            v106 = v96;
            v102 = *(_DWORD *)(v35 + 424);
            v103 = *(_DWORD *)(v35 + 420);
            LODWORD(v96) = v4;
            v100 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(
              v50,
              (unsigned int)byte_14013ED03,
              v35,
              v48,
              (__int64)&v100,
              (__int64)&v96,
              (__int64)&v103,
              (__int64)&v102,
              (__int64)&v106,
              (__int64)v95,
              (__int64)&v108,
              (__int64)&v107,
              (__int64)&v97);
          }
        }
      }
    }
    *((_DWORD *)this + 10) |= 1u;
  }
  else
  {
    v110.hContext = *(HANDLE *)(v36 + 616);
    v110.ContextInfo.DmaBufferSize = *(_DWORD *)(v36 + 624);
    v110.ContextInfo.DmaBufferSegmentSet = *(_DWORD *)(v36 + 628);
    v110.ContextInfo.AllocationListSize = *(_DWORD *)(v36 + 636);
    v110.ContextInfo.PatchLocationListSize = *(_DWORD *)(v36 + 640);
    v110.ContextInfo.DmaBufferPrivateDataSize = *(_DWORD *)(v36 + 632);
    *((_DWORD *)this + 10) &= ~1u;
    LODWORD(v4) = 0;
  }
  if ( (int)v4 < 0 )
    return (unsigned int)v4;
  if ( (*(_DWORD *)(*(_QWORD *)v6 + 464LL) == 2 || *((_DWORD *)this + 36) == 2)
    && v110.ContextInfo.AllocationListSize != 256 )
  {
    WdLogSingleEntry2(3, 256);
    WdLogGlobalForLineNumber = 1148;
    v110.ContextInfo.AllocationListSize = 256;
  }
  *((_QWORD *)this + 23) = v110.hContext;
  *(DXGK_CONTEXTINFO *)((char *)this + 200) = v110.ContextInfo;
  if ( *((_DWORD *)this + 52) )
  {
    v53 = (struct _LOOKASIDE_LIST_EX *)operator new(96, 1682995268, 64);
    *((_QWORD *)this + 61) = v53;
    if ( !v53 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1162;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to allocate lookaside list for private driver data",
        1162,
        0,
        0,
        0,
        0);
      return 3221225495LL;
    }
    v54 = ExInitializeLookasideListEx(
            v53,
            0,
            0,
            (POOL_TYPE)512,
            0,
            (unsigned int)(*((_DWORD *)this + 52) + 16),
            0x64507844u,
            0);
    v4 = v54;
    if ( v54 < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1178;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to initialize lookaside list for private driver data 0x%x",
        v4,
        0,
        0,
        0,
        0);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(*((void **)this + 61));
      *((_QWORD *)this + 61) = 0;
      return (unsigned int)v4;
    }
  }
  if ( (*(_BYTE *)&v110.ContextInfo.Caps.0 & 2) != 0 )
  {
    v55 = *(_QWORD *)v6;
    *(_BYTE *)(v55 + 1919) = 1;
    *(_BYTE *)(*(_QWORD *)(v55 + 40) + 337LL) = 1;
  }
  if ( *((_BYTE *)this + 430) )
  {
    v35 = *(_QWORD *)(352LL * *((unsigned int *)this + 97)
                    + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 16LL) + 16LL) + 3104LL)
                    + 32);
    v40 = 74LL * *((unsigned int *)this + 95);
    v56 = 0;
    if ( v35 )
    {
      v56 = *(_BYTE *)(v35 + v40 + 73);
      LOBYTE(v40) = *(_BYTE *)(v35 + v40 + 72) != 0;
    }
    else
    {
      LOBYTE(v40) = 0;
    }
    if ( *((_BYTE *)this + 433) )
    {
      if ( (*(_BYTE *)&v110.ContextInfo.Caps.0 & 4) != 0 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 1198;
        return 3221225473LL;
      }
    }
    else if ( (*(_BYTE *)&v110.ContextInfo.Caps.0 & 4) != 0 || v56 && !(_BYTE)v40 )
    {
      if ( !v56 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 1207;
        return 3221225473LL;
      }
      *((_BYTE *)this + 431) = 1;
    }
    else
    {
      *((_BYTE *)this + 432) = 1;
    }
  }
  else if ( !*((_DWORD *)this + 50) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1218;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"m_bUseGpuVa || m_ContextInfo.DmaBufferSize",
      1218,
      0,
      0,
      0,
      0);
  }
  if ( !*((_BYTE *)this + 430) )
  {
    if ( !*((_DWORD *)this + 53) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 1219;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"m_bUseGpuVa || m_ContextInfo.AllocationListSize",
        1219,
        0,
        0,
        0,
        0);
    }
    if ( !*((_BYTE *)this + 430) && !*((_DWORD *)this + 54) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 1220;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"m_bUseGpuVa || m_ContextInfo.PatchLocationListSize",
        1220,
        0,
        0,
        0,
        0);
    }
  }
  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x800) != 0 )
    McTemplateK0pqqqqqqqqppp_EtwWriteTransfer(
      v40,
      (unsigned int)EventCreateContext,
      v35,
      *(_QWORD *)v6,
      *((_DWORD *)this + 95),
      *((_DWORD *)this + 96),
      *((_DWORD *)this + 50),
      *((_DWORD *)this + 51),
      *((_DWORD *)this + 52),
      *((_DWORD *)this + 53),
      *((_DWORD *)this + 54),
      0,
      (char)this,
      *v105,
      0);
  v57 = *(_QWORD *)v6;
  if ( (*((_DWORD *)this + 98) & 0x10) != 0 )
  {
    memset(v111, 0, sizeof(v111));
    *(_DWORD *)&v111[20] = *(_DWORD *)(*(_QWORD *)(v57 + 40) + 416LL);
    *(_DWORD *)&v111[24] = DXGPROCESS::GetDefaultQos(*(_QWORD *)(*(_QWORD *)v6 + 40LL));
    *(_DWORD *)&v111[4] = *((_DWORD *)this + 95);
    *(_DWORD *)&v111[8] = *((_DWORD *)this + 97);
    *(_DWORD *)v111 = *(_DWORD *)v111 & 0xFFFFEBDD
                    | (2
                     * (*((_DWORD *)this + 98) & 1
                      | (4 * (*((_DWORD *)this + 98) & 4 | (16 * (*((_DWORD *)this + 98) & 0x28 | 0x11))))));
    *(_DWORD *)&v111[32] = *((_DWORD *)this + 36);
    v60 = (struct VIDSCH_HW_CONTEXT *)(*(__int64 (__fastcall **)(DXGCONTEXT *, _BYTE *))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v58 + 16) + 736LL) + 8LL)
                                                                                       + 240LL))(
                                        this,
                                        v111);
    *((_QWORD *)this + 35) = v60;
    if ( !v60 )
    {
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 1266;
      return 3221225495LL;
    }
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x800) != 0 )
    {
      McTemplateK0pppp_EtwWriteTransfer(
        v59,
        (unsigned int)EventAssociateContext,
        (_DWORD)v60,
        (_DWORD)this,
        (char)v60,
        *((_QWORD *)this + 23),
        *((_QWORD *)this + 24));
      v60 = (struct VIDSCH_HW_CONTEXT *)*((_QWORD *)this + 35);
    }
    memset(&v109, 0, sizeof(v109));
    v109.Flags.Value = (*((_DWORD *)this + 98) >> 2) & 8;
    LODWORD(v96) = VIDSCH_EXPORT::VidSchCreateHwQueue(
                     *(VIDSCH_EXPORT **)(*(_QWORD *)(*(_QWORD *)v6 + 16LL) + 736LL),
                     0,
                     v60,
                     &v109,
                     (struct VIDSCH_HW_QUEUE **)this + 36,
                     0);
    if ( (int)v96 < 0 )
    {
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 1285;
      return (unsigned int)v96;
    }
  }
  else
  {
    memset(v111, 0, sizeof(v111));
    *(_DWORD *)&v111[12] = 0;
    *(_DWORD *)&v111[20] = *(_DWORD *)(*(_QWORD *)(v57 + 40) + 416LL);
    *(_DWORD *)&v111[24] = DXGPROCESS::GetDefaultQos(*(_QWORD *)(*(_QWORD *)v6 + 40LL));
    *(_DWORD *)&v111[4] = *((_DWORD *)this + 95);
    *(_DWORD *)&v111[8] = *((_DWORD *)this + 97);
    v62 = *(_DWORD *)v111 & 0xFFFFEFFD | (2 * (*((_DWORD *)this + 98) & 1 | ((*((_DWORD *)this + 98) & 0x20) << 6)));
    *(_DWORD *)v111 = v62;
    *(_DWORD *)&v111[32] = *((_DWORD *)this + 36);
    if ( *((_BYTE *)this + 430) )
      *(_DWORD *)v111 = v62 | 0x80;
    if ( DXGADAPTER::IsDxgmms2(*(DXGADAPTER **)(*(_QWORD *)(v61 + 16) + 16LL)) )
    {
      if ( v64 >= 0x80 )
      {
        WdLogSingleEntry0(2);
        v23 = 1316;
        v24 = L"Context is setting non-zero Reserved flags at the creation time.";
        goto LABEL_21;
      }
      *(_DWORD *)v111 = v63 & 0xFFFFFBDF | (8 * (v64 & 4 | (16 * (v64 & 8))));
    }
    Context = VIDSCH_EXPORT::VidSchCreateContext(
                *(VIDSCH_EXPORT **)(*(_QWORD *)(v65 + 16) + 736LL),
                this,
                (struct _VIDSCH_CONTEXT_DATA *)v111);
    *((_QWORD *)this + 32) = Context;
    if ( !Context )
    {
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 1330;
      return 3221225495LL;
    }
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x800) != 0 )
      McTemplateK0pppp_EtwWriteTransfer(
        (_DWORD)Context,
        (unsigned int)EventAssociateContext,
        v67,
        (_DWORD)this,
        (char)Context,
        *((_QWORD *)this + 23),
        *((_QWORD *)this + 24));
  }
  if ( !*((_BYTE *)this + 430) || *(_DWORD *)(*(_QWORD *)v6 + 464LL) == 2 || *((_DWORD *)this + 36) == 2 )
  {
    v68 = DXGCONTEXT::EnsurePriviledgedDmaPool(this, *((_DWORD *)this + 53), *((_DWORD *)this + 54));
    if ( v68 < 0 )
    {
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 1348;
      return (unsigned int)v68;
    }
  }
  v69 = (_QWORD *)((char *)this + 48);
  *((_QWORD *)this + 6) = *((unsigned int *)this + 50);
  *((_DWORD *)this + 18) = *((_DWORD *)this + 53);
  v106 = (unsigned int *)((char *)this + 104);
  *((_DWORD *)this + 26) = *((_DWORD *)this + 54);
  if ( *((_BYTE *)this + 430) )
  {
    if ( *((_QWORD *)this + 44) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 1369;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NULL == m_pCommandDmaBuffer", 1369, 0, 0, 0, 0);
    }
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 16LL) + 16LL) + 444LL) & 0x10) != 0 && v101 && v98 == 16 )
    {
      VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
      v71 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, char *, int, int))VirtualMemoryInterface)(
              -1,
              (char *)this + 56,
              0,
              (char *)this + 48,
              12288,
              4);
      LODWORD(v4) = v71;
      if ( v71 < 0 )
      {
        WdLogSingleEntry3(3, this, *v69, v71);
        WdLogGlobalForLineNumber = 1390;
        return (unsigned int)v4;
      }
      v72 = *((_QWORD *)v101 + 1);
      v100 = *(_QWORD *)v101;
      ULong64FromUser = RtlReadULong64FromUser(v72);
      if ( !v72 || ULong64FromUser < 8 || !v100 )
      {
        WdLogSingleEntry2(3, this);
        WdLogGlobalForLineNumber = 1415;
        return 3221225485LL;
      }
      RtlWriteULong64ToUser(v100, *((_QWORD *)this + 7));
      RtlWriteULong64ToUser(v72, *v69);
    }
  }
  else
  {
    v74 = DxgkGetVirtualMemoryInterface();
    v75 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, char *, int, int))v74)(
            -1,
            (char *)this + 56,
            0,
            (char *)this + 48,
            12288,
            4);
    LODWORD(v4) = v75;
    if ( v75 < 0 )
    {
      WdLogSingleEntry3(3, this, *v69, v75);
      WdLogGlobalForLineNumber = 1444;
      return (unsigned int)v4;
    }
    Global = DXGGLOBAL::GetGlobal();
    if ( DXGVALIDATION::IsValidationEnabledForAdapterInCallerContext(
           (struct DXGGLOBAL *)((char *)Global + 1668),
           *(struct DXGADAPTER **)(*(_QWORD *)(*(_QWORD *)v6 + 16LL) + 16LL)) )
    {
      v77 = ExAllocatePool2(256, *v69, 1265072196);
      *((_QWORD *)this + 8) = v77;
      if ( !v77 )
      {
        WdLogSingleEntry3(3, this, *v69, -1073741801);
        WdLogGlobalForLineNumber = 1458;
        return 3221225495LL;
      }
    }
  }
  v78 = *((unsigned int *)this + 18);
  if ( (_DWORD)v78 )
  {
    v79 = 8 * v78;
    if ( v79 > 0xFFFFFFFF )
    {
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 1476;
      return 3221225621LL;
    }
    v80 = (SIZE_T *)((char *)this + 80);
    *((_QWORD *)this + 10) = (unsigned int)v79;
    v81 = DxgkGetVirtualMemoryInterface();
    v82 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, char *, int, int))v81)(
            -1,
            (char *)this + 88,
            0,
            (char *)this + 80,
            12288,
            4);
    LODWORD(v4) = v82;
    if ( v82 < 0 )
    {
      WdLogSingleEntry3(3, this, *v80, v82);
      WdLogGlobalForLineNumber = 1497;
      return (unsigned int)v4;
    }
    *((_QWORD *)this + 12) = MmSecureVirtualMemory(*((PVOID *)this + 11), *v80, 4u);
    if ( !*((_QWORD *)this + 12) )
    {
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 1521;
      return 3221225495LL;
    }
  }
  v83 = *v106;
  if ( !(_DWORD)v83 )
    goto LABEL_169;
  v84 = 24 * v83;
  if ( v84 > 0xFFFFFFFF )
  {
    WdLogSingleEntry2(3, this);
    WdLogGlobalForLineNumber = 1538;
    return 3221225621LL;
  }
  v85 = (SIZE_T *)((char *)this + 112);
  v100 = (__int64)this + 112;
  *((_QWORD *)this + 14) = (unsigned int)v84;
  v86 = DxgkGetVirtualMemoryInterface();
  v87 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, char *, int, int))v86)(
          -1,
          (char *)this + 120,
          0,
          (char *)this + 112,
          12288,
          4);
  LODWORD(v4) = v87;
  if ( v87 < 0 )
  {
    WdLogSingleEntry3(3, this, *v85, v87);
    WdLogGlobalForLineNumber = 1557;
    return (unsigned int)v4;
  }
  *((_QWORD *)this + 17) = MmSecureVirtualMemory(*((PVOID *)this + 15), *v85, 4u);
  if ( !*((_QWORD *)this + 17) )
  {
    WdLogSingleEntry2(3, this);
    WdLogGlobalForLineNumber = 1581;
    return 3221225495LL;
  }
  v88 = DXGGLOBAL::GetGlobal();
  v6 = v99;
  if ( DXGVALIDATION::IsValidationEnabledForAdapterInCallerContext(
         (struct DXGGLOBAL *)((char *)v88 + 1668),
         *(struct DXGADAPTER **)(*(_QWORD *)(*(_QWORD *)v99 + 16LL) + 16LL)) )
  {
    v89 = ExAllocatePool2(256, *v85, 1265072196);
    *((_QWORD *)this + 16) = v89;
    if ( !v89 )
    {
      WdLogSingleEntry3(3, this, *v85, -1073741801);
      WdLogGlobalForLineNumber = 1595;
      return 3221225495LL;
    }
  }
LABEL_169:
  v90 = *(_QWORD *)(*(_QWORD *)v6 + 40LL);
  v91 = (unsigned int)*v105;
  DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(v90 + 248));
  v92 = ((unsigned int)v91 >> 6) & 0xFFFFFF;
  if ( (unsigned int)v92 < *(_DWORD *)(v90 + 296) )
  {
    v93 = *(_QWORD *)(v90 + 280);
    if ( (((unsigned int)v91 >> 25) & 0x60) == (*(_BYTE *)(v93 + 16 * v92 + 8) & 0x60)
      && (*(_DWORD *)(v93 + 16 * v92 + 8) & 0x1F) != 0 )
    {
      v94 = 16 * ((v91 >> 6) & 0xFFFFFF);
      if ( (*(_DWORD *)(v94 + v93 + 8) & 0x2000) == 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 224;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"m_pEntryTable[GetIndex(hObject)].Destroyed",
          224,
          0,
          0,
          0,
          0);
      }
      *(_DWORD *)(v94 + *(_QWORD *)(v90 + 280) + 8) &= ~0x2000u;
    }
  }
  *(_QWORD *)(v90 + 256) = 0;
  ExReleasePushLockExclusiveEx(v90 + 248, 0);
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x1403aba94  push    rbx
0x1403aba96  push    rsi
0x1403aba97  push    rdi
0x1403aba98  push    r12
0x1403aba9a  push    r13
0x1403aba9c  push    r14
0x1403aba9e  push    r15
0x1403abaa0  sub     rsp, 190h
0x1403abaa7  mov     rax, cs:__security_cookie
0x1403abaae  xor     rax, rsp
0x1403abab1  mov     [rsp+1C8h+var_40], rax
0x1403abab9  mov     edi, r8d
0x1403ababc  mov     [rsp+1C8h+var_134], r8d
0x1403abac4  mov     r14, rdx
0x1403abac7  mov     [rsp+1C8h+var_120], rdx
0x1403abacf  mov     r13, rcx
0x1403abad2  mov     [rsp+1C8h+var_110], rcx
0x1403abada  lea     r15, [rcx+10h]
0x1403abade  mov     [rsp+1C8h+var_130], r15
0x1403abae6  mov     rax, [r15]
0x1403abae9  mov     rcx, [rax+10h]
0x1403abaed  mov     rbx, [rcx+10h]
0x1403abaf1  mov     [rsp+1C8h+var_140], rbx
0x1403abaf9  mov     r9d, [r13+17Ch]; unsigned int
0x1403abb00  mov     r8b, 1; unsigned __int8
0x1403abb03  mov     rdx, r13; struct DXGCONTEXT *
0x1403abb06  mov     rcx, rbx; this
0x1403abb09  call    ?NotifyContextCreation@DXGADAPTER@@QEAAXPEAVDXGCONTEXT@@EI@Z; DXGADAPTER::NotifyContextCreation(DXGCONTEXT *,uchar,uint)
0x1403abb0e  mov     esi, 2500h
0x1403abb13  cmp     [rbx+0B20h], esi
0x1403abb19  jl      loc_1403ABBA5
0x1403abb1f  mov     edx, 10h
0x1403abb24  lea     ecx, [rdx+30h]
0x1403abb27  mov     r8d, 4B677844h
0x1403abb2d  call    cs:__imp_ExAllocatePool2
0x1403abb34  nop     dword ptr [rax+rax+00h]
0x1403abb39  mov     [r13+1D8h], rax
0x1403abb40  xor     r12d, r12d
0x1403abb43  test    rax, rax
0x1403abb46  jnz     short loc_1403ABBA0
0x1403abb48  mov     rdx, r13
0x1403abb4b  lea     ecx, [rax+6]
0x1403abb4e  call    cs:__imp_WdLogSingleEntry1
0x1403abb55  nop     dword ptr [rax+rax+00h]
0x1403abb5a  mov     cs:WdLogGlobalForLineNumber, 389h
0x1403abb64  mov     [rsp+1C8h+var_188], r12
0x1403abb69  mov     qword ptr [rsp+1C8h+Depth], r12
0x1403abb6e  mov     qword ptr [rsp+1C8h+Tag], r12
0x1403abb73  mov     [rsp+1C8h+Size], r12
0x1403abb78  mov     qword ptr [rsp+1C8h+Flags], r13
0x1403abb7d  lea     r9, aDxgcontext0xPF_0; "DXGCONTEXT (0x%p) failed to allocate m_"...
0x1403abb84  mov     edx, 40001h
0x1403abb89  mov     r8d, 0FFFFFFFFh
0x1403abb8f  xor     ecx, ecx
0x1403abb91  call    DxgkLogInternalTriageEvent
0x1403abb96  mov     eax, 0C0000017h
0x1403abb9b  jmp     loc_1403AD327
0x1403abba0  mov     [rax], r13
0x1403abba3  jmp     short loc_1403ABBA8
0x1403abba5  xor     r12d, r12d
0x1403abba8  cmp     [r13+1B1h], r12b
0x1403abbaf  jz      short loc_1403ABC12
0x1403abbb1  cmp     [r13+1AEh], r12b
0x1403abbb8  jnz     short loc_1403ABC12
0x1403abbba  mov     ecx, 2
0x1403abbbf  call    cs:__imp_WdLogSingleEntry0
0x1403abbc6  nop     dword ptr [rax+rax+00h]
0x1403abbcb  mov     eax, 392h
0x1403abbd0  mov     cs:WdLogGlobalForLineNumber, eax
0x1403abbd6  mov     [rsp+1C8h+var_188], r12
0x1403abbdb  mov     qword ptr [rsp+1C8h+Depth], r12
0x1403abbe0  mov     qword ptr [rsp+1C8h+Tag], r12
0x1403abbe5  mov     [rsp+1C8h+Size], r12
0x1403abbea  mov     qword ptr [rsp+1C8h+Flags], rax
0x1403abbef  lea     r9, aThePhysicalAda; "The physical adapter requres GpuVaIoMmu"...
0x1403abbf6  mov     edx, 40000h
0x1403abbfb  xor     ecx, ecx
0x1403abbfd  mov     r8d, 0FFFFFFFFh
0x1403abc03  call    DxgkLogInternalTriageEvent
0x1403abc08  mov     eax, 0C000000Dh
0x1403abc0d  jmp     loc_1403AD327
0x1403abc12  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1403abc17  mov     rdx, rax; struct DXGPROCESS *
0x1403abc1a  lea     rcx, [rsp+1C8h+var_68]; this
0x1403abc22  call    ??0DXGHANDLETABLELOCKEXCLUSIVE@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE(DXGPROCESS *)
0x1403abc27  mov     rax, [r15]
0x1403abc2a  mov     rcx, [rax+28h]
0x1403abc2e  add     rcx, 118h
0x1403abc35  mov     [rsp+1C8h+Flags], r12d
0x1403abc3a  xor     r9d, r9d
0x1403abc3d  lea     r8d, [r9+7]
0x1403abc41  mov     rdx, r13
0x1403abc44  call    ?AllocHandle@HMGRTABLE@@QEAAIPEAXW4_HMGRENTRY_TYPE@@IH@Z; HMGRTABLE::AllocHandle(void *,_HMGRENTRY_TYPE,uint,int)
0x1403abc49  mov     r8d, eax
0x1403abc4c  lea     rax, [r13+18h]
0x1403abc50  mov     [rsp+1C8h+var_108], rax
0x1403abc58  mov     [rax], r8d
0x1403abc5b  test    r8d, r8d
0x1403abc5e  jnz     short loc_1403ABC97
0x1403abc60  mov     r8, 0FFFFFFFFC0000017h
0x1403abc67  mov     rdx, r13
0x1403abc6a  mov     ecx, 3
0x1403abc6f  call    cs:__imp_WdLogSingleEntry2
0x1403abc76  nop     dword ptr [rax+rax+00h]
0x1403abc7b  mov     cs:WdLogGlobalForLineNumber, 3A6h
0x1403abc85  lea     rcx, [rsp+1C8h+var_68]; this
0x1403abc8d  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1403abc92  jmp     loc_1403ABB96
0x1403abc97  mov     rax, [r15]
0x1403abc9a  mov     r9, [rax+28h]
0x1403abc9e  mov     eax, r8d
0x1403abca1  shr     eax, 6
0x1403abca4  and     eax, 0FFFFFFh
0x1403abca9  mov     ecx, eax
0x1403abcab  shl     rcx, 4
0x1403abcaf  cmp     eax, [r9+128h]
0x1403abcb6  jb      short loc_1403ABCBD
0x1403abcb8  mov     al, r12b
0x1403abcbb  jmp     short loc_1403ABCEA
0x1403abcbd  mov     rax, [r9+118h]
0x1403abcc4  mov     edx, [rax+rcx+8]
0x1403abcc8  shr     r8d, 19h
0x1403abccc  and     r8d, 60h
0x1403abcd0  mov     eax, edx
0x1403abcd2  and     eax, 60h
0x1403abcd5  cmp     r8b, al
0x1403abcd8  jnz     short loc_1403ABCB8
0x1403abcda  bt      edx, 0Dh
0x1403abcde  jb      short loc_1403ABCB8
0x1403abce0  test    dl, 1Fh
0x1403abce3  mov     al, r12b
0x1403abce6  jz      short loc_1403ABCEA
0x1403abce8  mov     al, 1
0x1403abcea  test    al, al
0x1403abcec  jz      short loc_1403ABCFB
0x1403abcee  mov     rax, [r9+118h]
0x1403abcf5  bts     dword ptr [rax+rcx+8], 0Dh
0x1403abcfb  lea     rcx, [rsp+1C8h+var_68]; this
0x1403abd03  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1403abd08  cmp     [rbx+0D1h], r12b
0x1403abd0f  jz      loc_1403ABF80
0x1403abd15  mov     byte ptr [r13+1B2h], 1
0x1403abd1d  mov     r15d, [r13+90h]
0x1403abd24  mov     ebx, [r13+188h]
0x1403abd2b  mov     esi, [r13+180h]
0x1403abd32  mov     r14d, [r13+17Ch]
0x1403abd39  mov     rcx, [rsp+1C8h+var_130]
0x1403abd41  mov     rcx, [rcx]
0x1403abd44  mov     edi, [rcx+1D8h]
0x1403abd4a  mov     rcx, [rcx+28h]; this
0x1403abd4e  call    ?GetHostProcess@DXGPROCESS@@QEAAIXZ; DXGPROCESS::GetHostProcess(void)
0x1403abd53  mov     rcx, [rsp+1C8h+var_140]
0x1403abd5b  add     rcx, 12A8h; this
0x1403abd62  mov     rdx, [rsp+1C8h+var_120]
0x1403abd6a  mov     [rsp+1C8h+var_188], rdx; void *
0x1403abd6f  mov     r9d, [rsp+1C8h+var_134]
0x1403abd77  mov     dword ptr [rsp+1C8h+Depth], r9d; unsigned int
0x1403abd7c  mov     [rsp+1C8h+Tag], r15d; enum _D3DKMT_CLIENTHINT
0x1403abd81  mov     dword ptr [rsp+1C8h+Size], ebx; struct _D3DDDI_CREATECONTEXTFLAGS
0x1403abd85  mov     [rsp+1C8h+Flags], esi; unsigned int
0x1403abd89  mov     r9d, r14d; unsigned int
0x1403abd8c  mov     r8d, edi; unsigned int
0x1403abd8f  mov     edx, eax; unsigned int
0x1403abd91  call    ?VmBusSendCreateContextVirtual@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAIIIIIU_D3DDDI_CREATECONTEXTFLAGS@@W4_D3DKMT_CLIENTHINT@@IPEAX@Z; DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendCreateContextVirtual(uint,uint,uint,uint,_D3DDDI_CREATECONTEXTFLAGS,_D3DKMT_CLIENTHINT,uint,void *)
0x1403abd96  mov     [r13+1Ch], eax
0x1403abd9a  test    eax, eax
0x1403abd9c  jnz     short loc_1403ABDF4
0x1403abd9e  lea     ecx, [rax+2]
0x1403abda1  call    cs:__imp_WdLogSingleEntry0
0x1403abda8  nop     dword ptr [rax+rax+00h]
0x1403abdad  mov     eax, 3BEh
0x1403abdb2  lea     r9, aFailedToCreate_27; "Failed to create context on the host"
0x1403abdb9  mov     r8d, 0FFFFFFFFh
0x1403abdbf  mov     [rsp+1C8h+var_188], r12
0x1403abdc4  mov     qword ptr [rsp+1C8h+Depth], r12
0x1403abdc9  mov     qword ptr [rsp+1C8h+Tag], r12
0x1403abdce  mov     [rsp+1C8h+Size], r12
0x1403abdd3  mov     cs:WdLogGlobalForLineNumber, eax
0x1403abdd9  mov     qword ptr [rsp+1C8h+Flags], rax
0x1403abdde  xor     ecx, ecx
0x1403abde0  mov     edx, 40000h
0x1403abde5  call    DxgkLogInternalTriageEvent
0x1403abdea  mov     eax, 0C0000001h
0x1403abdef  jmp     loc_1403AD327
0x1403abdf4  mov     rdi, [rsp+1C8h+var_130]
0x1403abdfc  mov     rax, [rdi]
0x1403abdff  mov     rsi, [rax+28h]
0x1403abe03  mov     r15, [rsp+1C8h+var_108]
0x1403abe0b  mov     ebx, [r15]
0x1403abe0e  lea     r14, [rsi+0F8h]
0x1403abe15  mov     rcx, r14; this
0x1403abe18  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x1403abe1d  mov     eax, ebx
0x1403abe1f  shr     eax, 6
0x1403abe22  mov     r9d, 0FFFFFFh
0x1403abe28  and     eax, r9d
0x1403abe2b  cmp     eax, [rsi+128h]
0x1403abe31  jnb     loc_1403ABECD
0x1403abe37  mov     r8, [rsi+118h]
0x1403abe3e  add     rax, rax
0x1403abe41  mov     edx, [r8+rax*8+8]
0x1403abe46  mov     ecx, ebx
0x1403abe48  shr     ecx, 19h
0x1403abe4b  and     ecx, 60h
0x1403abe4e  mov     eax, edx
0x1403abe50  and     eax, 60h
0x1403abe53  cmp     cl, al
0x1403abe55  jnz     short loc_1403ABECD
0x1403abe57  test    dl, 1Fh
0x1403abe5a  jz      short loc_1403ABECD
0x1403abe5c  shr     rbx, 6
0x1403abe60  and     rbx, r9
0x1403abe63  shl     rbx, 4
0x1403abe67  test    dword ptr [r8+rbx+8], 2000h
0x1403abe70  jnz     short loc_1403ABEC0
0x1403abe72  mov     ecx, 1
0x1403abe77  call    cs:__imp_WdLogSingleEntry0
0x1403abe7e  nop     dword ptr [rax+rax+00h]
0x1403abe83  mov     eax, 0E0h
0x1403abe88  mov     cs:WdLogGlobalForLineNumber, eax
0x1403abe8e  mov     [rsp+1C8h+var_188], r12
0x1403abe93  mov     qword ptr [rsp+1C8h+Depth], r12
0x1403abe98  mov     qword ptr [rsp+1C8h+Tag], r12
0x1403abe9d  mov     [rsp+1C8h+Size], r12
0x1403abea2  mov     qword ptr [rsp+1C8h+Flags], rax
0x1403abea7  lea     r9, aMPentrytableGe; "m_pEntryTable[GetIndex(hObject)].Destro"...
0x1403abeae  mov     edx, 40002h
0x1403abeb3  xor     ecx, ecx
0x1403abeb5  mov     r8d, 0FFFFFFFFh
0x1403abebb  call    DxgkLogInternalTriageEvent
0x1403abec0  mov     rax, [rsi+118h]
0x1403abec7  btr     dword ptr [rbx+rax+8], 0Dh
0x1403abecd  mov     [r14+8], r12
0x1403abed1  xor     edx, edx
0x1403abed3  mov     rcx, r14
0x1403abed6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1403abedd  nop     dword ptr [rax+rax+00h]
0x1403abee2  call    cs:__imp_KeLeaveCriticalRegion
0x1403abee9  nop     dword ptr [rax+rax+00h]
0x1403abeee  cmp     cs:bTracingEnabled, 0
0x1403abef5  jz      loc_1403AD325
0x1403abefb  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 8
0x1403abf02  jz      loc_1403AD325
0x1403abf08  mov     eax, [r15]
0x1403abf0b  mov     [rsp+1C8h+var_158], r12
0x1403abf10  mov     [rsp+1C8h+var_160], rax
0x1403abf15  mov     [rsp+1C8h+var_168], r13
0x1403abf1a  mov     dword ptr [rsp+1C8h+var_170], r12d
0x1403abf1f  mov     eax, [r13+0D8h]
0x1403abf26  mov     dword ptr [rsp+1C8h+var_178], eax
0x1403abf2a  mov     eax, [r13+0D4h]
0x1403abf31  mov     dword ptr [rsp+1C8h+var_180], eax
0x1403abf35  mov     eax, [r13+0D0h]
0x1403abf3c  mov     dword ptr [rsp+1C8h+var_188], eax
0x1403abf40  mov     eax, [r13+0CCh]
0x1403abf47  mov     dword ptr [rsp+1C8h+Depth], eax
0x1403abf4b  mov     eax, [r13+0C8h]
0x1403abf52  mov     [rsp+1C8h+Tag], eax
0x1403abf56  mov     eax, [r13+180h]
0x1403abf5d  mov     dword ptr [rsp+1C8h+Size], eax
0x1403abf61  mov     eax, [r13+17Ch]
0x1403abf68  mov     [rsp+1C8h+Flags], eax
0x1403abf6c  mov     r9, [rdi]
0x1403abf6f  lea     rdx, EventCreateContext
0x1403abf76  call    McTemplateK0pqqqqqqqqppp_EtwWriteTransfer
0x1403abf7b  jmp     loc_1403AD325
0x1403abf80  xor     edx, edx; Val
0x1403abf82  lea     r8d, [rdx+48h]; Size
0x1403abf86  lea     rcx, [rsp+1C8h+var_B8]; void *
0x1403abf8e  call    memset
0x1403abf93  cmp     [rbx+0B20h], esi
0x1403abf99  jl      short loc_1403ABFA4
0x1403abf9b  mov     rax, [r13+1D8h]
0x1403abfa2  jmp     short loc_1403ABFA7
0x1403abfa4  mov     rax, r13
0x1403abfa7  mov     [r13+0C0h], rax
0x1403abfae  mov     [rsp+1C8h+var_B8.hContext], rax
0x1403abfb6  mov     r8d, [r13+17Ch]; unsigned int
0x1403abfbd  mov     [rsp+1C8h+var_B8.NodeOrdinal], r8d
0x1403abfc5  mov     eax, [r13+180h]
0x1403abfcc  mov     [rsp+1C8h+var_B8.EngineAffinity], eax
0x1403abfd3  mov     [rsp+1C8h+var_B8.pPrivateDriverData], r14
0x1403abfdb  mov     [rsp+1C8h+var_B8.PrivateDriverDataSize], edi
0x1403abfe2  mov     r11, [r15]
0x1403abfe5  mov     esi, 2
0x1403abfea  test    byte ptr [r11+77Dh], 8
0x1403abff2  jnz     short loc_1403AC000
0x1403abff4  cmp     [r13+90h], esi
0x1403abffb  mov     eax, r12d
0x1403abffe  jnz     short loc_1403AC002
0x1403ac000  mov     eax, esi
0x1403ac002  movzx   ecx, byte ptr [r13+1AEh]
0x1403ac00a  mov     [rsp+1C8h+var_138], ecx
0x1403ac011  mov     r10d, ecx
0x1403ac014  shl     r10d, 2
0x1403ac018  xor     r10d, eax
0x1403ac01b  and     r10d, 4
0x1403ac01f  xor     r10d, eax
0x1403ac022  mov     dword ptr [rsp+1C8h+var_B8.Flags], r10d
0x1403ac02a  mov     ebx, [r13+188h]
  ... truncated ...
```
