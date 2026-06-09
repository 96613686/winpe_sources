# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000ca10`
- end: `0x18000cb30`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180009314`
- `0x18000a844`
- `0x18000a9ac`
- `0x18000ad74`
- `0x18000af30`
- `0x18000ca10`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000cae5`
- `KERNEL32!GetModuleHandleW` at `0x18000cae5`
- `KERNEL32!GetProcAddress` at `0x18000cafc`
- `KERNEL32!GetProcAddress` at `0x18000cafc`

## string_xrefs

- `0x18000cade`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  __int64 v3; // rax
  __int64 v4; // r8
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v3 = a3;
  v4 = (unsigned int)a2;
  LODWORD(v4) = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || (_DWORD)v3 || (_DWORD)v4 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        a2,
        v3);
    }
    else if ( (_DWORD)v3 || (_DWORD)v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        v3);
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001E2B8[25], qword_18001E2B8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001E2B8);
  }
}

```

## disassembly

```asm
0x18000ca10  sub     rsp, 38h
0x18000ca14  mov     eax, r8d
0x18000ca17  mov     r8d, edx
0x18000ca1a  btr     r8d, 1Fh; unsigned __int16
0x18000ca1f  test    ecx, ecx
0x18000ca21  jnz     short loc_18000CA7F
0x18000ca23  test    eax, eax
0x18000ca25  jnz     short loc_18000CA7F
0x18000ca27  test    r8d, r8d
0x18000ca2a  jnz     short loc_18000CA7F
0x18000ca2c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000ca33  jnz     short loc_18000CA7A
0x18000ca35  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ca3c  test    rax, rax
0x18000ca3f  jz      short loc_18000CA4A
0x18000ca41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca46  test    al, al
0x18000ca48  jnz     short loc_18000CA7A
0x18000ca4a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000ca51  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000ca56  test    al, al
0x18000ca58  jz      short loc_18000CA7A
0x18000ca5a  mov     rdx, cs:qword_18001E2B8; SRWLock
0x18000ca61  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000ca68  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000ca6d  mov     rcx, cs:qword_18001E2B8; SRWLock
0x18000ca74  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ca79  nop
0x18000ca7a  jmp     loc_18000CB2B
0x18000ca7f  bt      r8d, 1Eh
0x18000ca84  jnb     short loc_18000CA9C
0x18000ca86  mov     r9d, eax; unsigned int
0x18000ca89  mov     edx, ecx; unsigned int
0x18000ca8b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000ca92  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000ca97  jmp     loc_18000CB2B
0x18000ca9c  test    eax, eax
0x18000ca9e  jnz     short loc_18000CB1A
0x18000caa0  cmp     r8d, 0FEh
0x18000caa7  jz      short loc_18000CB1A
0x18000caa9  mov     [rsp+38h+var_18], 0
0x18000cab2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000cab6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000cabc  test    edx, edx
0x18000cabe  jns     short loc_18000CAC6
0x18000cac0  or      word ptr [rsp+38h+var_18+6], 1
0x18000cac6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000cacd  test    rax, rax
0x18000cad0  jnz     short loc_18000CB0E
0x18000cad2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cad9  test    rax, rax
0x18000cadc  jnz     short loc_18000CAF2
0x18000cade  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000cae5  call    cs:__imp_GetModuleHandleW
0x18000caeb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000caf2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000caf9  mov     rcx, rax; hModule
0x18000cafc  call    cs:__imp_GetProcAddress
0x18000cb02  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000cb09  test    rax, rax
0x18000cb0c  jz      short loc_18000CB2B
0x18000cb0e  lea     rcx, [rsp+38h+var_18]
0x18000cb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb18  jmp     short loc_18000CB2B
0x18000cb1a  mov     r9, rax
0x18000cb1d  mov     edx, ecx
0x18000cb1f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000cb26  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000cb2b  add     rsp, 38h
0x18000cb2f  retn
```
