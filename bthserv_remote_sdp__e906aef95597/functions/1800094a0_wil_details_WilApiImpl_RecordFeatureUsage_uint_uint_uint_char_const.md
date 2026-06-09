# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800094a0`
- end: `0x1800095cd`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004dd4`
- `0x1800065ac`
- `0x1800068d8`
- `0x180006eb4`
- `0x1800070e4`
- `0x1800094a0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009572`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009572`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000958f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000958f`

## string_xrefs

- `0x18000956b`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // edx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (v4 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        v4,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)v4;
      if ( a2 < 0 )
        HIWORD(v8) |= 1u;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_20;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_20:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180046070[25], qword_180046070);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180046070);
  }
}

```

## disassembly

```asm
0x1800094a0  sub     rsp, 38h
0x1800094a4  mov     eax, edx
0x1800094a6  btr     edx, 1Fh
0x1800094aa  test    ecx, ecx
0x1800094ac  jnz     short loc_180009509
0x1800094ae  test    r8d, r8d
0x1800094b1  jnz     short loc_180009509
0x1800094b3  test    edx, edx
0x1800094b5  jnz     short loc_180009509
0x1800094b7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x1800094bd  jnz     short loc_180009504
0x1800094bf  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800094c6  test    rax, rax
0x1800094c9  jz      short loc_1800094D4
0x1800094cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d0  test    al, al
0x1800094d2  jnz     short loc_180009504
0x1800094d4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800094db  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800094e0  test    al, al
0x1800094e2  jz      short loc_180009504
0x1800094e4  mov     rdx, cs:qword_180046070; SRWLock
0x1800094eb  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800094f2  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800094f7  mov     rcx, cs:qword_180046070; SRWLock
0x1800094fe  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009503  nop
0x180009504  jmp     loc_1800095C7
0x180009509  bt      edx, 1Eh
0x18000950d  jnb     short loc_180009529
0x18000950f  mov     r9d, r8d; unsigned int
0x180009512  movzx   r8d, dx; unsigned __int16
0x180009516  mov     edx, ecx; unsigned int
0x180009518  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000951f  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009524  jmp     loc_1800095C7
0x180009529  test    r8d, r8d
0x18000952c  jnz     loc_1800095B3
0x180009532  cmp     edx, 0FEh
0x180009538  jz      short loc_1800095B3
0x18000953a  and     [rsp+38h+var_18], 0
0x180009540  mov     dword ptr [rsp+38h+var_18], ecx
0x180009544  mov     word ptr [rsp+38h+var_18+4], dx
0x180009549  test    eax, eax
0x18000954b  jns     short loc_180009553
0x18000954d  or      word ptr [rsp+38h+var_18+6], 1
0x180009553  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000955a  test    rax, rax
0x18000955d  jnz     short loc_1800095A7
0x18000955f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009566  test    rax, rax
0x180009569  jnz     short loc_180009585
0x18000956b  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180009572  call    cs:__imp_GetModuleHandleW
0x180009579  nop     dword ptr [rax+rax+00h]
0x18000957e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009585  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000958c  mov     rcx, rax; hModule
0x18000958f  call    cs:__imp_GetProcAddress
0x180009596  nop     dword ptr [rax+rax+00h]
0x18000959b  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800095a2  test    rax, rax
0x1800095a5  jz      short loc_1800095C7
0x1800095a7  lea     rcx, [rsp+38h+var_18]
0x1800095ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b1  jmp     short loc_1800095C7
0x1800095b3  mov     r9d, r8d
0x1800095b6  mov     r8d, edx
0x1800095b9  mov     edx, ecx
0x1800095bb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800095c2  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800095c7  add     rsp, 38h
0x1800095cb  retn
```
