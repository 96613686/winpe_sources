# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140007ed0`
- end: `0x140007ff0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140004484`
- `0x140005774`
- `0x1400058dc`
- `0x140005cf4`
- `0x140005eb0`
- `0x140007ed0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007fa5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007fa5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007fbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007fbc`

## string_xrefs

- `0x140007f9e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400290B8[25], qword_1400290B8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400290B8);
  }
}

```

## disassembly

```asm
0x140007ed0  sub     rsp, 38h
0x140007ed4  mov     eax, r8d
0x140007ed7  mov     r8d, edx
0x140007eda  btr     r8d, 1Fh; unsigned __int16
0x140007edf  test    ecx, ecx
0x140007ee1  jnz     short loc_140007F3F
0x140007ee3  test    eax, eax
0x140007ee5  jnz     short loc_140007F3F
0x140007ee7  test    r8d, r8d
0x140007eea  jnz     short loc_140007F3F
0x140007eec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140007ef3  jnz     short loc_140007F3A
0x140007ef5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140007efc  test    rax, rax
0x140007eff  jz      short loc_140007F0A
0x140007f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f06  test    al, al
0x140007f08  jnz     short loc_140007F3A
0x140007f0a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140007f11  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140007f16  test    al, al
0x140007f18  jz      short loc_140007F3A
0x140007f1a  mov     rdx, cs:qword_1400290B8; SRWLock
0x140007f21  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140007f28  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x140007f2d  mov     rcx, cs:qword_1400290B8; SRWLock
0x140007f34  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140007f39  nop
0x140007f3a  jmp     loc_140007FEB
0x140007f3f  bt      r8d, 1Eh
0x140007f44  jnb     short loc_140007F5C
0x140007f46  mov     r9d, eax; unsigned int
0x140007f49  mov     edx, ecx; unsigned int
0x140007f4b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140007f52  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140007f57  jmp     loc_140007FEB
0x140007f5c  test    eax, eax
0x140007f5e  jnz     short loc_140007FDA
0x140007f60  cmp     r8d, 0FEh
0x140007f67  jz      short loc_140007FDA
0x140007f69  mov     [rsp+38h+var_18], 0
0x140007f72  mov     dword ptr [rsp+38h+var_18], ecx
0x140007f76  mov     word ptr [rsp+38h+var_18+4], r8w
0x140007f7c  test    edx, edx
0x140007f7e  jns     short loc_140007F86
0x140007f80  or      word ptr [rsp+38h+var_18+6], 1
0x140007f86  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140007f8d  test    rax, rax
0x140007f90  jnz     short loc_140007FCE
0x140007f92  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007f99  test    rax, rax
0x140007f9c  jnz     short loc_140007FB2
0x140007f9e  lea     rcx, ModuleName; "ntdll.dll"
0x140007fa5  call    cs:__imp_GetModuleHandleW
0x140007fab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007fb2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140007fb9  mov     rcx, rax; hModule
0x140007fbc  call    cs:__imp_GetProcAddress
0x140007fc2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140007fc9  test    rax, rax
0x140007fcc  jz      short loc_140007FEB
0x140007fce  lea     rcx, [rsp+38h+var_18]
0x140007fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fd8  jmp     short loc_140007FEB
0x140007fda  mov     r9, rax
0x140007fdd  mov     edx, ecx
0x140007fdf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140007fe6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140007feb  add     rsp, 38h
0x140007fef  retn
```
