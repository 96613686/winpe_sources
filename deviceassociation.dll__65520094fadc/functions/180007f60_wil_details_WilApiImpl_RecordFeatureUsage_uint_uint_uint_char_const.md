# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180007f60`
- end: `0x18000808b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004b54`
- `0x180006134`
- `0x18000629c`
- `0x180006664`
- `0x18000681c`
- `0x180007f60`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008057`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008057`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008040`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008040`

## string_xrefs

- `0x180008039`: `ntdll.dll`

## pseudocode

```c
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
        goto LABEL_19;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180015038[25], qword_180015038);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180015038);
  }
}

```

## disassembly

```asm
0x180007f60  sub     rsp, 38h
0x180007f64  mov     eax, r8d
0x180007f67  mov     r8d, edx
0x180007f6a  btr     r8d, 1Fh; unsigned __int16
0x180007f6f  test    ecx, ecx
0x180007f71  jnz     short loc_180007FDA
0x180007f73  test    eax, eax
0x180007f75  jnz     short loc_180007FDA
0x180007f77  test    r8d, r8d
0x180007f7a  jnz     short loc_180007FDA
0x180007f7c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180007f83  jnz     loc_180008086
0x180007f89  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007f90  test    rax, rax
0x180007f93  jz      short loc_180007FA2
0x180007f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f9a  test    al, al
0x180007f9c  jnz     loc_180008086
0x180007fa2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007fa9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007fae  test    al, al
0x180007fb0  jz      loc_180008086
0x180007fb6  mov     rdx, cs:qword_180015038; SRWLock
0x180007fbd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007fc4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180007fc9  mov     rcx, cs:qword_180015038; SRWLock
0x180007fd0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007fd5  jmp     loc_180008086
0x180007fda  bt      r8d, 1Eh
0x180007fdf  jnb     short loc_180007FF7
0x180007fe1  mov     edx, ecx; unsigned int
0x180007fe3  mov     r9d, eax; unsigned int
0x180007fe6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180007fed  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180007ff2  jmp     loc_180008086
0x180007ff7  test    eax, eax
0x180007ff9  jnz     short loc_180008075
0x180007ffb  cmp     r8d, 0FEh
0x180008002  jz      short loc_180008075
0x180008004  mov     [rsp+38h+var_18], 0
0x18000800d  mov     dword ptr [rsp+38h+var_18], ecx
0x180008011  mov     word ptr [rsp+38h+var_18+4], r8w
0x180008017  test    edx, edx
0x180008019  jns     short loc_180008021
0x18000801b  or      word ptr [rsp+38h+var_18+6], 1
0x180008021  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180008028  test    rax, rax
0x18000802b  jnz     short loc_180008069
0x18000802d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008034  test    rax, rax
0x180008037  jnz     short loc_18000804D
0x180008039  lea     rcx, ModuleName; "ntdll.dll"
0x180008040  call    cs:__imp_GetModuleHandleW
0x180008046  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000804d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008054  mov     rcx, rax; hModule
0x180008057  call    cs:__imp_GetProcAddress
0x18000805d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008064  test    rax, rax
0x180008067  jz      short loc_180008086
0x180008069  lea     rcx, [rsp+38h+var_18]
0x18000806e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008073  jmp     short loc_180008086
0x180008075  mov     edx, ecx
0x180008077  mov     r9, rax
0x18000807a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008081  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180008086  add     rsp, 38h
0x18000808a  retn
```
