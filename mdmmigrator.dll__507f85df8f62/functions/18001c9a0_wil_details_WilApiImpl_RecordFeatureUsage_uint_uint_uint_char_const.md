# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18001c9a0`
- end: `0x18001cacb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800170f4`
- `0x180017ad0`
- `0x180017b94`
- `0x180017f40`
- `0x1800180c0`
- `0x18001c9a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ca80`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ca80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ca97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ca97`

## string_xrefs

- `0x18001ca79`: `ntdll.dll`

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
        goto LABEL_19;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_19:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18002B198[25], qword_18002B198);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18002B198);
  }
}

```

## disassembly

```asm
0x18001c9a0  sub     rsp, 38h
0x18001c9a4  mov     eax, r8d
0x18001c9a7  mov     r8d, edx
0x18001c9aa  btr     r8d, 1Fh; unsigned __int16
0x18001c9af  test    ecx, ecx
0x18001c9b1  jnz     short loc_18001CA1A
0x18001c9b3  test    eax, eax
0x18001c9b5  jnz     short loc_18001CA1A
0x18001c9b7  test    r8d, r8d
0x18001c9ba  jnz     short loc_18001CA1A
0x18001c9bc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18001c9c3  jnz     loc_18001CAC6
0x18001c9c9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c9d0  test    rax, rax
0x18001c9d3  jz      short loc_18001C9E2
0x18001c9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9da  test    al, al
0x18001c9dc  jnz     loc_18001CAC6
0x18001c9e2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001c9e9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001c9ee  test    al, al
0x18001c9f0  jz      loc_18001CAC6
0x18001c9f6  mov     rdx, cs:qword_18002B198; SRWLock
0x18001c9fd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001ca04  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001ca09  mov     rcx, cs:qword_18002B198; SRWLock
0x18001ca10  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001ca15  jmp     loc_18001CAC6
0x18001ca1a  bt      r8d, 1Eh
0x18001ca1f  jnb     short loc_18001CA37
0x18001ca21  mov     edx, ecx; unsigned int
0x18001ca23  mov     r9d, eax; unsigned int
0x18001ca26  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001ca2d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18001ca32  jmp     loc_18001CAC6
0x18001ca37  test    eax, eax
0x18001ca39  jnz     short loc_18001CAB5
0x18001ca3b  cmp     r8d, 0FEh
0x18001ca42  jz      short loc_18001CAB5
0x18001ca44  mov     [rsp+38h+var_18], 0
0x18001ca4d  mov     dword ptr [rsp+38h+var_18], ecx
0x18001ca51  mov     word ptr [rsp+38h+var_18+4], r8w
0x18001ca57  test    edx, edx
0x18001ca59  jns     short loc_18001CA61
0x18001ca5b  or      word ptr [rsp+38h+var_18+6], 1
0x18001ca61  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001ca68  test    rax, rax
0x18001ca6b  jnz     short loc_18001CAA9
0x18001ca6d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ca74  test    rax, rax
0x18001ca77  jnz     short loc_18001CA8D
0x18001ca79  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001ca80  call    cs:__imp_GetModuleHandleW
0x18001ca86  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ca8d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001ca94  mov     rcx, rax; hModule
0x18001ca97  call    cs:__imp_GetProcAddress
0x18001ca9d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001caa4  test    rax, rax
0x18001caa7  jz      short loc_18001CAC6
0x18001caa9  lea     rcx, [rsp+38h+var_18]
0x18001caae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cab3  jmp     short loc_18001CAC6
0x18001cab5  mov     edx, ecx
0x18001cab7  mov     r9, rax
0x18001caba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001cac1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001cac6  add     rsp, 38h
0x18001caca  retn
```
