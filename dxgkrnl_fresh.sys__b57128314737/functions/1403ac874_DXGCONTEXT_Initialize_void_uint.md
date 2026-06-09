# DXGCONTEXT::Initialize(void *,uint)

- ea: `0x1403ac874`
- end: `0x1403ae12b`
- name: `?Initialize@DXGCONTEXT@@QEAAJPEAXI@Z`
- size: `6327`
- prototype: `__int64 __fastcall(DXGCONTEXT *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1403ac284`

## callees

- `0x140003498`
- `0x14000d990`
- `0x140012540`
- `0x14001a874`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14002e2e0`
- `0x14002ff90`
- `0x140033af0`
- `0x140037ac0`
- `0x1400440b8`
- `0x140045f58`
- `0x14004acd8`
- `0x14004b168`
- `0x14004ec54`
- `0x14005248c`
- `0x140052ea8`
- `0x140059738`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x14019af20`
- `0x1401e7744`
- `0x1401e7804`
- `0x1402461d0`
- `0x1402932ac`
- `0x14031e734`
- `0x14032a5c4`
- `0x14035327c`
- `0x1403ac874`
- `0x1403edb4c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403accc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ae0f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403accc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ae0f9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403accb6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403ae0ed`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403accb6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403ae0ed`
- `ntoskrnl!ExAllocatePool2` at `0x1403ac90d`
- `ntoskrnl!ExAllocatePool2` at `0x1403add20`
- `ntoskrnl!ExAllocatePool2` at `0x1403adfb5`
- `ntoskrnl!ExAllocatePool2` at `0x1403ac90d`
- `ntoskrnl!ExAllocatePool2` at `0x1403add20`
- `ntoskrnl!ExAllocatePool2` at `0x1403adfb5`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1403ad3ed`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1403ad3ed`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1403added`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1403adf12`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1403added`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1403adf12`
- `watchdog!WdLogSingleEntry2` at `0x1403aca4f`
- `watchdog!WdLogSingleEntry2` at `0x1403ad2a2`
- `watchdog!WdLogSingleEntry2` at `0x1403ad7ea`
- `watchdog!WdLogSingleEntry2` at `0x1403ad8b5`
- `watchdog!WdLogSingleEntry2` at `0x1403ada1c`
- `watchdog!WdLogSingleEntry2` at `0x1403adaae`
- `watchdog!WdLogSingleEntry2` at `0x1403adc46`
- `watchdog!WdLogSingleEntry2` at `0x1403adc7a`
- `watchdog!WdLogSingleEntry2` at `0x1403ade36`
- `watchdog!WdLogSingleEntry2` at `0x1403ade56`
- `watchdog!WdLogSingleEntry2` at `0x1403adf64`
- `watchdog!WdLogSingleEntry2` at `0x1403adffc`
- `watchdog!WdLogSingleEntry2` at `0x1403aca4f`
- `watchdog!WdLogSingleEntry2` at `0x1403ad2a2`
- `watchdog!WdLogSingleEntry2` at `0x1403ad7ea`
- `watchdog!WdLogSingleEntry2` at `0x1403ad8b5`
- `watchdog!WdLogSingleEntry2` at `0x1403ada1c`
- `watchdog!WdLogSingleEntry2` at `0x1403adaae`
- `watchdog!WdLogSingleEntry2` at `0x1403adc46`
- `watchdog!WdLogSingleEntry2` at `0x1403adc7a`
- `watchdog!WdLogSingleEntry2` at `0x1403ade36`
- `watchdog!WdLogSingleEntry2` at `0x1403ade56`
- `watchdog!WdLogSingleEntry2` at `0x1403adf64`
- `watchdog!WdLogSingleEntry2` at `0x1403adffc`
- `watchdog!WdLogSingleEntry3` at `0x1403adbcc`
- `watchdog!WdLogSingleEntry3` at `0x1403adcd7`
- `watchdog!WdLogSingleEntry3` at `0x1403add44`
- `watchdog!WdLogSingleEntry3` at `0x1403addc5`
- `watchdog!WdLogSingleEntry3` at `0x1403adeea`
- `watchdog!WdLogSingleEntry3` at `0x1403adfdc`
- `watchdog!WdLogSingleEntry3` at `0x1403adbcc`
- `watchdog!WdLogSingleEntry3` at `0x1403adcd7`
- `watchdog!WdLogSingleEntry3` at `0x1403add44`
- `watchdog!WdLogSingleEntry3` at `0x1403addc5`
- `watchdog!WdLogSingleEntry3` at `0x1403adeea`
- `watchdog!WdLogSingleEntry3` at `0x1403adfdc`
- `watchdog!WdLogSingleEntry0` at `0x1403ac99f`
- `watchdog!WdLogSingleEntry0` at `0x1403acb81`
- `watchdog!WdLogSingleEntry0` at `0x1403acc57`
- `watchdog!WdLogSingleEntry0` at `0x1403acedf`
- `watchdog!WdLogSingleEntry0` at `0x1403acf11`
- `watchdog!WdLogSingleEntry0` at `0x1403acf3a`
- `watchdog!WdLogSingleEntry0` at `0x1403acf61`
- `watchdog!WdLogSingleEntry0` at `0x1403acfe5`
- `watchdog!WdLogSingleEntry0` at `0x1403ad37c`
- `watchdog!WdLogSingleEntry0` at `0x1403ad4f1`
- `watchdog!WdLogSingleEntry0` at `0x1403ad532`
- `watchdog!WdLogSingleEntry0` at `0x1403ad565`
- `watchdog!WdLogSingleEntry0` at `0x1403ad5c4`
- `watchdog!WdLogSingleEntry0` at `0x1403ad61f`
- `watchdog!WdLogSingleEntry0` at `0x1403ad9a4`
- `watchdog!WdLogSingleEntry0` at `0x1403adb12`
- `watchdog!WdLogSingleEntry0` at `0x1403ae091`
- `watchdog!WdLogSingleEntry0` at `0x1403ac99f`
- `watchdog!WdLogSingleEntry0` at `0x1403acb81`
- `watchdog!WdLogSingleEntry0` at `0x1403acc57`
- `watchdog!WdLogSingleEntry0` at `0x1403acedf`
- `watchdog!WdLogSingleEntry0` at `0x1403acf11`
- `watchdog!WdLogSingleEntry0` at `0x1403acf3a`
- `watchdog!WdLogSingleEntry0` at `0x1403acf61`
- `watchdog!WdLogSingleEntry0` at `0x1403acfe5`
- `watchdog!WdLogSingleEntry0` at `0x1403ad37c`
- `watchdog!WdLogSingleEntry0` at `0x1403ad4f1`
- `watchdog!WdLogSingleEntry0` at `0x1403ad532`
- `watchdog!WdLogSingleEntry0` at `0x1403ad565`
- `watchdog!WdLogSingleEntry0` at `0x1403ad5c4`
- `watchdog!WdLogSingleEntry0` at `0x1403ad61f`
- `watchdog!WdLogSingleEntry0` at `0x1403ad9a4`
- `watchdog!WdLogSingleEntry0` at `0x1403adb12`
- `watchdog!WdLogSingleEntry0` at `0x1403ae091`
- `watchdog!WdLogSingleEntry1` at `0x1403ac92e`
- `watchdog!WdLogSingleEntry1` at `0x1403ad03d`
- `watchdog!WdLogSingleEntry1` at `0x1403ad405`
- `watchdog!WdLogSingleEntry1` at `0x1403ac92e`
- `watchdog!WdLogSingleEntry1` at `0x1403ad03d`
- `watchdog!WdLogSingleEntry1` at `0x1403ad405`

## string_xrefs

- `0x1403adb42`: `NULL == m_pCommandDmaBuffer`
- `0x1403acb92`: `Failed to create context on the host`
- `0x1403ac9cf`: `The physical adapter requres GpuVaIoMmu but a non-virtual context is created`
- `0x1403ad06c`: `DdiCreateContext() failed with status 0x%I64x`
- `0x1403ad434`: `Failed to initialize lookaside list for private driver data 0x%x`
- `0x1403ad3ac`: `Failed to allocate lookaside list for private driver data`

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
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r9
  unsigned int v64; // edx
  int v65; // edx
  unsigned int v66; // r8d
  __int64 v67; // r9
  struct _VIDSCH_CONTEXT *Context; // rax
  int v69; // r8d
  int v70; // eax
  unsigned int v71; // esi
  _QWORD *v72; // rsi
  __int64 v73; // rcx
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  int v75; // eax
  __int64 v76; // r14
  unsigned __int64 ULong64FromUser; // rax
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *v78; // rax
  int v79; // eax
  struct DXGGLOBAL *Global; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // r8
  unsigned __int64 v84; // rax
  SIZE_T *v85; // rsi
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *v86; // rax
  int v87; // eax
  __int64 v88; // rax
  __int64 v89; // r8
  unsigned __int64 v90; // rax
  SIZE_T *v91; // rsi
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *v92; // rax
  int v93; // eax
  struct DXGGLOBAL *v94; // rax
  __int64 v95; // rax
  __int64 v96; // rsi
  unsigned __int64 v97; // rbx
  __int64 v98; // rax
  __int64 v99; // r8
  __int64 v100; // rbx
  char v101[8]; // [rsp+80h] [rbp-148h] BYREF
  unsigned int *v102; // [rsp+88h] [rbp-140h] BYREF
  int v103; // [rsp+90h] [rbp-138h] BYREF
  unsigned int v104; // [rsp+94h] [rbp-134h]
  char *v105; // [rsp+98h] [rbp-130h]
  __int64 v106; // [rsp+A0h] [rbp-128h] BYREF
  void *v107; // [rsp+A8h] [rbp-120h]
  int v108; // [rsp+B0h] [rbp-118h] BYREF
  int v109; // [rsp+B4h] [rbp-114h] BYREF
  DXGCONTEXT *v110; // [rsp+B8h] [rbp-110h]
  _DWORD *v111; // [rsp+C0h] [rbp-108h]
  unsigned int *v112; // [rsp+C8h] [rbp-100h] BYREF
  _BYTE *v113; // [rsp+D0h] [rbp-F8h] BYREF
  __int64 v114; // [rsp+D8h] [rbp-F0h] BYREF
  _D3DKMT_CREATEHWQUEUE v115; // [rsp+E0h] [rbp-E8h] BYREF
  _DXGKARG_CREATECONTEXT v116; // [rsp+110h] [rbp-B8h] BYREF
  _BYTE v117[36]; // [rsp+160h] [rbp-68h] BYREF

  v104 = a3;
  v4 = (__int64)a2;
  v107 = a2;
  v110 = this;
  v6 = (char *)this + 16;
  v105 = (char *)this + 16;
  v7 = *(unsigned int **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL);
  v102 = v7;
  DXGADAPTER::NotifyContextCreation((DXGADAPTER *)v7, this, 1u, *((_DWORD *)this + 95));
  if ( (int)v7[716] >= 9472 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 16, 1265072196);
    *((_QWORD *)this + 59) = Pool2;
    if ( !Pool2 )
    {
      WdLogSingleEntry1(6, this);
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
  DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE((DXGHANDLETABLELOCKEXCLUSIVE *)v117, Current);
  v11 = HMGRTABLE::AllocHandle(*(_QWORD *)(*(_QWORD *)v6 + 40LL) + 280LL, this, 7);
  v111 = (_DWORD *)((char *)this + 24);
  *((_DWORD *)this + 6) = v11;
  if ( !v11 )
  {
    WdLogSingleEntry2(3, this, -1073741801);
    WdLogGlobalForLineNumber = 934;
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v117);
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
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v117);
  if ( *((_BYTE *)v7 + 209) )
  {
    *((_BYTE *)this + 434) = 1;
    v16 = *((_DWORD *)this + 36);
    v17.0 = (struct _D3DDDI_CREATECONTEXTFLAGS::$95B81DE25B1D554D835F0ED864974D68::$C6DD82D22F896EDD365A25DACAAAF57F)*((_DWORD *)this + 98);
    v18 = *((_DWORD *)this + 96);
    v19 = *((_DWORD *)this + 95);
    v20 = *(_DWORD *)(*(_QWORD *)v105 + 472LL);
    HostProcess = DXGPROCESS::GetHostProcess(*(DXGPROCESS **)(*(_QWORD *)v105 + 40LL));
    ContextVirtual = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendCreateContextVirtual(
                       (DXG_GUEST_VIRTUALGPU_VMBUS *)(v102 + 1198),
                       HostProcess,
                       v20,
                       v19,
                       v18,
                       v17,
                       v16,
                       v104,
                       v107);
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
    v25 = v105;
    v26 = *(_QWORD *)(*(_QWORD *)v105 + 40LL);
    v27 = v111;
    v28 = (unsigned int)*v111;
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
          (unsigned int)&EventCreateContext,
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
  memset(&v116, 0, sizeof(v116));
  if ( (int)v7[716] < 9472 )
    v34 = this;
  else
    v34 = (DXGCONTEXT *)*((_QWORD *)this + 59);
  *((_QWORD *)this + 24) = v34;
  v116.hContext = v34;
  LODWORD(v35) = *((_DWORD *)this + 95);
  v116.NodeOrdinal = v35;
  v116.EngineAffinity = *((_DWORD *)this + 96);
  v116.pPrivateDriverData = (void *)v4;
  v116.PrivateDriverDataSize = a3;
  v36 = *(_QWORD *)v6;
  if ( (*(_BYTE *)(*(_QWORD *)v6 + 1917LL) & 8) != 0 || (v37 = 0, *((_DWORD *)this + 36) == 2) )
    v37 = 2;
  v103 = *((unsigned __int8 *)this + 430);
  v116.Flags.Value = v37 ^ ((unsigned __int8)v37 ^ (unsigned __int8)(4 * v103)) & 4;
  v38 = *((_DWORD *)this + 98);
  if ( (v38 & 0x40) != 0 )
    v116.Flags.Value = v37 ^ ((unsigned __int8)v37 ^ (unsigned __int8)(4 * v103)) & 4 | 0x20;
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
      if ( *(int *)(*((_QWORD *)v42 + 2) + 3132LL) < 2500 )
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
      if ( !(_BYTE)v103 )
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
      v116.Flags.Value = v44 | 0x10;
      v45 = *(_QWORD *)(352 * v43 + *(_QWORD *)(*((_QWORD *)*v39 + 2) + 3120LL) + 32);
      if ( v45 )
        v46 = (*(_BYTE *)(74 * v35 + v45 + 68) & 2) != 0;
      else
        v46 = 0;
      *((_BYTE *)this + 296) = v46;
      v4 = (__int64)v107;
    }
    else if ( ADAPTER_RENDER::NodeSupportsContextScheduling(v42, *((_DWORD *)this + 97), v35) )
    {
      WdLogSingleEntry0(2);
      v23 = 1061;
      v24 = L"Context doesn't pass HwQueueSupported flag, but GPU node requires hardware scheduling";
      goto LABEL_21;
    }
  }
  LODWORD(v40) = *(_DWORD *)(*((_QWORD *)*v39 + 2) + 2592LL);
  if ( (v40 & 1) != 0 )
  {
    v41 = *((_DWORD *)this + 98);
    if ( (v41 & 0x20) != 0 )
    {
      result = CheckNoKmdAccessPrivateData(v104, (void *)v4, 0xFF000003);
      LODWORD(v4) = result;
      if ( (int)result < 0 )
        return result;
      v116.hContext = 0;
      v116.ContextInfo.DmaBufferPrivateDataSize = 264;
      v116.ContextInfo.AllocationListSize = 128;
      v116.ContextInfo.PatchLocationListSize = 128;
      v116.ContextInfo.DmaBufferSize = 1024;
    }
    else if ( (v41 & 8) != 0 )
    {
      LODWORD(v4) = 0;
      v116.hContext = 0;
    }
    else
    {
      v47 = ADAPTER_RENDER::DdiCreateContext(*v39, *(void **)(v36 + 616), &v116);
      v4 = v47;
      if ( v47 < 0 )
      {
        WdLogSingleEntry1(2, v47);
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
        LODWORD(v35) = (_DWORD)v102;
        v102 = *(unsigned int **)(v102 + 103);
        if ( (unsigned int)dword_140160690 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_140160690, 0x400000000000LL) )
          {
            LOWORD(v103) = 0;
            v49 = *(_QWORD *)v6;
            v50 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 40LL) + 64LL);
            *(_OWORD *)v117 = *(_OWORD *)(v50 + 144);
            v113 = v117;
            v51 = *(_QWORD *)(*(_QWORD *)(v49 + 40) + 64LL);
            if ( v51 )
              v52 = *(_QWORD *)(v51 + 96);
            else
              v52 = 0;
            v114 = v52;
            v101[0] = *((_BYTE *)this + 144);
            v112 = v102;
            v108 = *(_DWORD *)(v35 + 424);
            v109 = *(_DWORD *)(v35 + 420);
            LODWORD(v102) = v4;
            v106 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(
              v50,
              (unsigned int)&unk_140141F0B,
              v35,
              v48,
              (__int64)&v106,
              (__int64)&v102,
              (__int64)&v109,
              (__int64)&v108,
              (__int64)&v112,
              (__int64)v101,
              (__int64)&v114,
              (__int64)&v113,
              (__int64)&v103);
          }
        }
      }
    }
    *((_DWORD *)this + 10) |= 1u;
  }
  else
  {
    v116.hContext = *(HANDLE *)(v36 + 616);
    v116.ContextInfo.DmaBufferSize = *(_DWORD *)(v36 + 624);
    v116.ContextInfo.DmaBufferSegmentSet = *(_DWORD *)(v36 + 628);
    v116.ContextInfo.AllocationListSize = *(_DWORD *)(v36 + 636);
    v116.ContextInfo.PatchLocationListSize = *(_DWORD *)(v36 + 640);
    v116.ContextInfo.DmaBufferPrivateDataSize = *(_DWORD *)(v36 + 632);
    *((_DWORD *)this + 10) &= ~1u;
    LODWORD(v4) = 0;
  }
  if ( (int)v4 < 0 )
    return (unsigned int)v4;
  if ( (*(_DWORD *)(*(_QWORD *)v6 + 464LL) == 2 || *((_DWORD *)this + 36) == 2)
    && v116.ContextInfo.AllocationListSize != 256 )
  {
    WdLogSingleEntry2(3, 256, v116.ContextInfo.AllocationListSize);
    WdLogGlobalForLineNumber = 1148;
    v116.ContextInfo.AllocationListSize = 256;
  }
  *((_QWORD *)this + 23) = v116.hContext;
  *(DXGK_CONTEXTINFO *)((char *)this + 200) = v116.ContextInfo;
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
      WdLogSingleEntry1(2, v54);
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
  if ( (*(_BYTE *)&v116.ContextInfo.Caps.0 & 2) != 0 )
  {
    v55 = *(_QWORD *)v6;
    *(_BYTE *)(v55 + 1919) = 1;
    *(_BYTE *)(*(_QWORD *)(v55 + 40) + 337LL) = 1;
  }
  if ( *((_BYTE *)this + 430) )
  {
    v35 = *(_QWORD *)(352LL * *((unsigned int *)this + 97)
                    + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 16LL) + 16LL) + 3120LL)
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
      if ( (*(_BYTE *)&v116.ContextInfo.Caps.0 & 4) != 0 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 1198;
        return 3221225473LL;
      }
    }
    else if ( (*(_BYTE *)&v116.ContextInfo.Caps.0 & 4) != 0 || v56 && !(_BYTE)v40 )
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
      (unsigned int)&EventCreateContext,
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
      *v111,
      0);
  v57 = *(_QWORD *)v6;
  if ( (*((_DWORD *)this + 98) & 0x10) != 0 )
  {
    memset(v117, 0, sizeof(v117));
    *(_DWORD *)&v117[20] = *(_DWORD *)(*(_QWORD *)(v57 + 40) + 416LL);
    *(_DWORD *)&v117[24] = DXGPROCESS::GetDefaultQos(*(_QWORD *)(*(_QWORD *)v6 + 40LL));
    *(_DWORD *)&v117[4] = *((_DWORD *)this + 95);
    *(_DWORD *)&v117[8] = *((_DWORD *)this + 97);
    *(_DWORD *)v117 = *(_DWORD *)v117 & 0xFFFFEBDD
                    | (2
                     * (*((_DWORD *)this + 98) & 1
                      | (4 * (*((_DWORD *)this + 98) & 4 | (16 * (*((_DWORD *)this + 98) & 0x28 | 0x11))))));
    *(_DWORD *)&v117[32] = *((_DWORD *)this + 36);
    v60 = (struct VIDSCH_HW_CONTEXT *)(*(__int64 (__fastcall **)(DXGCONTEXT *, _BYTE *))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v58 + 16) + 736LL) + 8LL)
                                                                                       + 240LL))(
                                        this,
                                        v117);
    *((_QWORD *)this + 35) = v60;
    if ( !v60 )
    {
      WdLogSingleEntry2(3, this, -1073741801);
      WdLogGlobalForLineNumber = 1266;
      return 3221225495LL;
    }
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x800) != 0 )
    {
      McTemplateK0pppp_EtwWriteTransfer(
        v59,
        (unsigned int)&EventAssociateContext,
        (_DWORD)v60,
        (_DWORD)this,
        (char)v60,
        *((_QWORD *)this + 23),
        *((_QWORD *)this + 24));
      v60 = (struct VIDSCH_HW_CONTEXT *)*((_QWORD *)this + 35);
    }
    memset(&v115, 0, sizeof(v115));
    v115.Flags.Value = (*((_DWORD *)this + 98) >> 2) & 8;
    v61 = VIDSCH_EXPORT::VidSchCreateHwQueue(
            *(VIDSCH_EXPORT **)(*(_QWORD *)(*(_QWORD *)v6 + 16LL) + 736LL),
            0,
            v60,
            &v115,
            (struct VIDSCH_HW_QUEUE **)this + 36,
            0);
    LODWORD(v102) = v61;
    if ( v61 < 0 )
    {
      WdLogSingleEntry2(3, this, v61);
      WdLogGlobalForLineNumber = 1285;
      return (unsigned int)v102;
    }
  }
  else
  {
    memset(v117, 0, sizeof(v117));
    *(_DWORD *)&v117[12] = 0;
    *(_DWORD *)&v117[20] = *(_DWORD *)(*(_QWORD *)(v57 + 40) + 416LL);
    *(_DWORD *)&v117[24] = DXGPROCESS::GetDefaultQos(*(_QWORD *)(*(_QWORD *)v6 + 40LL));
    *(_DWORD *)&v117[4] = *((_DWORD *)this + 95);
    *(_DWORD *)&v117[8] = *((_DWORD *)this + 97);
    v64 = *(_DWORD *)v117 & 0xFFFFEFFD | (2 * (*((_DWORD *)this + 98) & 1 | ((*((_DWORD *)this + 98) & 0x20) << 6)));
    *(_DWORD *)v117 = v64;
    *(_DWORD *)&v117[32] = *((_DWORD *)this + 36);
    if ( *((_BYTE *)this + 430) )
      *(_DWORD *)v117 = v64 | 0x80;
    if ( DXGADAPTER::IsDxgmms2(*(DXGADAPTER **)(*(_QWORD *)(v63 + 16) + 16LL)) )
    {
      if ( v66 >= 0x80 )
      {
        WdLogSingleEntry0(2);
        v23 = 1316;
        v24 = L"Context is setting non-zero Reserved flags at the creation time.";
        goto LABEL_21;
      }
      *(_DWORD *)v117 = v65 & 0xFFFFFBDF | (8 * (v66 & 4 | (16 * (v66 & 8))));
    }
    Context = VIDSCH_EXPORT::VidSchCreateContext(
                *(VIDSCH_EXPORT **)(*(_QWORD *)(v67 + 16) + 736LL),
                this,
                (struct _VIDSCH_CONTEXT_DATA *)v117);
    *((_QWORD *)this + 32) = Context;
    if ( !Context )
    {
      WdLogSingleEntry2(3, this, -1073741801);
      WdLogGlobalForLineNumber = 1330;
      return 3221225495LL;
    }
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x800) != 0 )
      McTemplateK0pppp_EtwWriteTransfer(
        (_DWORD)Context,
        (unsigned int)&EventAssociateContext,
        v69,
        (_DWORD)this,
        (char)Context,
        *((_QWORD *)this + 23),
        *((_QWORD *)this + 24));
  }
  if ( !*((_BYTE *)this + 430) || *(_DWORD *)(*(_QWORD *)v6 + 464LL) == 2 || *((_DWORD *)this + 36) == 2 )
  {
    v70 = DXGCONTEXT::EnsurePriviledgedDmaPool(this, *((_DWORD *)this + 53), *((_DWORD *)this + 54));
    v71 = v70;
    if ( v70 < 0 )
    {
      WdLogSingleEntry2(3, this, v70);
      WdLogGlobalForLineNumber = 1348;
      return v71;
    }
  }
  v72 = (_QWORD *)((char *)this + 48);
  *((_QWORD *)this + 6) = *((unsigned int *)this + 50);
  *((_DWORD *)this + 18) = *((_DWORD *)this + 53);
  v112 = (unsigned int *)((char *)this + 104);
  *((_DWORD *)this + 26) = *((_DWORD *)this + 54);
  if ( *((_BYTE *)this + 430) )
  {
    if ( *((_QWORD *)this + 44) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 1369;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NULL == m_pCommandDmaBuffer", 1369, 0, 0, 0, 0);
    }
    v73 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 16LL) + 16LL) + 444LL);
    if ( (v73 & 0x10) != 0 && v107 && v104 == 16 )
    {
      VirtualMemoryInterface = DxgkGetVirtualMemoryInterface(v73, v62);
      v75 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, char *, int, int))VirtualMemoryInterface)(
              -1,
              (char *)this + 56,
              0,
              (char *)this + 48,
              12288,
              4);
      LODWORD(v4) = v75;
      if ( v75 < 0 )
      {
        WdLogSingleEntry3(3, this, *v72, v75);
        WdLogGlobalForLineNumber = 1390;
        return (unsigned int)v4;
      }
      v76 = *((_QWORD *)v107 + 1);
      v106 = *(_QWORD *)v107;
      ULong64FromUser = RtlReadULong64FromUser(v76);
      if ( !v76 || ULong64FromUser < 8 || !v106 )
      {
        WdLogSingleEntry2(3, this, -1073741811);
        WdLogGlobalForLineNumber = 1415;
        return 3221225485LL;
      }
      RtlWriteULong64ToUser(v106, *((_QWORD *)this + 7));
      RtlWriteULong64ToUser(v76, *v72);
    }
  }
  else
  {
    v78 = DxgkGetVirtualMemoryInterface((__int64)this + 104, v62);
    v79 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, char *, int, int))v78)(
            -1,
            (char *)this + 56,
            0,
            (char *)this + 48,
            12288,
            4);
    LODWORD(v4) = v79;
    if ( v79 < 0 )
    {
      WdLogSingleEntry3(3, this, *v72, v79);
      WdLogGlobalForLineNumber = 1444;
      return (unsigned int)v4;
    }
    Global = DXGGLOBAL::GetGlobal();
    if ( DXGVALIDATION::IsValidationEnabledForAdapterInCallerContext(
           (struct DXGGLOBAL *)((char *)Global + 1668),
           *(struct DXGADAPTER **)(*(_QWORD *)(*(_QWORD *)v6 + 16LL) + 16LL)) )
    {
      v81 = ExAllocatePool2(256, *v72, 1265072196);
      *((_QWORD *)this + 8) = v81;
      if ( !v81 )
      {
        WdLogSingleEntry3(3, this, *v72, -1073741801);
        WdLogGlobalForLineNumber = 1458;
        return 3221225495LL;
      }
    }
  }
  v82 = *((unsigned int *)this + 18);
  if ( (_DWORD)v82 )
  {
    v83 = (unsigned int)v82;
    v84 = 8 * v82;
    if ( v84 > 0xFFFFFFFF )
    {
      WdLogSingleEntry2(3, this, v83);
      WdLogGlobalForLineNumber = 1476;
      return 3221225621LL;
    }
    v85 = (SIZE_T *)((char *)this + 80);
    *((_QWORD *)this + 10) = (unsigned int)v84;
    v86 = DxgkGetVirtualMemoryInterface(v73, v62);
    v87 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, char *, int, int))v86)(
            -1,
            (char *)this + 88,
            0,
            (char *)this + 80,
            12288,
            4);
    LODWORD(v4) = v87;
    if ( v87 < 0 )
    {
      WdLogSingleEntry3(3, this, *v85, v87);
      WdLogGlobalForLineNumber = 1497;
      return (unsigned int)v4;
    }
    *((_QWORD *)this + 12) = MmSecureVirtualMemory(*((PVOID *)this + 11), *v85, 4u);
    if ( !*((_QWORD *)this + 12) )
    {
      WdLogSingleEntry2(3, this, -1073741801);
      WdLogGlobalForLineNumber = 1521;
      return 3221225495LL;
    }
  }
  v88 = *v112;
  if ( !(_DWORD)v88 )
    goto LABEL_169;
  v89 = (unsigned int)v88;
  v90 = 24 * v88;
  if ( v90 > 0xFFFFFFFF )
  {
    WdLogSingleEntry2(3, this, v89);
    WdLogGlobalForLineNumber = 1538;
    return 3221225621LL;
  }
  v91 = (SIZE_T *)((char *)this + 112);
  v106 = (__int64)this + 112;
  *((_QWORD *)this + 14) = (unsigned int)v90;
  v92 = DxgkGetVirtualMemoryInterface(v73, v62);
  v93 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, char *, int, int))v92)(
          -1,
          (char *)this + 120,
          0,
          (char *)this + 112,
          12288,
          4);
  LODWORD(v4) = v93;
  if ( v93 < 0 )
  {
    WdLogSingleEntry3(3, this, *v91, v93);
    WdLogGlobalForLineNumber = 1557;
    return (unsigned int)v4;
  }
  *((_QWORD *)this + 17) = MmSecureVirtualMemory(*((PVOID *)this + 15), *v91, 4u);
  if ( !*((_QWORD *)this + 17) )
  {
    WdLogSingleEntry2(3, this, -1073741801);
    WdLogGlobalForLineNumber = 1581;
    return 3221225495LL;
  }
  v94 = DXGGLOBAL::GetGlobal();
  v6 = v105;
  if ( DXGVALIDATION::IsValidationEnabledForAdapterInCallerContext(
         (struct DXGGLOBAL *)((char *)v94 + 1668),
         *(struct DXGADAPTER **)(*(_QWORD *)(*(_QWORD *)v105 + 16LL) + 16LL)) )
  {
    v95 = ExAllocatePool2(256, *v91, 1265072196);
    *((_QWORD *)this + 16) = v95;
    if ( !v95 )
    {
      WdLogSingleEntry3(3, this, *v91, -1073741801);
      WdLogGlobalForLineNumber = 1595;
      return 3221225495LL;
    }
  }
LABEL_169:
  v96 = *(_QWORD *)(*(_QWORD *)v6 + 40LL);
  v97 = (unsigned int)*v111;
  DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(v96 + 248));
  v98 = ((unsigned int)v97 >> 6) & 0xFFFFFF;
  if ( (unsigned int)v98 < *(_DWORD *)(v96 + 296) )
  {
    v99 = *(_QWORD *)(v96 + 280);
    if ( (((unsigned int)v97 >> 25) & 0x60) == (*(_BYTE *)(v99 + 16 * v98 + 8) & 0x60)
      && (*(_DWORD *)(v99 + 16 * v98 + 8) & 0x1F) != 0 )
    {
      v100 = 16 * ((v97 >> 6) & 0xFFFFFF);
      if ( (*(_DWORD *)(v100 + v99 + 8) & 0x2000) == 0 )
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
      *(_DWORD *)(v100 + *(_QWORD *)(v96 + 280) + 8) &= ~0x2000u;
    }
  }
  *(_QWORD *)(v96 + 256) = 0;
  ExReleasePushLockExclusiveEx(v96 + 248, 0);
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x1403ac874  push    rbx
0x1403ac876  push    rsi
0x1403ac877  push    rdi
0x1403ac878  push    r12
0x1403ac87a  push    r13
0x1403ac87c  push    r14
0x1403ac87e  push    r15
0x1403ac880  sub     rsp, 190h
0x1403ac887  mov     rax, cs:__security_cookie
0x1403ac88e  xor     rax, rsp
0x1403ac891  mov     [rsp+1C8h+var_40], rax
0x1403ac899  mov     edi, r8d
0x1403ac89c  mov     [rsp+1C8h+var_134], r8d
0x1403ac8a4  mov     r14, rdx
0x1403ac8a7  mov     [rsp+1C8h+var_120], rdx
0x1403ac8af  mov     r13, rcx
0x1403ac8b2  mov     [rsp+1C8h+var_110], rcx
0x1403ac8ba  lea     r15, [rcx+10h]
0x1403ac8be  mov     [rsp+1C8h+var_130], r15
0x1403ac8c6  mov     rax, [r15]
0x1403ac8c9  mov     rcx, [rax+10h]
0x1403ac8cd  mov     rbx, [rcx+10h]
0x1403ac8d1  mov     [rsp+1C8h+var_140], rbx
0x1403ac8d9  mov     r9d, [r13+17Ch]; unsigned int
0x1403ac8e0  mov     r8b, 1; unsigned __int8
0x1403ac8e3  mov     rdx, r13; struct DXGCONTEXT *
0x1403ac8e6  mov     rcx, rbx; this
0x1403ac8e9  call    ?NotifyContextCreation@DXGADAPTER@@QEAAXPEAVDXGCONTEXT@@EI@Z; DXGADAPTER::NotifyContextCreation(DXGCONTEXT *,uchar,uint)
0x1403ac8ee  mov     esi, 2500h
0x1403ac8f3  cmp     [rbx+0B30h], esi
0x1403ac8f9  jl      loc_1403AC985
0x1403ac8ff  mov     edx, 10h
0x1403ac904  lea     ecx, [rdx+30h]
0x1403ac907  mov     r8d, 4B677844h
0x1403ac90d  call    cs:__imp_ExAllocatePool2
0x1403ac914  nop     dword ptr [rax+rax+00h]
0x1403ac919  mov     [r13+1D8h], rax
0x1403ac920  xor     r12d, r12d
0x1403ac923  test    rax, rax
0x1403ac926  jnz     short loc_1403AC980
0x1403ac928  mov     rdx, r13
0x1403ac92b  lea     ecx, [rax+6]
0x1403ac92e  call    cs:__imp_WdLogSingleEntry1
0x1403ac935  nop     dword ptr [rax+rax+00h]
0x1403ac93a  mov     cs:WdLogGlobalForLineNumber, 389h
0x1403ac944  mov     [rsp+1C8h+var_188], r12
0x1403ac949  mov     qword ptr [rsp+1C8h+Depth], r12
0x1403ac94e  mov     qword ptr [rsp+1C8h+Tag], r12
0x1403ac953  mov     [rsp+1C8h+Size], r12
0x1403ac958  mov     qword ptr [rsp+1C8h+Flags], r13
0x1403ac95d  lea     r9, aDxgcontext0xPF_0; "DXGCONTEXT (0x%p) failed to allocate m_"...
0x1403ac964  mov     edx, 40001h
0x1403ac969  mov     r8d, 0FFFFFFFFh
0x1403ac96f  xor     ecx, ecx
0x1403ac971  call    DxgkLogInternalTriageEvent
0x1403ac976  mov     eax, 0C0000017h
0x1403ac97b  jmp     loc_1403AE107
0x1403ac980  mov     [rax], r13
0x1403ac983  jmp     short loc_1403AC988
0x1403ac985  xor     r12d, r12d
0x1403ac988  cmp     [r13+1B1h], r12b
0x1403ac98f  jz      short loc_1403AC9F2
0x1403ac991  cmp     [r13+1AEh], r12b
0x1403ac998  jnz     short loc_1403AC9F2
0x1403ac99a  mov     ecx, 2
0x1403ac99f  call    cs:__imp_WdLogSingleEntry0
0x1403ac9a6  nop     dword ptr [rax+rax+00h]
0x1403ac9ab  mov     eax, 392h
0x1403ac9b0  mov     cs:WdLogGlobalForLineNumber, eax
0x1403ac9b6  mov     [rsp+1C8h+var_188], r12
0x1403ac9bb  mov     qword ptr [rsp+1C8h+Depth], r12
0x1403ac9c0  mov     qword ptr [rsp+1C8h+Tag], r12
0x1403ac9c5  mov     [rsp+1C8h+Size], r12
0x1403ac9ca  mov     qword ptr [rsp+1C8h+Flags], rax
0x1403ac9cf  lea     r9, aThePhysicalAda; "The physical adapter requres GpuVaIoMmu"...
0x1403ac9d6  mov     edx, 40000h
0x1403ac9db  xor     ecx, ecx
0x1403ac9dd  mov     r8d, 0FFFFFFFFh
0x1403ac9e3  call    DxgkLogInternalTriageEvent
0x1403ac9e8  mov     eax, 0C000000Dh
0x1403ac9ed  jmp     loc_1403AE107
0x1403ac9f2  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1403ac9f7  mov     rdx, rax; struct DXGPROCESS *
0x1403ac9fa  lea     rcx, [rsp+1C8h+var_68]; this
0x1403aca02  call    ??0DXGHANDLETABLELOCKEXCLUSIVE@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE(DXGPROCESS *)
0x1403aca07  mov     rax, [r15]
0x1403aca0a  mov     rcx, [rax+28h]
0x1403aca0e  add     rcx, 118h
0x1403aca15  mov     [rsp+1C8h+Flags], r12d
0x1403aca1a  xor     r9d, r9d
0x1403aca1d  lea     r8d, [r9+7]
0x1403aca21  mov     rdx, r13
0x1403aca24  call    ?AllocHandle@HMGRTABLE@@QEAAIPEAXW4_HMGRENTRY_TYPE@@IH@Z; HMGRTABLE::AllocHandle(void *,_HMGRENTRY_TYPE,uint,int)
0x1403aca29  mov     r8d, eax
0x1403aca2c  lea     rax, [r13+18h]
0x1403aca30  mov     [rsp+1C8h+var_108], rax
0x1403aca38  mov     [rax], r8d
0x1403aca3b  test    r8d, r8d
0x1403aca3e  jnz     short loc_1403ACA77
0x1403aca40  mov     r8, 0FFFFFFFFC0000017h
0x1403aca47  mov     rdx, r13
0x1403aca4a  mov     ecx, 3
0x1403aca4f  call    cs:__imp_WdLogSingleEntry2
0x1403aca56  nop     dword ptr [rax+rax+00h]
0x1403aca5b  mov     cs:WdLogGlobalForLineNumber, 3A6h
0x1403aca65  lea     rcx, [rsp+1C8h+var_68]; this
0x1403aca6d  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1403aca72  jmp     loc_1403AC976
0x1403aca77  mov     rax, [r15]
0x1403aca7a  mov     r9, [rax+28h]
0x1403aca7e  mov     eax, r8d
0x1403aca81  shr     eax, 6
0x1403aca84  and     eax, 0FFFFFFh
0x1403aca89  mov     ecx, eax
0x1403aca8b  shl     rcx, 4
0x1403aca8f  cmp     eax, [r9+128h]
0x1403aca96  jb      short loc_1403ACA9D
0x1403aca98  mov     al, r12b
0x1403aca9b  jmp     short loc_1403ACACA
0x1403aca9d  mov     rax, [r9+118h]
0x1403acaa4  mov     edx, [rax+rcx+8]
0x1403acaa8  shr     r8d, 19h
0x1403acaac  and     r8d, 60h
0x1403acab0  mov     eax, edx
0x1403acab2  and     eax, 60h
0x1403acab5  cmp     r8b, al
0x1403acab8  jnz     short loc_1403ACA98
0x1403acaba  bt      edx, 0Dh
0x1403acabe  jb      short loc_1403ACA98
0x1403acac0  test    dl, 1Fh
0x1403acac3  mov     al, r12b
0x1403acac6  jz      short loc_1403ACACA
0x1403acac8  mov     al, 1
0x1403acaca  test    al, al
0x1403acacc  jz      short loc_1403ACADB
0x1403acace  mov     rax, [r9+118h]
0x1403acad5  bts     dword ptr [rax+rcx+8], 0Dh
0x1403acadb  lea     rcx, [rsp+1C8h+var_68]; this
0x1403acae3  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1403acae8  cmp     [rbx+0D1h], r12b
0x1403acaef  jz      loc_1403ACD60
0x1403acaf5  mov     byte ptr [r13+1B2h], 1
0x1403acafd  mov     r15d, [r13+90h]
0x1403acb04  mov     ebx, [r13+188h]
0x1403acb0b  mov     esi, [r13+180h]
0x1403acb12  mov     r14d, [r13+17Ch]
0x1403acb19  mov     rcx, [rsp+1C8h+var_130]
0x1403acb21  mov     rcx, [rcx]
0x1403acb24  mov     edi, [rcx+1D8h]
0x1403acb2a  mov     rcx, [rcx+28h]; this
0x1403acb2e  call    ?GetHostProcess@DXGPROCESS@@QEAAIXZ; DXGPROCESS::GetHostProcess(void)
0x1403acb33  mov     rcx, [rsp+1C8h+var_140]
0x1403acb3b  add     rcx, 12B8h; this
0x1403acb42  mov     rdx, [rsp+1C8h+var_120]
0x1403acb4a  mov     [rsp+1C8h+var_188], rdx; void *
0x1403acb4f  mov     r9d, [rsp+1C8h+var_134]
0x1403acb57  mov     dword ptr [rsp+1C8h+Depth], r9d; unsigned int
0x1403acb5c  mov     [rsp+1C8h+Tag], r15d; enum _D3DKMT_CLIENTHINT
0x1403acb61  mov     dword ptr [rsp+1C8h+Size], ebx; struct _D3DDDI_CREATECONTEXTFLAGS
0x1403acb65  mov     [rsp+1C8h+Flags], esi; unsigned int
0x1403acb69  mov     r9d, r14d; unsigned int
0x1403acb6c  mov     r8d, edi; unsigned int
0x1403acb6f  mov     edx, eax; unsigned int
0x1403acb71  call    ?VmBusSendCreateContextVirtual@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAIIIIIU_D3DDDI_CREATECONTEXTFLAGS@@W4_D3DKMT_CLIENTHINT@@IPEAX@Z; DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendCreateContextVirtual(uint,uint,uint,uint,_D3DDDI_CREATECONTEXTFLAGS,_D3DKMT_CLIENTHINT,uint,void *)
0x1403acb76  mov     [r13+1Ch], eax
0x1403acb7a  test    eax, eax
0x1403acb7c  jnz     short loc_1403ACBD4
0x1403acb7e  lea     ecx, [rax+2]
0x1403acb81  call    cs:__imp_WdLogSingleEntry0
0x1403acb88  nop     dword ptr [rax+rax+00h]
0x1403acb8d  mov     eax, 3BEh
0x1403acb92  lea     r9, aFailedToCreate_28; "Failed to create context on the host"
0x1403acb99  mov     r8d, 0FFFFFFFFh
0x1403acb9f  mov     [rsp+1C8h+var_188], r12
0x1403acba4  mov     qword ptr [rsp+1C8h+Depth], r12
0x1403acba9  mov     qword ptr [rsp+1C8h+Tag], r12
0x1403acbae  mov     [rsp+1C8h+Size], r12
0x1403acbb3  mov     cs:WdLogGlobalForLineNumber, eax
0x1403acbb9  mov     qword ptr [rsp+1C8h+Flags], rax
0x1403acbbe  xor     ecx, ecx
0x1403acbc0  mov     edx, 40000h
0x1403acbc5  call    DxgkLogInternalTriageEvent
0x1403acbca  mov     eax, 0C0000001h
0x1403acbcf  jmp     loc_1403AE107
0x1403acbd4  mov     rdi, [rsp+1C8h+var_130]
0x1403acbdc  mov     rax, [rdi]
0x1403acbdf  mov     rsi, [rax+28h]
0x1403acbe3  mov     r15, [rsp+1C8h+var_108]
0x1403acbeb  mov     ebx, [r15]
0x1403acbee  lea     r14, [rsi+0F8h]
0x1403acbf5  mov     rcx, r14; this
0x1403acbf8  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x1403acbfd  mov     eax, ebx
0x1403acbff  shr     eax, 6
0x1403acc02  mov     r9d, 0FFFFFFh
0x1403acc08  and     eax, r9d
0x1403acc0b  cmp     eax, [rsi+128h]
0x1403acc11  jnb     loc_1403ACCAD
0x1403acc17  mov     r8, [rsi+118h]
0x1403acc1e  add     rax, rax
0x1403acc21  mov     edx, [r8+rax*8+8]
0x1403acc26  mov     ecx, ebx
0x1403acc28  shr     ecx, 19h
0x1403acc2b  and     ecx, 60h
0x1403acc2e  mov     eax, edx
0x1403acc30  and     eax, 60h
0x1403acc33  cmp     cl, al
0x1403acc35  jnz     short loc_1403ACCAD
0x1403acc37  test    dl, 1Fh
0x1403acc3a  jz      short loc_1403ACCAD
0x1403acc3c  shr     rbx, 6
0x1403acc40  and     rbx, r9
0x1403acc43  shl     rbx, 4
0x1403acc47  test    dword ptr [r8+rbx+8], 2000h
0x1403acc50  jnz     short loc_1403ACCA0
0x1403acc52  mov     ecx, 1
0x1403acc57  call    cs:__imp_WdLogSingleEntry0
0x1403acc5e  nop     dword ptr [rax+rax+00h]
0x1403acc63  mov     eax, 0E0h
0x1403acc68  mov     cs:WdLogGlobalForLineNumber, eax
0x1403acc6e  mov     [rsp+1C8h+var_188], r12
0x1403acc73  mov     qword ptr [rsp+1C8h+Depth], r12
0x1403acc78  mov     qword ptr [rsp+1C8h+Tag], r12
0x1403acc7d  mov     [rsp+1C8h+Size], r12
0x1403acc82  mov     qword ptr [rsp+1C8h+Flags], rax
0x1403acc87  lea     r9, aMPentrytableGe; "m_pEntryTable[GetIndex(hObject)].Destro"...
0x1403acc8e  mov     edx, 40002h
0x1403acc93  xor     ecx, ecx
0x1403acc95  mov     r8d, 0FFFFFFFFh
0x1403acc9b  call    DxgkLogInternalTriageEvent
0x1403acca0  mov     rax, [rsi+118h]
0x1403acca7  btr     dword ptr [rbx+rax+8], 0Dh
0x1403accad  mov     [r14+8], r12
0x1403accb1  xor     edx, edx
0x1403accb3  mov     rcx, r14
0x1403accb6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1403accbd  nop     dword ptr [rax+rax+00h]
0x1403accc2  call    cs:__imp_KeLeaveCriticalRegion
0x1403accc9  nop     dword ptr [rax+rax+00h]
0x1403accce  cmp     cs:bTracingEnabled, 0
0x1403accd5  jz      loc_1403AE105
0x1403accdb  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 8
0x1403acce2  jz      loc_1403AE105
0x1403acce8  mov     eax, [r15]
0x1403acceb  mov     [rsp+1C8h+var_158], r12
0x1403accf0  mov     [rsp+1C8h+var_160], rax
0x1403accf5  mov     [rsp+1C8h+var_168], r13
0x1403accfa  mov     dword ptr [rsp+1C8h+var_170], r12d
0x1403accff  mov     eax, [r13+0D8h]
0x1403acd06  mov     dword ptr [rsp+1C8h+var_178], eax
0x1403acd0a  mov     eax, [r13+0D4h]
0x1403acd11  mov     dword ptr [rsp+1C8h+var_180], eax
0x1403acd15  mov     eax, [r13+0D0h]
0x1403acd1c  mov     dword ptr [rsp+1C8h+var_188], eax
0x1403acd20  mov     eax, [r13+0CCh]
0x1403acd27  mov     dword ptr [rsp+1C8h+Depth], eax
0x1403acd2b  mov     eax, [r13+0C8h]
0x1403acd32  mov     [rsp+1C8h+Tag], eax
0x1403acd36  mov     eax, [r13+180h]
0x1403acd3d  mov     dword ptr [rsp+1C8h+Size], eax
0x1403acd41  mov     eax, [r13+17Ch]
0x1403acd48  mov     [rsp+1C8h+Flags], eax
0x1403acd4c  mov     r9, [rdi]
0x1403acd4f  lea     rdx, EventCreateContext
0x1403acd56  call    McTemplateK0pqqqqqqqqppp_EtwWriteTransfer
0x1403acd5b  jmp     loc_1403AE105
0x1403acd60  xor     edx, edx; Val
0x1403acd62  lea     r8d, [rdx+48h]; Size
0x1403acd66  lea     rcx, [rsp+1C8h+var_B8]; void *
0x1403acd6e  call    memset
0x1403acd73  cmp     [rbx+0B30h], esi
0x1403acd79  jl      short loc_1403ACD84
0x1403acd7b  mov     rax, [r13+1D8h]
0x1403acd82  jmp     short loc_1403ACD87
0x1403acd84  mov     rax, r13
0x1403acd87  mov     [r13+0C0h], rax
0x1403acd8e  mov     [rsp+1C8h+var_B8.hContext], rax
0x1403acd96  mov     r8d, [r13+17Ch]; unsigned int
0x1403acd9d  mov     [rsp+1C8h+var_B8.NodeOrdinal], r8d
0x1403acda5  mov     eax, [r13+180h]
0x1403acdac  mov     [rsp+1C8h+var_B8.EngineAffinity], eax
0x1403acdb3  mov     [rsp+1C8h+var_B8.pPrivateDriverData], r14
0x1403acdbb  mov     [rsp+1C8h+var_B8.PrivateDriverDataSize], edi
0x1403acdc2  mov     r11, [r15]
0x1403acdc5  mov     esi, 2
0x1403acdca  test    byte ptr [r11+77Dh], 8
0x1403acdd2  jnz     short loc_1403ACDE0
0x1403acdd4  cmp     [r13+90h], esi
0x1403acddb  mov     eax, r12d
0x1403acdde  jnz     short loc_1403ACDE2
0x1403acde0  mov     eax, esi
0x1403acde2  movzx   ecx, byte ptr [r13+1AEh]
0x1403acdea  mov     [rsp+1C8h+var_138], ecx
0x1403acdf1  mov     r10d, ecx
0x1403acdf4  shl     r10d, 2
0x1403acdf8  xor     r10d, eax
0x1403acdfb  and     r10d, 4
0x1403acdff  xor     r10d, eax
0x1403ace02  mov     dword ptr [rsp+1C8h+var_B8.Flags], r10d
0x1403ace0a  mov     ebx, [r13+188h]
  ... truncated ...
```
