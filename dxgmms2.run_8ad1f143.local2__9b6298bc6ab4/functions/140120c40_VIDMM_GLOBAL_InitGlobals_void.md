# VIDMM_GLOBAL::InitGlobals(void)

- ea: `0x140120c40`
- end: `0x1401212c3`
- name: `?InitGlobals@VIDMM_GLOBAL@@SAJXZ`
- size: `1667`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140120c28`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140017380`
- `0x140031178`
- `0x140031604`
- `0x140044e28`
- `0x1400473a8`
- `0x140047948`
- `0x1400479a0`
- `0x140058760`
- `0x1400adadc`
- `0x1400bce24`
- `0x1400bdb50`
- `0x14011a844`
- `0x14011b1e8`
- `0x140120c40`

## import_xrefs

- `ntoskrnl!PcwRegister` at `0x140120f31`
- `ntoskrnl!PcwRegister` at `0x140120fb8`
- `ntoskrnl!PcwRegister` at `0x140121038`
- `ntoskrnl!PcwRegister` at `0x1401210b9`
- `ntoskrnl!PcwRegister` at `0x140120f31`
- `ntoskrnl!PcwRegister` at `0x140120fb8`
- `ntoskrnl!PcwRegister` at `0x140121038`
- `ntoskrnl!PcwRegister` at `0x1401210b9`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1401211ca`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1401211ca`
- `watchdog!WdLogSingleEntry0` at `0x140120d18`
- `watchdog!WdLogSingleEntry0` at `0x140120ebb`
- `watchdog!WdLogSingleEntry0` at `0x140121273`
- `watchdog!WdLogSingleEntry0` at `0x140120d18`
- `watchdog!WdLogSingleEntry0` at `0x140120ebb`
- `watchdog!WdLogSingleEntry0` at `0x140121273`
- `watchdog!WdLogSingleEntry1` at `0x140120d49`
- `watchdog!WdLogSingleEntry1` at `0x140120d9f`
- `watchdog!WdLogSingleEntry1` at `0x140120e0e`
- `watchdog!WdLogSingleEntry1` at `0x140120f4c`
- `watchdog!WdLogSingleEntry1` at `0x140120fd2`
- `watchdog!WdLogSingleEntry1` at `0x140121053`
- `watchdog!WdLogSingleEntry1` at `0x1401210d8`
- `watchdog!WdLogSingleEntry1` at `0x14012114c`
- `watchdog!WdLogSingleEntry1` at `0x1401211f6`
- `watchdog!WdLogSingleEntry1` at `0x140121224`
- `watchdog!WdLogSingleEntry1` at `0x140120d49`
- `watchdog!WdLogSingleEntry1` at `0x140120d9f`
- `watchdog!WdLogSingleEntry1` at `0x140120e0e`
- `watchdog!WdLogSingleEntry1` at `0x140120f4c`
- `watchdog!WdLogSingleEntry1` at `0x140120fd2`
- `watchdog!WdLogSingleEntry1` at `0x140121053`
- `watchdog!WdLogSingleEntry1` at `0x1401210d8`
- `watchdog!WdLogSingleEntry1` at `0x14012114c`
- `watchdog!WdLogSingleEntry1` at `0x1401211f6`
- `watchdog!WdLogSingleEntry1` at `0x140121224`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x14012112d`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x14012112d`
- `HAL!KeQueryPerformanceCounter` at `0x140120c5a`
- `HAL!KeQueryPerformanceCounter` at `0x140120c5a`

## string_xrefs

- `0x140120f58`: `Failed to create RegisterGpuPerformanceCounterSetProcessMemory, returning 0x%I64x`
- `0x140120fde`: `Failed to create RegisterGpuPerformanceCounterSetAdapterMemory, returning 0x%I64x`
- `0x14012105f`: `Failed to create RegisterGpuPerformanceCounterSetLocalAdapterMemory, returning 0x%I64x`
- `0x1401210e4`: `Failed to create RegisterGpuPerformanceCounterSetNonLocalAdapterMemory, returning 0x%I64x`
- `0x14012115d`: `Failed to DxgCreateLiveDumpWithWdLogs, error: 0x%I64x`

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
  int LiveDumpWithWdLogs; // eax
  __int64 v26; // rbx
  int v27; // ecx
  int v28; // r8d
  int DedicatedPartition; // eax
  int v30; // ecx
  int v31; // r8d
  int Size; // [rsp+28h] [rbp-31h]
  _PCW_REGISTRATION_INFORMATION Info; // [rsp+50h] [rbp-9h] BYREF
  __int64 v34; // [rsp+80h] [rbp+27h]

  KeQueryPerformanceCounter(&VIDMM_GLOBAL::_QpcFrequency);
  qword_140086690 = (__int64)&g_VidMmProcessListHead;
  g_VidMmProcessListHead.Flink = &g_VidMmProcessListHead;
  g_VidMmProcessListHeadLock = 0;
  VIDMM_GLOBAL::_DedicatedPartitionLock = 0;
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
    _InterlockedIncrement(&dword_1400866FC);
    WdLogSingleEntry0(6);
    v5 = 1187;
    v6 = L"Failed to allocate memory for VIDMM_PROCESS::_pDxProcessPerAdapterCount.\n";
LABEL_36:
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
    WdLogGlobalForLineNumber = 1199;
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
    WdLogGlobalForLineNumber = 1207;
    goto LABEL_9;
  }
  v14 = (struct VIDMM_EXISTINGSYSMEM_HEAP *)operator new(16, 1697737046, 256);
  if ( !v14 )
  {
    g_pExistingSysMemHeap = 0;
    _InterlockedIncrement(&dword_14008689C);
    WdLogSingleEntry0(6);
    v5 = 1219;
    v6 = L"Failed to allocate memory for VIDMM_EXISTINGSYSMEM_HEAP.\n";
    goto LABEL_36;
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
    WdLogGlobalForLineNumber = 1226;
    goto LABEL_9;
  }
  qword_140086AC8 = (__int64)&VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead;
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
      _InterlockedIncrement(&dword_14008688C);
      WdLogSingleEntry0(6);
      v5 = 1245;
      v6 = L"Failed to allocate memory for global array VIDMM_SYSTEM_HEAP per NUMA node.\n";
      goto LABEL_36;
    }
    VIDMM_PARTITION::_PartitionTree = 0;
    qword_1400862B8 = (__int64)&VIDMM_GLOBAL::_AdapterListHead;
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
      byte_1400869A2 = 1;
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
        byte_1400869A1 = 1;
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
          byte_1400869A0 = 1;
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
            byte_140086298 = 1;
            g_Feature_FenceStorageUsingVidMmAlloc = (unsigned int)Feature_FenceStorageUsingVidMmAlloc__private_IsEnabledDeviceUsageNoInline() != 0;
            g_Feature_Largify64KBPrototype = 0;
            ExInitializeLookasideListEx(&g_VaRangeLookasideList, 0, 0, PagedPool, 0, 0x90u, 0x35356956u, 0);
            if ( (unsigned int)Feature_IntelligentCarveout__private_IsEnabledDeviceUsageNoInline() )
            {
              DedicatedPartition = VIDMM_GLOBAL::CreateDedicatedPartition();
              if ( DedicatedPartition < 0 )
              {
                WdLogSingleEntry1(3, DedicatedPartition);
                WdLogGlobalForLineNumber = 1321;
              }
            }
            return (unsigned int)v8;
          }
          WdLogSingleEntry1(1, v24);
          v21 = L"Failed to create RegisterGpuPerformanceCounterSetNonLocalAdapterMemory, returning 0x%I64x";
          WdLogGlobalForLineNumber = 1295;
        }
        else
        {
          WdLogSingleEntry1(1, v23);
          v21 = L"Failed to create RegisterGpuPerformanceCounterSetLocalAdapterMemory, returning 0x%I64x";
          WdLogGlobalForLineNumber = 1284;
        }
      }
      else
      {
        WdLogSingleEntry1(1, v22);
        v21 = L"Failed to create RegisterGpuPerformanceCounterSetAdapterMemory, returning 0x%I64x";
        WdLogGlobalForLineNumber = 1273;
      }
    }
    else
    {
      WdLogSingleEntry1(1, v18);
      v21 = L"Failed to create RegisterGpuPerformanceCounterSetProcessMemory, returning 0x%I64x";
      WdLogGlobalForLineNumber = 1262;
    }
    DxgkLogInternalTriageEvent(v19, 0x40000, v20, (_DWORD)v21, v8, 0, 0, 0);
    LOBYTE(Size) = 0;
    LiveDumpWithWdLogs = DxgCreateLiveDumpWithWdLogs(403, 2065, (int)v8, 0, 0, Size);
    if ( LiveDumpWithWdLogs < 0 )
    {
      v26 = LiveDumpWithWdLogs;
      WdLogSingleEntry1(1, LiveDumpWithWdLogs);
      WdLogGlobalForLineNumber = 1336;
      DxgkLogInternalTriageEvent(
        v27,
        0x40000,
        v28,
        (unsigned int)L"Failed to DxgCreateLiveDumpWithWdLogs, error: 0x%I64x",
        v26,
        0,
        0,
        0);
    }
    return (unsigned int)v8;
  }
  VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListLock = 0;
  WdLogSingleEntry1(1, -1073741801);
  WdLogGlobalForLineNumber = 1234;
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
0x140120c40  push    rbp
0x140120c42  push    rbx
0x140120c43  push    rsi
0x140120c44  push    rdi
0x140120c45  push    r14
0x140120c47  lea     rbp, [rsp-37h]
0x140120c4c  sub     rsp, 90h
0x140120c53  lea     rcx, ?_QpcFrequency@VIDMM_GLOBAL@@2T_LARGE_INTEGER@@A; PerformanceFrequency
0x140120c5a  call    cs:__imp_KeQueryPerformanceCounter
0x140120c61  nop     dword ptr [rax+rax+00h]
0x140120c66  lea     rax, ?g_VidMmProcessListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_VidMmProcessListHead
0x140120c6d  xor     esi, esi
0x140120c6f  mov     cs:qword_140086690, rax
0x140120c76  mov     cs:?g_VidMmProcessListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_VidMmProcessListHead
0x140120c7d  mov     cs:?g_VidMmProcessListHeadLock@@3U_EX_PUSH_LOCK@@A, rsi; _EX_PUSH_LOCK g_VidMmProcessListHeadLock
0x140120c84  mov     cs:?_DedicatedPartitionLock@VIDMM_GLOBAL@@2U_EX_PUSH_LOCK@@A, rsi; _EX_PUSH_LOCK VIDMM_GLOBAL::_DedicatedPartitionLock
0x140120c8b  mov     cs:bTracingEnabled, sil
0x140120c92  call    McGenEventRegister_EtwRegister
0x140120c97  call    TlgRegisterAggregateProviderEx
0x140120c9c  call    ?ReadConfiguration@VIDMM_GLOBAL@@SAXXZ; VIDMM_GLOBAL::ReadConfiguration(void)
0x140120ca1  mov     edx, 6D4D6956h
0x140120ca6  lea     r8d, [rsi+40h]
0x140120caa  mov     ecx, 18000h
0x140120caf  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140120cb4  mov     qword ptr cs:?_RotationHistory@VIDMM_GLOBAL@@2U_VIDMM_ROTATION_HISTORY@@A, rax; _VIDMM_ROTATION_HISTORY VIDMM_GLOBAL::_RotationHistory
0x140120cbb  test    rax, rax
0x140120cbe  jz      short loc_140120CCB
0x140120cc0  mov     qword ptr cs:?_RotationHistory@VIDMM_GLOBAL@@2U_VIDMM_ROTATION_HISTORY@@A+8, 800h; _VIDMM_ROTATION_HISTORY VIDMM_GLOBAL::_RotationHistory
0x140120ccb  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140120cd0  mov     rcx, rax; this
0x140120cd3  call    ?GetMaximumGlobalAdapterCount@DXGGLOBAL@@QEBAKXZ; DXGGLOBAL::GetMaximumGlobalAdapterCount(void)
0x140120cd8  mov     ecx, eax
0x140120cda  mov     r14, 0FFFFFFFFFFFFFFFFh
0x140120ce1  mov     eax, 4
0x140120ce6  mov     ebx, 100h
0x140120ceb  mul     rcx
0x140120cee  mov     r8d, ebx
0x140120cf1  mov     edx, 33316956h
0x140120cf6  cmovb   rax, r14
0x140120cfa  mov     rcx, rax
0x140120cfd  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140120d02  mov     cs:?_pDxProcessPerAdapterCount@VIDMM_PROCESS@@2PEAJEA, rax; long * VIDMM_PROCESS::_pDxProcessPerAdapterCount
0x140120d09  test    rax, rax
0x140120d0c  jnz     short loc_140120D35
0x140120d0e  lock inc cs:dword_1400866FC
0x140120d15  lea     ecx, [rax+6]
0x140120d18  call    cs:__imp_WdLogSingleEntry0
0x140120d1f  nop     dword ptr [rax+rax+00h]
0x140120d24  mov     eax, 4A3h
0x140120d29  lea     r9, aFailedToAlloca_39; "Failed to allocate memory for VIDMM_PRO"...
0x140120d30  jmp     loc_14012128B
0x140120d35  call    ?VidMmInitDmaPoolGlobals@@YAJXZ; VidMmInitDmaPoolGlobals(void)
0x140120d3a  movsxd  rdi, eax
0x140120d3d  test    eax, eax
0x140120d3f  jns     short loc_140120D8B
0x140120d41  mov     rdx, rdi
0x140120d44  mov     ecx, 1
0x140120d49  call    cs:__imp_WdLogSingleEntry1
0x140120d50  nop     dword ptr [rax+rax+00h]
0x140120d55  lea     r9, aFailedToVidmmD; "Failed to VIDMM_DMA_POOL::InitGlobals i"...
0x140120d5c  mov     cs:WdLogGlobalForLineNumber, 4AFh
0x140120d66  mov     qword ptr [rsp+0B0h+Depth], rsi
0x140120d6b  mov     qword ptr [rsp+0B0h+Tag], rsi
0x140120d70  mov     [rsp+0B0h+Size], rsi
0x140120d75  mov     qword ptr [rsp+0B0h+Flags], rdi
0x140120d7a  mov     edx, 40000h
0x140120d7f  call    DxgkLogInternalTriageEvent
0x140120d84  mov     eax, edi
0x140120d86  jmp     loc_1401212B4
0x140120d8b  call    ?InitGlobalStorage@VIDMM_PROCESS_FENCE_STORAGE@@SAJXZ; VIDMM_PROCESS_FENCE_STORAGE::InitGlobalStorage(void)
0x140120d90  movsxd  rdi, eax
0x140120d93  test    eax, eax
0x140120d95  jns     short loc_140120DBE
0x140120d97  mov     rdx, rdi
0x140120d9a  mov     ecx, 1
0x140120d9f  call    cs:__imp_WdLogSingleEntry1
0x140120da6  nop     dword ptr [rax+rax+00h]
0x140120dab  lea     r9, aFailedToVidmmP; "Failed to VIDMM_PROCESS_FENCE_STORAGE::"...
0x140120db2  mov     cs:WdLogGlobalForLineNumber, 4B7h
0x140120dbc  jmp     short loc_140120D66
0x140120dbe  mov     r8, rbx
0x140120dc1  mov     edx, 65316956h
0x140120dc6  mov     ecx, 10h
0x140120dcb  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140120dd0  mov     rcx, rax
0x140120dd3  test    rax, rax
0x140120dd6  jz      loc_140121260
0x140120ddc  lea     rax, ??_7VIDMM_EXISTINGSYSMEM_HEAP@@6B@; const VIDMM_EXISTINGSYSMEM_HEAP::`vftable'
0x140120de3  mov     [rcx+8], sil
0x140120de7  mov     [rcx], rax
0x140120dea  xor     r8d, r8d
0x140120ded  mov     rax, [rax+8]
0x140120df1  xor     edx, edx
0x140120df3  mov     cs:?g_pExistingSysMemHeap@@3PEAVVIDMM_EXISTINGSYSMEM_HEAP@@EA, rcx; VIDMM_EXISTINGSYSMEM_HEAP * g_pExistingSysMemHeap
0x140120dfa  call    _guard_dispatch_icall
0x140120dff  movsxd  rdi, eax
0x140120e02  test    eax, eax
0x140120e04  jns     short loc_140120E30
0x140120e06  mov     rdx, rdi
0x140120e09  mov     ecx, 1
0x140120e0e  call    cs:__imp_WdLogSingleEntry1
0x140120e15  nop     dword ptr [rax+rax+00h]
0x140120e1a  lea     r9, aFailedToInitia_8; "Failed to Initialize existing sysmem he"...
0x140120e21  mov     cs:WdLogGlobalForLineNumber, 4CAh
0x140120e2b  jmp     loc_140120D66
0x140120e30  lea     rax, ?_GlobalHeapManagerListHead@VIDMM_RECYCLE_HEAP_MGR@@0U_LIST_ENTRY@@A; _LIST_ENTRY VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead
0x140120e37  mov     r8, rbx
0x140120e3a  mov     edx, 30316956h
0x140120e3f  mov     cs:qword_140086AC8, rax
0x140120e46  mov     ecx, 20h ; ' '
0x140120e4b  mov     cs:?_GlobalHeapManagerListHead@VIDMM_RECYCLE_HEAP_MGR@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead
0x140120e52  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140120e57  test    rax, rax
0x140120e5a  jz      loc_140121211
0x140120e60  mov     [rax], rsi
0x140120e63  mov     [rax+8], rsi
0x140120e67  mov     [rax+10h], esi
0x140120e6a  mov     dword ptr [rax+14h], 4Eh ; 'N'
0x140120e71  mov     [rax+18h], r14d
0x140120e75  mov     cs:?_GlobalHeapManagerListLock@VIDMM_RECYCLE_HEAP_MGR@@0PEAVDXGPUSHLOCK@@EA, rax; DXGPUSHLOCK * VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListLock
0x140120e7c  call    ?VidMmCalculateHeapPerNumaNodeArraySize@@YAKXZ; VidMmCalculateHeapPerNumaNodeArraySize(void)
0x140120e81  mov     ecx, eax
0x140120e83  mov     r8, rbx
0x140120e86  mov     cs:?g_ppSystemHeapPerNumaNodeArraySize@@3KA, ecx; ulong g_ppSystemHeapPerNumaNodeArraySize
0x140120e8c  mov     eax, 8
0x140120e91  mul     rcx
0x140120e94  mov     edx, 63316956h
0x140120e99  cmovb   rax, r14
0x140120e9d  mov     rcx, rax
0x140120ea0  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140120ea5  mov     cs:?g_ppSystemHeapPerNumaNode@@3PEAPEAVVIDMM_SYSTEM_HEAP@@EA, rax; VIDMM_SYSTEM_HEAP * * g_ppSystemHeapPerNumaNode
0x140120eac  test    rax, rax
0x140120eaf  jnz     short loc_140120ED8
0x140120eb1  lock inc cs:dword_14008688C
0x140120eb8  lea     ecx, [rax+6]
0x140120ebb  call    cs:__imp_WdLogSingleEntry0
0x140120ec2  nop     dword ptr [rax+rax+00h]
0x140120ec7  mov     eax, 4DDh
0x140120ecc  lea     r9, aFailedToAlloca_16; "Failed to allocate memory for global ar"...
0x140120ed3  jmp     loc_14012128B
0x140120ed8  lea     rax, ?_AdapterListHead@VIDMM_GLOBAL@@2U_LIST_ENTRY@@A; _LIST_ENTRY VIDMM_GLOBAL::_AdapterListHead
0x140120edf  mov     cs:?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A, rsi; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x140120ee6  mov     cs:qword_1400862B8, rax
0x140120eed  lea     rdx, [rbp+57h+Info]; Info
0x140120ef1  mov     cs:?_AdapterListHead@VIDMM_GLOBAL@@2U_LIST_ENTRY@@A, rax; _LIST_ENTRY VIDMM_GLOBAL::_AdapterListHead
0x140120ef8  lea     rcx, GpuPerformanceCounterSetProcessMemory; Registration
0x140120eff  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetProcessMemory@@9@4U_UNICODE_STRING@@B; "$&"
0x140120f06  mov     qword ptr [rbp+57h+Info.Version], 200h
0x140120f0e  mov     [rbp+57h+Info.Name], rax
0x140120f12  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetProcessMemory@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetProcessMemory'::`2'::Descriptors
0x140120f19  mov     [rbp+57h+Info.Counters], rax
0x140120f1d  mov     qword ptr [rbp+57h+Info.CounterCount], 5
0x140120f25  mov     [rbp+57h+var_30], rsi
0x140120f29  mov     [rbp+57h+Info.Callback], rsi
0x140120f2d  mov     [rbp+57h+Info.CallbackContext], rsi
0x140120f31  call    cs:__imp_PcwRegister
0x140120f38  nop     dword ptr [rax+rax+00h]
0x140120f3d  movsxd  rdi, eax
0x140120f40  test    eax, eax
0x140120f42  jns     short loc_140120F6E
0x140120f44  mov     rdx, rdi
0x140120f47  mov     ecx, 1
0x140120f4c  call    cs:__imp_WdLogSingleEntry1
0x140120f53  nop     dword ptr [rax+rax+00h]
0x140120f58  lea     r9, aFailedToCreate; "Failed to create RegisterGpuPerformance"...
0x140120f5f  mov     cs:WdLogGlobalForLineNumber, 4EEh
0x140120f69  jmp     loc_1401210F5
0x140120f6e  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetAdapterMemory@@9@4U_UNICODE_STRING@@B; "$&"
0x140120f75  mov     cs:byte_1400869A2, 1
0x140120f7c  mov     [rbp+57h+Info.Name], rax
0x140120f80  lea     rdx, [rbp+57h+Info]; Info
0x140120f84  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetAdapterMemory@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetAdapterMemory'::`2'::Descriptors
0x140120f8b  mov     qword ptr [rbp+57h+Info.Version], 200h
0x140120f93  lea     rcx, GpuPerformanceCounterSetAdapterMemory; Registration
0x140120f9a  mov     [rbp+57h+Info.Counters], rax
0x140120f9e  mov     qword ptr [rbp+57h+Info.CounterCount], 3
0x140120fa6  mov     r14d, 3
0x140120fac  mov     [rbp+57h+var_30], rsi
0x140120fb0  mov     [rbp+57h+Info.Callback], rsi
0x140120fb4  mov     [rbp+57h+Info.CallbackContext], rsi
0x140120fb8  call    cs:__imp_PcwRegister
0x140120fbf  nop     dword ptr [rax+rax+00h]
0x140120fc4  movsxd  rdi, eax
0x140120fc7  test    eax, eax
0x140120fc9  jns     short loc_140120FF4
0x140120fcb  mov     rdx, rdi
0x140120fce  lea     ecx, [r14-2]
0x140120fd2  call    cs:__imp_WdLogSingleEntry1
0x140120fd9  nop     dword ptr [rax+rax+00h]
0x140120fde  lea     r9, aFailedToCreate_12; "Failed to create RegisterGpuPerformance"...
0x140120fe5  mov     cs:WdLogGlobalForLineNumber, 4F9h
0x140120fef  jmp     loc_1401210F5
0x140120ff4  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetLocalAdapterMemory@@9@4U_UNICODE_STRING@@B; "02"
0x140120ffb  mov     cs:byte_1400869A1, 1
0x140121002  mov     [rbp+57h+Info.Name], rax
0x140121006  lea     rdx, [rbp+57h+Info]; Info
0x14012100a  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetLocalAdapterMemory@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetLocalAdapterMemory'::`2'::Descriptors
0x140121011  mov     qword ptr [rbp+57h+Info.Version], 200h
0x140121019  lea     rcx, GpuPerformanceCounterSetLocalAdapterMemory; Registration
0x140121020  mov     [rbp+57h+Info.Counters], rax
0x140121024  mov     qword ptr [rbp+57h+Info.CounterCount], 1
0x14012102c  mov     [rbp+57h+var_30], rsi
0x140121030  mov     [rbp+57h+Info.Callback], rsi
0x140121034  mov     [rbp+57h+Info.CallbackContext], rsi
0x140121038  call    cs:__imp_PcwRegister
0x14012103f  nop     dword ptr [rax+rax+00h]
0x140121044  movsxd  rdi, eax
0x140121047  test    eax, eax
0x140121049  jns     short loc_140121075
0x14012104b  mov     rdx, rdi
0x14012104e  mov     ecx, 1
0x140121053  call    cs:__imp_WdLogSingleEntry1
0x14012105a  nop     dword ptr [rax+rax+00h]
0x14012105f  lea     r9, aFailedToCreate_5; "Failed to create RegisterGpuPerformance"...
0x140121066  mov     cs:WdLogGlobalForLineNumber, 504h
0x140121070  jmp     loc_1401210F5
0x140121075  lea     rax, ?Name@?1??InitRegistrationInformationGpuPerformanceCounterSetNonLocalAdapterMemory@@9@4U_UNICODE_STRING@@B; "8:"
0x14012107c  mov     cs:byte_1400869A0, 1
0x140121083  mov     [rbp+57h+Info.Name], rax
0x140121087  lea     rdx, [rbp+57h+Info]; Info
0x14012108b  lea     rax, ?Descriptors@?1??InitRegistrationInformationGpuPerformanceCounterSetNonLocalAdapterMemory@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `InitRegistrationInformationGpuPerformanceCounterSetNonLocalAdapterMemory'::`2'::Descriptors
0x140121092  mov     qword ptr [rbp+57h+Info.Version], 200h
0x14012109a  lea     rcx, GpuPerformanceCounterSetNonLocalAdapterMemory; Registration
0x1401210a1  mov     [rbp+57h+Info.Counters], rax
0x1401210a5  mov     qword ptr [rbp+57h+Info.CounterCount], 1
0x1401210ad  mov     [rbp+57h+var_30], rsi
0x1401210b1  mov     [rbp+57h+Info.Callback], rsi
0x1401210b5  mov     [rbp+57h+Info.CallbackContext], rsi
0x1401210b9  call    cs:__imp_PcwRegister
0x1401210c0  nop     dword ptr [rax+rax+00h]
0x1401210c5  movsxd  rdi, eax
0x1401210c8  test    eax, eax
0x1401210ca  jns     loc_140121182
0x1401210d0  mov     rdx, rdi
0x1401210d3  mov     ecx, 1
0x1401210d8  call    cs:__imp_WdLogSingleEntry1
0x1401210df  nop     dword ptr [rax+rax+00h]
0x1401210e4  lea     r9, aFailedToCreate_20; "Failed to create RegisterGpuPerformance"...
0x1401210eb  mov     cs:WdLogGlobalForLineNumber, 50Fh
0x1401210f5  mov     qword ptr [rsp+0B0h+Depth], rsi
0x1401210fa  mov     edx, 40000h
0x1401210ff  mov     qword ptr [rsp+0B0h+Tag], rsi
0x140121104  mov     [rsp+0B0h+Size], rsi
0x140121109  mov     qword ptr [rsp+0B0h+Flags], rdi
0x14012110e  call    DxgkLogInternalTriageEvent
0x140121113  movsxd  r8, edi
0x140121116  xor     r9d, r9d
0x140121119  mov     edx, 811h
0x14012111e  mov     byte ptr [rsp+0B0h+Size], sil
0x140121123  mov     ecx, 193h
0x140121128  mov     qword ptr [rsp+0B0h+Flags], rsi
0x14012112d  call    cs:__imp_?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x140121134  nop     dword ptr [rax+rax+00h]
0x140121139  test    eax, eax
0x14012113b  jns     loc_140120D84
0x140121141  movsxd  rbx, eax
0x140121144  mov     ecx, 1
0x140121149  mov     rdx, rbx
0x14012114c  call    cs:__imp_WdLogSingleEntry1
0x140121153  nop     dword ptr [rax+rax+00h]
0x140121158  mov     qword ptr [rsp+0B0h+Depth], rsi
0x14012115d  lea     r9, aFailedToDxgcre; "Failed to DxgCreateLiveDumpWithWdLogs, "...
0x140121164  mov     qword ptr [rsp+0B0h+Tag], rsi
0x140121169  mov     [rsp+0B0h+Size], rsi
0x14012116e  mov     qword ptr [rsp+0B0h+Flags], rbx
0x140121173  mov     cs:WdLogGlobalForLineNumber, 538h
0x14012117d  jmp     loc_140120D7A
0x140121182  mov     cs:byte_140086298, 1
0x140121189  call    Feature_FenceStorageUsingVidMmAlloc__private_IsEnabledDeviceUsageNoInline
0x14012118e  test    eax, eax
0x140121190  setnz   cs:?g_Feature_FenceStorageUsingVidMmAlloc@@3EC; uchar volatile g_Feature_FenceStorageUsingVidMmAlloc
0x140121197  mov     cs:?g_Feature_Largify64KBPrototype@@3EC, sil; uchar volatile g_Feature_Largify64KBPrototype
0x14012119e  mov     [rsp+0B0h+Depth], si; Depth
0x1401211a3  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1401211aa  mov     [rsp+0B0h+Tag], 35356956h; Tag
0x1401211b2  mov     r9d, 1; PoolType
0x1401211b8  mov     [rsp+0B0h+Size], 90h; Size
0x1401211c1  xor     r8d, r8d; Free
0x1401211c4  xor     edx, edx; Allocate
0x1401211c6  mov     [rsp+0B0h+Flags], esi; Flags
0x1401211ca  call    cs:__imp_ExInitializeLookasideListEx
0x1401211d1  nop     dword ptr [rax+rax+00h]
0x1401211d6  call    Feature_IntelligentCarveout__private_IsEnabledDeviceUsageNoInline
0x1401211db  test    eax, eax
0x1401211dd  jz      loc_140120D84
0x1401211e3  call    ?CreateDedicatedPartition@VIDMM_GLOBAL@@SAJXZ; VIDMM_GLOBAL::CreateDedicatedPartition(void)
0x1401211e8  test    eax, eax
0x1401211ea  jns     loc_140120D84
0x1401211f0  movsxd  rdx, eax
0x1401211f3  mov     ecx, r14d
0x1401211f6  call    cs:__imp_WdLogSingleEntry1
0x1401211fd  nop     dword ptr [rax+rax+00h]
0x140121202  mov     cs:WdLogGlobalForLineNumber, 529h
0x14012120c  jmp     loc_140120D84
0x140121211  mov     cs:?_GlobalHeapManagerListLock@VIDMM_RECYCLE_HEAP_MGR@@0PEAVDXGPUSHLOCK@@EA, rsi; DXGPUSHLOCK * VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListLock
0x140121218  mov     rdx, 0FFFFFFFFC0000017h
0x14012121f  mov     ecx, 1
0x140121224  call    cs:__imp_WdLogSingleEntry1
0x14012122b  nop     dword ptr [rax+rax+00h]
0x140121230  mov     qword ptr [rsp+0B0h+Depth], rsi
  ... truncated ...
```
