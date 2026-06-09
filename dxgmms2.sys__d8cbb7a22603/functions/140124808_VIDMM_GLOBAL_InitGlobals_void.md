# VIDMM_GLOBAL::InitGlobals(void)

- ea: `0x140124808`
- end: `0x140124ea3`
- name: `?InitGlobals@VIDMM_GLOBAL@@SAJXZ`
- size: `1691`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1401247f0`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002dbd0`
- `0x14002ed58`
- `0x14002f480`
- `0x14004502c`
- `0x140047ac8`
- `0x140047b20`
- `0x140047b78`
- `0x140059030`
- `0x1400af02c`
- `0x1400c08d4`
- `0x1400c1c34`
- `0x1400c9d34`
- `0x14011e034`
- `0x14011eaf8`
- `0x140124808`

## import_xrefs

- `ntoskrnl!PcwRegister` at `0x140124b0f`
- `ntoskrnl!PcwRegister` at `0x140124bb0`
- `ntoskrnl!PcwRegister` at `0x140124c31`
- `ntoskrnl!PcwRegister` at `0x140124cb2`
- `ntoskrnl!PcwRegister` at `0x140124b0f`
- `ntoskrnl!PcwRegister` at `0x140124bb0`
- `ntoskrnl!PcwRegister` at `0x140124c31`
- `ntoskrnl!PcwRegister` at `0x140124cb2`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140124d39`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140124d39`
- `watchdog!WdLogSingleEntry0` at `0x1401248f6`
- `watchdog!WdLogSingleEntry0` at `0x140124a99`
- `watchdog!WdLogSingleEntry0` at `0x140124e53`
- `watchdog!WdLogSingleEntry0` at `0x1401248f6`
- `watchdog!WdLogSingleEntry0` at `0x140124a99`
- `watchdog!WdLogSingleEntry0` at `0x140124e53`
- `watchdog!WdLogSingleEntry1` at `0x140124927`
- `watchdog!WdLogSingleEntry1` at `0x14012497d`
- `watchdog!WdLogSingleEntry1` at `0x1401249ec`
- `watchdog!WdLogSingleEntry1` at `0x140124b2f`
- `watchdog!WdLogSingleEntry1` at `0x140124bcb`
- `watchdog!WdLogSingleEntry1` at `0x140124c4c`
- `watchdog!WdLogSingleEntry1` at `0x140124ccd`
- `watchdog!WdLogSingleEntry1` at `0x140124d6a`
- `watchdog!WdLogSingleEntry1` at `0x140124db9`
- `watchdog!WdLogSingleEntry1` at `0x140124e04`
- `watchdog!WdLogSingleEntry1` at `0x140124927`
- `watchdog!WdLogSingleEntry1` at `0x14012497d`
- `watchdog!WdLogSingleEntry1` at `0x1401249ec`
- `watchdog!WdLogSingleEntry1` at `0x140124b2f`
- `watchdog!WdLogSingleEntry1` at `0x140124bcb`
- `watchdog!WdLogSingleEntry1` at `0x140124c4c`
- `watchdog!WdLogSingleEntry1` at `0x140124ccd`
- `watchdog!WdLogSingleEntry1` at `0x140124d6a`
- `watchdog!WdLogSingleEntry1` at `0x140124db9`
- `watchdog!WdLogSingleEntry1` at `0x140124e04`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x140124d9a`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x140124d9a`
- `HAL!KeQueryPerformanceCounter` at `0x140124841`
- `HAL!KeQueryPerformanceCounter` at `0x140124841`

## string_xrefs

- `0x140124b3b`: `Failed to create RegisterGpuPerformanceCounterSetProcessMemory, returning 0x%I64x`
- `0x140124bd7`: `Failed to create RegisterGpuPerformanceCounterSetAdapterMemory, returning 0x%I64x`
- `0x140124c58`: `Failed to create RegisterGpuPerformanceCounterSetLocalAdapterMemory, returning 0x%I64x`
- `0x140124cd9`: `Failed to create RegisterGpuPerformanceCounterSetNonLocalAdapterMemory, returning 0x%I64x`
- `0x140124dca`: `Failed to DxgCreateLiveDumpWithWdLogs, error: 0x%I64x`

## pseudocode

```c
__int64 VIDMM_GLOBAL::InitGlobals(void)
{
  DXGGLOBAL *Global; // rax
  __int64 v1; // rax
  unsigned __int64 MaximumGlobalAdapterCount; // kr00_8
  int v3; // ecx
  int v4; // r8d
  __int64 v5; // rax
  const wchar_t *v6; // r9
  int inited; // eax
  __int64 v8; // rdi
  int v9; // ecx
  int v10; // r8d
  const wchar_t *v11; // r9
  int v13; // eax
  struct VIDMM_EXISTINGSYSMEM_HEAP *v14; // rax
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rax
  NTSTATUS v18; // eax
  int v19; // ecx
  int v20; // r8d
  const wchar_t *v21; // r9
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  int v25; // eax
  int LiveDumpWithWdLogs; // eax
  __int64 v27; // rbx
  int v28; // ecx
  int v29; // r8d
  int v30; // ecx
  int v31; // r8d
  int Size; // [rsp+28h] [rbp-31h]
  _PCW_REGISTRATION_INFORMATION Info; // [rsp+50h] [rbp-9h] BYREF
  __int64 v34; // [rsp+80h] [rbp+27h]

  g_Feature_ResourcePoolManagement = (unsigned int)Feature_ResourcePoolManagement__private_IsEnabledDeviceUsageNoInline() != 0;
  g_Feature_IntelligentCarveout = (unsigned int)Feature_IntelligentCarveout__private_IsEnabledDeviceUsageNoInline() != 0;
  KeQueryPerformanceCounter(&VIDMM_GLOBAL::_QpcFrequency);
  g_VidMmProcessListHeadLock = 0;
  qword_140087660 = (__int64)&g_VidMmProcessListHead;
  g_VidMmProcessListHead.Flink = &g_VidMmProcessListHead;
  bTracingEnabled = 0;
  McGenEventRegister_EtwRegister();
  TlgRegisterAggregateProviderEx();
  VIDMM_GLOBAL::ReadConfiguration();
  VIDMM_GLOBAL::_RotationHistory = (void *)operator new[](98304, 1833789782, 64);
  if ( VIDMM_GLOBAL::_RotationHistory )
    *(&VIDMM_GLOBAL::_RotationHistory + 1) = (void *)2048;
  Global = DXGGLOBAL::GetGlobal();
  MaximumGlobalAdapterCount = DXGGLOBAL::GetMaximumGlobalAdapterCount(Global);
  v1 = 4 * MaximumGlobalAdapterCount;
  if ( !is_mul_ok(MaximumGlobalAdapterCount, 4u) )
    v1 = -1;
  VIDMM_PROCESS::_pDxProcessPerAdapterCount = (void *)operator new[](v1, 858876246, 256);
  if ( !VIDMM_PROCESS::_pDxProcessPerAdapterCount )
  {
    _InterlockedIncrement(&dword_1400876DC);
    WdLogSingleEntry0(6);
    v5 = 1242;
    v6 = L"Failed to allocate memory for VIDMM_PROCESS::_pDxProcessPerAdapterCount.\n";
LABEL_37:
    WdLogGlobalForLineNumber = v5;
    DxgkLogInternalTriageEvent(v3, 262145, v4, (_DWORD)v6, v5, 0, 0, 0);
    return 3221225495LL;
  }
  inited = VidMmInitDmaPoolGlobals();
  v8 = inited;
  if ( inited < 0 )
  {
    WdLogSingleEntry1(1, inited);
    v11 = L"Failed to VIDMM_DMA_POOL::InitGlobals in InitGlobals, returning 0x%I64x";
    WdLogGlobalForLineNumber = 1254;
LABEL_9:
    DxgkLogInternalTriageEvent(v9, 0x40000, v10, (_DWORD)v11, v8, 0, 0, 0);
    return (unsigned int)v8;
  }
  v13 = VIDMM_PROCESS_FENCE_STORAGE::InitGlobalStorage();
  v8 = v13;
  if ( v13 < 0 )
  {
    WdLogSingleEntry1(1, v13);
    v11 = L"Failed to VIDMM_PROCESS_FENCE_STORAGE::InitGlobalStorage in InitGlobals, returning 0x%I64x";
    WdLogGlobalForLineNumber = 1262;
    goto LABEL_9;
  }
  v14 = (struct VIDMM_EXISTINGSYSMEM_HEAP *)operator new(16, 1697737046, 256);
  if ( !v14 )
  {
    g_pExistingSysMemHeap = 0;
    _InterlockedIncrement(&dword_14008787C);
    WdLogSingleEntry0(6);
    v5 = 1274;
    v6 = L"Failed to allocate memory for VIDMM_EXISTINGSYSMEM_HEAP.\n";
    goto LABEL_37;
  }
  *((_BYTE *)v14 + 8) = 0;
  *(_QWORD *)v14 = &VIDMM_EXISTINGSYSMEM_HEAP::`vftable';
  g_pExistingSysMemHeap = v14;
  v15 = ((__int64 (__fastcall *)(struct VIDMM_EXISTINGSYSMEM_HEAP *, _QWORD, _QWORD))VIDMM_PARAVIRTUALIZATION_HEAP::GetBackingAddress)(
          v14,
          0,
          0);
  v8 = v15;
  if ( v15 < 0 )
  {
    WdLogSingleEntry1(1, v15);
    v11 = L"Failed to Initialize existing sysmem heap, returning 0x%I64x";
    WdLogGlobalForLineNumber = 1281;
    goto LABEL_9;
  }
  qword_140087AA8 = (__int64)&VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead;
  VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead.Flink = &VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead;
  v16 = operator new(32, 808544598, 256);
  if ( v16 )
  {
    *(_QWORD *)v16 = 0;
    *(_QWORD *)(v16 + 8) = 0;
    *(_DWORD *)(v16 + 16) = 0;
    *(_DWORD *)(v16 + 20) = 78;
    *(_DWORD *)(v16 + 24) = -1;
    VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListLock = (struct DXGPUSHLOCK *)v16;
    g_ppSystemHeapPerNumaNodeArraySize = VidMmCalculateHeapPerNumaNodeArraySize();
    v17 = 8LL * g_ppSystemHeapPerNumaNodeArraySize;
    if ( !is_mul_ok(g_ppSystemHeapPerNumaNodeArraySize, 8u) )
      v17 = -1;
    g_ppSystemHeapPerNumaNode = (void *)operator new[](v17, 1664182614, 256);
    if ( !g_ppSystemHeapPerNumaNode )
    {
      _InterlockedIncrement(&dword_14008786C);
      WdLogSingleEntry0(6);
      v5 = 1300;
      v6 = L"Failed to allocate memory for global array VIDMM_SYSTEM_HEAP per NUMA node.\n";
      goto LABEL_37;
    }
    VIDMM_PARTITION::_PartitionTree = 0;
    qword_140087290 = (__int64)&VIDMM_GLOBAL::_AdapterListHead;
    VIDMM_GLOBAL::_AdapterListHead = &VIDMM_GLOBAL::_AdapterListHead;
    *(_QWORD *)&Info.Version = 512;
    Info.Name = (PCUNICODE_STRING)L"$&";
    Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`InitRegistrationInformationGpuPerformanceCounterSetProcessMemory'::`2'::Descriptors;
    *(_QWORD *)&Info.CounterCount = 5;
    v34 = 0;
    Info.Callback = 0;
    Info.CallbackContext = 0;
    v18 = PcwRegister(&GpuPerformanceCounterSetProcessMemory, &Info);
    v8 = v18;
    if ( v18 >= 0 )
    {
      byte_1400879AB = 1;
      Info.Name = (PCUNICODE_STRING)L"$&";
      *(_QWORD *)&Info.Version = 512;
      Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`InitRegistrationInformationGpuPerformanceCounterSetAdapterMemory'::`2'::Descriptors;
      *(_QWORD *)&Info.CounterCount = 3;
      v34 = 0;
      Info.Callback = 0;
      Info.CallbackContext = 0;
      v22 = PcwRegister(&GpuPerformanceCounterSetAdapterMemory, &Info);
      v8 = v22;
      if ( v22 >= 0 )
      {
        byte_1400879AA = 1;
        Info.Name = (PCUNICODE_STRING)L"02";
        *(_QWORD *)&Info.Version = 512;
        Info.Counters = (PPCW_COUNTER_DESCRIPTOR)&`InitRegistrationInformationGpuPerformanceCounterSetLocalAdapterMemory'::`2'::Descriptors;
        *(_QWORD *)&Info.CounterCount = 1;
        v34 = 0;
        Info.Callback = 0;
        Info.CallbackContext = 0;
        v23 = PcwRegister(&GpuPerformanceCounterSetLocalAdapterMemory, &Info);
        v8 = v23;
        if ( v23 >= 0 )
        {
          byte_1400879A9 = 1;
          Info.Name = (PCUNICODE_STRING)L"8:";
          *(_QWORD *)&Info.Version = 512;
          Info.Counters = (PPCW_COUNTER_DESCRIPTOR)&`InitRegistrationInformationGpuPerformanceCounterSetNonLocalAdapterMemory'::`2'::Descriptors;
          *(_QWORD *)&Info.CounterCount = 1;
          v34 = 0;
          Info.Callback = 0;
          Info.CallbackContext = 0;
          v24 = PcwRegister(&GpuPerformanceCounterSetNonLocalAdapterMemory, &Info);
          v8 = v24;
          if ( v24 >= 0 )
          {
            byte_1400879A8 = 1;
            g_Feature_FenceStorageUsingVidMmAlloc = (unsigned int)Feature_FenceStorageUsingVidMmAlloc__private_IsEnabledDeviceUsageNoInline() != 0;
            g_Feature_Largify64KBPrototype = 0;
            ExInitializeLookasideListEx(&g_VaRangeLookasideList, 0, 0, PagedPool, 0, 0x90u, 0x35356956u, 0);
            if ( !g_Feature_ResourcePoolManagement )
              return (unsigned int)v8;
            v25 = VidMmInitializeSystemResourcePool();
            LODWORD(v8) = v25;
            if ( v25 >= 0 )
              return (unsigned int)v8;
            WdLogSingleEntry1(3, v25);
            WdLogGlobalForLineNumber = 1373;
            goto LABEL_33;
          }
          WdLogSingleEntry1(1, v24);
          v21 = L"Failed to create RegisterGpuPerformanceCounterSetNonLocalAdapterMemory, returning 0x%I64x";
          WdLogGlobalForLineNumber = 1350;
        }
        else
        {
          WdLogSingleEntry1(1, v23);
          v21 = L"Failed to create RegisterGpuPerformanceCounterSetLocalAdapterMemory, returning 0x%I64x";
          WdLogGlobalForLineNumber = 1339;
        }
      }
      else
      {
        WdLogSingleEntry1(1, v22);
        v21 = L"Failed to create RegisterGpuPerformanceCounterSetAdapterMemory, returning 0x%I64x";
        WdLogGlobalForLineNumber = 1328;
      }
    }
    else
    {
      WdLogSingleEntry1(1, v18);
      v21 = L"Failed to create RegisterGpuPerformanceCounterSetProcessMemory, returning 0x%I64x";
      WdLogGlobalForLineNumber = 1317;
    }
    DxgkLogInternalTriageEvent(v19, 0x40000, v20, (_DWORD)v21, v8, 0, 0, 0);
LABEL_33:
    LOBYTE(Size) = 0;
    LiveDumpWithWdLogs = DxgCreateLiveDumpWithWdLogs(403, 2065, (int)v8, 0, 0, Size);
    if ( LiveDumpWithWdLogs < 0 )
    {
      v27 = LiveDumpWithWdLogs;
      WdLogSingleEntry1(1, LiveDumpWithWdLogs);
      WdLogGlobalForLineNumber = 1390;
      DxgkLogInternalTriageEvent(
        v28,
        0x40000,
        v29,
        (unsigned int)L"Failed to DxgCreateLiveDumpWithWdLogs, error: 0x%I64x",
        v27,
        0,
        0,
        0);
    }
    return (unsigned int)v8;
  }
  VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListLock = 0;
  WdLogSingleEntry1(1, -1073741801);
  WdLogGlobalForLineNumber = 1289;
  DxgkLogInternalTriageEvent(
    v30,
    0x40000,
    v31,
    (unsigned int)L"Failed to VidMmInitializeGlobalHeapManagerTracking in InitGlobals, returning 0x%I64x",
    -1073741801,
    0,
    0,
    0);
  return 3221225495LL;
}

```

## disassembly

```asm
0x140124808  push    rbp
0x14012480a  push    rbx
0x14012480b  push    rsi
0x14012480c  push    rdi
0x14012480d  push    r14
0x14012480f  lea     rbp, [rsp-37h]
0x140124814  sub     rsp, 90h
0x14012481b  call    Feature_ResourcePoolManagement__private_IsEnabledDeviceUsageNoInline
0x140124820  xor     r14d, r14d
0x140124823  test    eax, eax
0x140124825  setnz   cs:?g_Feature_ResourcePoolManagement@@3_NA; bool g_Feature_ResourcePoolManagement
0x14012482c  call    Feature_IntelligentCarveout__private_IsEnabledDeviceUsageNoInline
0x140124831  test    eax, eax
0x140124833  lea     rcx, ?_QpcFrequency@VIDMM_GLOBAL@@2T_LARGE_INTEGER@@A; PerformanceFrequency
0x14012483a  setnz   cs:?g_Feature_IntelligentCarveout@@3_NA; bool g_Feature_IntelligentCarveout
0x140124841  call    cs:__imp_KeQueryPerformanceCounter
0x140124848  nop     dword ptr [rax+rax+00h]
0x14012484d  lea     rax, ?g_VidMmProcessListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_VidMmProcessListHead
0x140124854  mov     cs:?g_VidMmProcessListHeadLock@@3U_EX_PUSH_LOCK@@A, r14; _EX_PUSH_LOCK g_VidMmProcessListHeadLock
0x14012485b  mov     cs:qword_140087660, rax
0x140124862  mov     cs:?g_VidMmProcessListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_VidMmProcessListHead
0x140124869  mov     cs:bTracingEnabled, r14b
0x140124870  call    McGenEventRegister_EtwRegister
0x140124875  call    TlgRegisterAggregateProviderEx
0x14012487a  call    ?ReadConfiguration@VIDMM_GLOBAL@@SAXXZ; VIDMM_GLOBAL::ReadConfiguration(void)
0x14012487f  mov     edx, 6D4D6956h
0x140124884  lea     r8d, [r14+40h]
0x140124888  mov     ecx, 18000h
0x14012488d  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140124892  mov     qword ptr cs:?_RotationHistory@VIDMM_GLOBAL@@2U_VIDMM_ROTATION_HISTORY@@A, rax; _VIDMM_ROTATION_HISTORY VIDMM_GLOBAL::_RotationHistory
0x140124899  test    rax, rax
0x14012489c  jz      short loc_1401248A9
0x14012489e  mov     qword ptr cs:?_RotationHistory@VIDMM_GLOBAL@@2U_VIDMM_ROTATION_HISTORY@@A+8, 800h; _VIDMM_ROTATION_HISTORY VIDMM_GLOBAL::_RotationHistory
0x1401248a9  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401248ae  mov     rcx, rax; this
0x1401248b1  call    ?GetMaximumGlobalAdapterCount@DXGGLOBAL@@QEBAKXZ; DXGGLOBAL::GetMaximumGlobalAdapterCount(void)
0x1401248b6  mov     ecx, eax
0x1401248b8  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1401248bf  mov     eax, 4
0x1401248c4  mov     ebx, 100h
0x1401248c9  mul     rcx
0x1401248cc  mov     r8d, ebx
0x1401248cf  mov     edx, 33316956h
0x1401248d4  cmovb   rax, rsi
0x1401248d8  mov     rcx, rax
0x1401248db  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401248e0  mov     cs:?_pDxProcessPerAdapterCount@VIDMM_PROCESS@@2PEAJEA, rax; long * VIDMM_PROCESS::_pDxProcessPerAdapterCount
0x1401248e7  test    rax, rax
0x1401248ea  jnz     short loc_140124913
0x1401248ec  lock inc cs:dword_1400876DC
0x1401248f3  lea     ecx, [rsi+7]
0x1401248f6  call    cs:__imp_WdLogSingleEntry0
0x1401248fd  nop     dword ptr [rax+rax+00h]
0x140124902  mov     eax, 4DAh
0x140124907  lea     r9, aFailedToAlloca_43; "Failed to allocate memory for VIDMM_PRO"...
0x14012490e  jmp     loc_140124E6B
0x140124913  call    ?VidMmInitDmaPoolGlobals@@YAJXZ; VidMmInitDmaPoolGlobals(void)
0x140124918  movsxd  rdi, eax
0x14012491b  test    eax, eax
0x14012491d  jns     short loc_140124969
0x14012491f  mov     rdx, rdi
0x140124922  mov     ecx, 1
0x140124927  call    cs:__imp_WdLogSingleEntry1
0x14012492e  nop     dword ptr [rax+rax+00h]
0x140124933  lea     r9, aFailedToVidmmD; "Failed to VIDMM_DMA_POOL::InitGlobals i"...
0x14012493a  mov     cs:WdLogGlobalForLineNumber, 4E6h
0x140124944  mov     qword ptr [rsp+0B0h+Depth], r14
0x140124949  mov     edx, 40000h
0x14012494e  mov     qword ptr [rsp+0B0h+Tag], r14
0x140124953  mov     [rsp+0B0h+Size], r14
0x140124958  mov     qword ptr [rsp+0B0h+Flags], rdi
0x14012495d  call    DxgkLogInternalTriageEvent
0x140124962  mov     eax, edi
0x140124964  jmp     loc_140124E94
0x140124969  call    ?InitGlobalStorage@VIDMM_PROCESS_FENCE_STORAGE@@SAJXZ; VIDMM_PROCESS_FENCE_STORAGE::InitGlobalStorage(void)
0x14012496e  movsxd  rdi, eax
0x140124971  test    eax, eax
0x140124973  jns     short loc_14012499C
0x140124975  mov     rdx, rdi
0x140124978  mov     ecx, 1
0x14012497d  call    cs:__imp_WdLogSingleEntry1
0x140124984  nop     dword ptr [rax+rax+00h]
0x140124989  lea     r9, aFailedToVidmmP; "Failed to VIDMM_PROCESS_FENCE_STORAGE::"...
0x140124990  mov     cs:WdLogGlobalForLineNumber, 4EEh
0x14012499a  jmp     short loc_140124944
0x14012499c  mov     r8, rbx
0x14012499f  mov     edx, 65316956h
0x1401249a4  mov     ecx, 10h
0x1401249a9  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401249ae  mov     rcx, rax
0x1401249b1  test    rax, rax
0x1401249b4  jz      loc_140124E40
0x1401249ba  lea     rax, ??_7VIDMM_EXISTINGSYSMEM_HEAP@@6B@; const VIDMM_EXISTINGSYSMEM_HEAP::`vftable'
0x1401249c1  mov     [rcx+8], r14b
0x1401249c5  mov     [rcx], rax
0x1401249c8  xor     r8d, r8d
0x1401249cb  mov     rax, [rax+8]
0x1401249cf  xor     edx, edx
0x1401249d1  mov     cs:?g_pExistingSysMemHeap@@3PEAVVIDMM_EXISTINGSYSMEM_HEAP@@EA, rcx; VIDMM_EXISTINGSYSMEM_HEAP * g_pExistingSysMemHeap
0x1401249d8  call    _guard_dispatch_icall
0x1401249dd  movsxd  rdi, eax
0x1401249e0  test    eax, eax
0x1401249e2  jns     short loc_140124A0E
0x1401249e4  mov     rdx, rdi
0x1401249e7  mov     ecx, 1
0x1401249ec  call    cs:__imp_WdLogSingleEntry1
0x1401249f3  nop     dword ptr [rax+rax+00h]
0x1401249f8  lea     r9, aFailedToInitia_10; "Failed to Initialize existing sysmem he"...
0x1401249ff  mov     cs:WdLogGlobalForLineNumber, 501h
0x140124a09  jmp     loc_140124944
0x140124a0e  lea     rax, ?_GlobalHeapManagerListHead@VIDMM_RECYCLE_HEAP_MGR@@0U_LIST_ENTRY@@A; _LIST_ENTRY VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead
0x140124a15  mov     r8, rbx
0x140124a18  mov     edx, 30316956h
0x140124a1d  mov     cs:qword_140087AA8, rax
0x140124a24  mov     ecx, 20h ; ' '
0x140124a29  mov     cs:?_GlobalHeapManagerListHead@VIDMM_RECYCLE_HEAP_MGR@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead
0x140124a30  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140124a35  test    rax, rax
0x140124a38  jz      loc_140124DF1
0x140124a3e  mov     [rax], r14
0x140124a41  mov     [rax+8], r14
0x140124a45  mov     [rax+10h], r14d
0x140124a49  mov     dword ptr [rax+14h], 4Eh ; 'N'
0x140124a50  mov     [rax+18h], esi
0x140124a53  mov     cs:?_GlobalHeapManagerListLock@VIDMM_RECYCLE_HEAP_MGR@@0PEAVDXGPUSHLOCK@@EA, rax; DXGPUSHLOCK * VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListLock
0x140124a5a  call    ?VidMmCalculateHeapPerNumaNodeArraySize@@YAKXZ; VidMmCalculateHeapPerNumaNodeArraySize(void)
0x140124a5f  mov     ecx, eax
0x140124a61  mov     r8, rbx
0x140124a64  mov     cs:?g_ppSystemHeapPerNumaNodeArraySize@@3KA, ecx; ulong g_ppSystemHeapPerNumaNodeArraySize
0x140124a6a  mov     eax, 8
0x140124a6f  mul     rcx
0x140124a72  mov     edx, 63316956h
0x140124a77  cmovb   rax, rsi
0x140124a7b  mov     rcx, rax
0x140124a7e  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140124a83  mov     cs:?g_ppSystemHeapPerNumaNode@@3PEAPEAVVIDMM_SYSTEM_HEAP@@EA, rax; VIDMM_SYSTEM_HEAP * * g_ppSystemHeapPerNumaNode
0x140124a8a  test    rax, rax
0x140124a8d  jnz     short loc_140124AB6
0x140124a8f  lock inc cs:dword_14008786C
0x140124a96  lea     ecx, [rax+6]
0x140124a99  call    cs:__imp_WdLogSingleEntry0
0x140124aa0  nop     dword ptr [rax+rax+00h]
0x140124aa5  mov     eax, 514h
0x140124aaa  lea     r9, aFailedToAlloca_19; "Failed to allocate memory for global ar"...
0x140124ab1  jmp     loc_140124E6B
0x140124ab6  lea     rax, ?_AdapterListHead@VIDMM_GLOBAL@@2U_LIST_ENTRY@@A; _LIST_ENTRY VIDMM_GLOBAL::_AdapterListHead
0x140124abd  mov     cs:?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A, r14; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x140124ac4  mov     cs:qword_140087290, rax
0x140124acb  lea     rdx, [rbp+57h+Info]; Info
0x140124acf  mov     cs:?_AdapterListHead@VIDMM_GLOBAL@@2U_LIST_ENTRY@@A, rax; _LIST_ENTRY VIDMM_GLOBAL::_AdapterListHead
0x140124ad6  lea     rcx, GpuPerformanceCounterSetProcessMemory; Registration
0x140124add  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetProcessMemory@@9@4U_UNICODE_STRING@@B; "$&"
0x140124ae4  mov     qword ptr [rbp+57h+Info.Version], 200h
0x140124aec  mov     [rbp+57h+Info.Name], rax
0x140124af0  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetProcessMemory@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetProcessMemory'::`2'::Descriptors
0x140124af7  mov     [rbp+57h+Info.Counters], rax
0x140124afb  mov     qword ptr [rbp+57h+Info.CounterCount], 5
0x140124b03  mov     [rbp+57h+var_30], r14
0x140124b07  mov     [rbp+57h+Info.Callback], r14
0x140124b0b  mov     [rbp+57h+Info.CallbackContext], r14
0x140124b0f  call    cs:__imp_PcwRegister
0x140124b16  nop     dword ptr [rax+rax+00h]
0x140124b1b  movsxd  rdi, eax
0x140124b1e  mov     esi, 40000h
0x140124b23  test    eax, eax
0x140124b25  jns     short loc_140124B6C
0x140124b27  mov     rdx, rdi
0x140124b2a  mov     ecx, 1
0x140124b2f  call    cs:__imp_WdLogSingleEntry1
0x140124b36  nop     dword ptr [rax+rax+00h]
0x140124b3b  lea     r9, aFailedToCreate; "Failed to create RegisterGpuPerformance"...
0x140124b42  mov     cs:WdLogGlobalForLineNumber, 525h
0x140124b4c  mov     qword ptr [rsp+0B0h+Depth], r14
0x140124b51  mov     edx, esi
0x140124b53  mov     qword ptr [rsp+0B0h+Tag], r14
0x140124b58  mov     [rsp+0B0h+Size], r14
0x140124b5d  mov     qword ptr [rsp+0B0h+Flags], rdi
0x140124b62  call    DxgkLogInternalTriageEvent
0x140124b67  jmp     loc_140124D80
0x140124b6c  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetAdapterMemory@@9@4U_UNICODE_STRING@@B; "$&"
0x140124b73  mov     cs:byte_1400879AB, 1
0x140124b7a  mov     [rbp+57h+Info.Name], rax
0x140124b7e  lea     rdx, [rbp+57h+Info]; Info
0x140124b82  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetAdapterMemory@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetAdapterMemory'::`2'::Descriptors
0x140124b89  mov     qword ptr [rbp+57h+Info.Version], 200h
0x140124b91  lea     rcx, GpuPerformanceCounterSetAdapterMemory; Registration
0x140124b98  mov     [rbp+57h+Info.Counters], rax
0x140124b9c  mov     qword ptr [rbp+57h+Info.CounterCount], 3
0x140124ba4  mov     [rbp+57h+var_30], r14
0x140124ba8  mov     [rbp+57h+Info.Callback], r14
0x140124bac  mov     [rbp+57h+Info.CallbackContext], r14
0x140124bb0  call    cs:__imp_PcwRegister
0x140124bb7  nop     dword ptr [rax+rax+00h]
0x140124bbc  movsxd  rdi, eax
0x140124bbf  test    eax, eax
0x140124bc1  jns     short loc_140124BED
0x140124bc3  mov     rdx, rdi
0x140124bc6  mov     ecx, 1
0x140124bcb  call    cs:__imp_WdLogSingleEntry1
0x140124bd2  nop     dword ptr [rax+rax+00h]
0x140124bd7  lea     r9, aFailedToCreate_12; "Failed to create RegisterGpuPerformance"...
0x140124bde  mov     cs:WdLogGlobalForLineNumber, 530h
0x140124be8  jmp     loc_140124B4C
0x140124bed  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetLocalAdapterMemory@@9@4U_UNICODE_STRING@@B; "02"
0x140124bf4  mov     cs:byte_1400879AA, 1
0x140124bfb  mov     [rbp+57h+Info.Name], rax
0x140124bff  lea     rdx, [rbp+57h+Info]; Info
0x140124c03  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetLocalAdapterMemory@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetLocalAdapterMemory'::`2'::Descriptors
0x140124c0a  mov     qword ptr [rbp+57h+Info.Version], 200h
0x140124c12  lea     rcx, GpuPerformanceCounterSetLocalAdapterMemory; Registration
0x140124c19  mov     [rbp+57h+Info.Counters], rax
0x140124c1d  mov     qword ptr [rbp+57h+Info.CounterCount], 1
0x140124c25  mov     [rbp+57h+var_30], r14
0x140124c29  mov     [rbp+57h+Info.Callback], r14
0x140124c2d  mov     [rbp+57h+Info.CallbackContext], r14
0x140124c31  call    cs:__imp_PcwRegister
0x140124c38  nop     dword ptr [rax+rax+00h]
0x140124c3d  movsxd  rdi, eax
0x140124c40  test    eax, eax
0x140124c42  jns     short loc_140124C6E
0x140124c44  mov     rdx, rdi
0x140124c47  mov     ecx, 1
0x140124c4c  call    cs:__imp_WdLogSingleEntry1
0x140124c53  nop     dword ptr [rax+rax+00h]
0x140124c58  lea     r9, aFailedToCreate_5; "Failed to create RegisterGpuPerformance"...
0x140124c5f  mov     cs:WdLogGlobalForLineNumber, 53Bh
0x140124c69  jmp     loc_140124B4C
0x140124c6e  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetNonLocalAdapterMemory@@9@4U_UNICODE_STRING@@B; "8:"
0x140124c75  mov     cs:byte_1400879A9, 1
0x140124c7c  mov     [rbp+57h+Info.Name], rax
0x140124c80  lea     rdx, [rbp+57h+Info]; Info
0x140124c84  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetNonLocalAdapterMemory@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetNonLocalAdapterMemory'::`2'::Descriptors
0x140124c8b  mov     qword ptr [rbp+57h+Info.Version], 200h
0x140124c93  lea     rcx, GpuPerformanceCounterSetNonLocalAdapterMemory; Registration
0x140124c9a  mov     [rbp+57h+Info.Counters], rax
0x140124c9e  mov     qword ptr [rbp+57h+Info.CounterCount], 1
0x140124ca6  mov     [rbp+57h+var_30], r14
0x140124caa  mov     [rbp+57h+Info.Callback], r14
0x140124cae  mov     [rbp+57h+Info.CallbackContext], r14
0x140124cb2  call    cs:__imp_PcwRegister
0x140124cb9  nop     dword ptr [rax+rax+00h]
0x140124cbe  movsxd  rdi, eax
0x140124cc1  test    eax, eax
0x140124cc3  jns     short loc_140124CEF
0x140124cc5  mov     rdx, rdi
0x140124cc8  mov     ecx, 1
0x140124ccd  call    cs:__imp_WdLogSingleEntry1
0x140124cd4  nop     dword ptr [rax+rax+00h]
0x140124cd9  lea     r9, aFailedToCreate_20; "Failed to create RegisterGpuPerformance"...
0x140124ce0  mov     cs:WdLogGlobalForLineNumber, 546h
0x140124cea  jmp     loc_140124B4C
0x140124cef  mov     cs:byte_1400879A8, 1
0x140124cf6  call    Feature_FenceStorageUsingVidMmAlloc__private_IsEnabledDeviceUsageNoInline
0x140124cfb  test    eax, eax
0x140124cfd  setnz   cs:?g_Feature_FenceStorageUsingVidMmAlloc@@3EC; uchar volatile g_Feature_FenceStorageUsingVidMmAlloc
0x140124d04  mov     cs:?g_Feature_Largify64KBPrototype@@3EC, r14b; uchar volatile g_Feature_Largify64KBPrototype
0x140124d0b  mov     [rsp+0B0h+Depth], r14w; Depth
0x140124d11  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140124d18  mov     [rsp+0B0h+Tag], 35356956h; Tag
0x140124d20  mov     r9d, 1; PoolType
0x140124d26  mov     [rsp+0B0h+Size], 90h; Size
0x140124d2f  xor     r8d, r8d; Free
0x140124d32  xor     edx, edx; Allocate
0x140124d34  mov     [rsp+0B0h+Flags], r14d; Flags
0x140124d39  call    cs:__imp_ExInitializeLookasideListEx
0x140124d40  nop     dword ptr [rax+rax+00h]
0x140124d45  cmp     cs:?g_Feature_ResourcePoolManagement@@3_NA, r14b; bool g_Feature_ResourcePoolManagement
0x140124d4c  jz      loc_140124962
0x140124d52  call    ?VidMmInitializeSystemResourcePool@@YAJXZ; VidMmInitializeSystemResourcePool(void)
0x140124d57  movsxd  rdi, eax
0x140124d5a  test    eax, eax
0x140124d5c  jns     loc_140124962
0x140124d62  mov     rdx, rdi
0x140124d65  mov     ecx, 3
0x140124d6a  call    cs:__imp_WdLogSingleEntry1
0x140124d71  nop     dword ptr [rax+rax+00h]
0x140124d76  mov     cs:WdLogGlobalForLineNumber, 55Dh
0x140124d80  movsxd  r8, edi
0x140124d83  xor     r9d, r9d
0x140124d86  mov     byte ptr [rsp+0B0h+Size], r14b
0x140124d8b  mov     edx, 811h
0x140124d90  mov     ecx, 193h
0x140124d95  mov     qword ptr [rsp+0B0h+Flags], r14
0x140124d9a  call    cs:__imp_?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x140124da1  nop     dword ptr [rax+rax+00h]
0x140124da6  test    eax, eax
0x140124da8  jns     loc_140124962
0x140124dae  movsxd  rbx, eax
0x140124db1  mov     ecx, 1
0x140124db6  mov     rdx, rbx
0x140124db9  call    cs:__imp_WdLogSingleEntry1
0x140124dc0  nop     dword ptr [rax+rax+00h]
0x140124dc5  mov     qword ptr [rsp+0B0h+Depth], r14
0x140124dca  lea     r9, aFailedToDxgcre; "Failed to DxgCreateLiveDumpWithWdLogs, "...
0x140124dd1  mov     qword ptr [rsp+0B0h+Tag], r14
0x140124dd6  mov     edx, esi
0x140124dd8  mov     [rsp+0B0h+Size], r14
0x140124ddd  mov     qword ptr [rsp+0B0h+Flags], rbx
0x140124de2  mov     cs:WdLogGlobalForLineNumber, 56Eh
0x140124dec  jmp     loc_14012495D
  ... truncated ...
```
