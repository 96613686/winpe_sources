# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009510`
- end: `0x180009630`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004e64`
- `0x18000677c`
- `0x180006980`
- `0x180006f74`
- `0x180007170`
- `0x180009510`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800095fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800095fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095e5`

## string_xrefs

- `0x1800095de`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // r8d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        a2,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        (__int64)&wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)a2;
      if ( a2 < 0 )
        HIWORD(v8) |= 1u;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_20;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800200A8[25], qword_1800200A8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800200A8);
  }
}

```

## disassembly

```asm
0x180009510  sub     rsp, 38h
0x180009514  mov     eax, r8d
0x180009517  mov     r8d, edx
0x18000951a  btr     r8d, 1Fh; unsigned __int16
0x18000951f  test    ecx, ecx
0x180009521  jnz     short loc_18000957F
0x180009523  test    eax, eax
0x180009525  jnz     short loc_18000957F
0x180009527  test    r8d, r8d
0x18000952a  jnz     short loc_18000957F
0x18000952c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180009533  jnz     short loc_18000957A
0x180009535  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000953c  test    rax, rax
0x18000953f  jz      short loc_18000954A
0x180009541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009546  test    al, al
0x180009548  jnz     short loc_18000957A
0x18000954a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009551  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009556  test    al, al
0x180009558  jz      short loc_18000957A
0x18000955a  mov     rdx, cs:qword_1800200A8; SRWLock
0x180009561  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009568  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000956d  mov     rcx, cs:qword_1800200A8; SRWLock
0x180009574  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009579  nop
0x18000957a  jmp     loc_18000962B
0x18000957f  bt      r8d, 1Eh
0x180009584  jnb     short loc_18000959C
0x180009586  mov     r9d, eax; unsigned int
0x180009589  mov     edx, ecx; unsigned int
0x18000958b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009592  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009597  jmp     loc_18000962B
0x18000959c  test    eax, eax
0x18000959e  jnz     short loc_18000961A
0x1800095a0  cmp     r8d, 0FEh
0x1800095a7  jz      short loc_18000961A
0x1800095a9  mov     [rsp+38h+var_18], 0
0x1800095b2  mov     dword ptr [rsp+38h+var_18], ecx
0x1800095b6  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800095bc  test    edx, edx
0x1800095be  jns     short loc_1800095C6
0x1800095c0  or      word ptr [rsp+38h+var_18+6], 1
0x1800095c6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800095cd  test    rax, rax
0x1800095d0  jnz     short loc_18000960E
0x1800095d2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800095d9  test    rax, rax
0x1800095dc  jnz     short loc_1800095F2
0x1800095de  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800095e5  call    cs:__imp_GetModuleHandleW
0x1800095eb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800095f2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800095f9  mov     rcx, rax; hModule
0x1800095fc  call    cs:__imp_GetProcAddress
0x180009602  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009609  test    rax, rax
0x18000960c  jz      short loc_18000962B
0x18000960e  lea     rcx, [rsp+38h+var_18]
0x180009613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009618  jmp     short loc_18000962B
0x18000961a  mov     r9, rax
0x18000961d  mov     edx, ecx
0x18000961f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009626  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000962b  add     rsp, 38h
0x18000962f  retn
```
