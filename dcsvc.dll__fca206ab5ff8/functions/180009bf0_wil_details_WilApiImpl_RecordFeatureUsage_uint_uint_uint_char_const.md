# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009bf0`
- end: `0x180009d10`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004ee4`
- `0x1800067f4`
- `0x1800069f8`
- `0x180006fa4`
- `0x1800071a0`
- `0x180009bf0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009cdc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009cdc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009cc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009cc5`

## string_xrefs

- `0x180009cbe`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001B148[25], qword_18001B148);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001B148);
  }
}

```

## disassembly

```asm
0x180009bf0  sub     rsp, 38h
0x180009bf4  mov     eax, r8d
0x180009bf7  mov     r8d, edx
0x180009bfa  btr     r8d, 1Fh; unsigned __int16
0x180009bff  test    ecx, ecx
0x180009c01  jnz     short loc_180009C5F
0x180009c03  test    eax, eax
0x180009c05  jnz     short loc_180009C5F
0x180009c07  test    r8d, r8d
0x180009c0a  jnz     short loc_180009C5F
0x180009c0c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180009c13  jnz     short loc_180009C5A
0x180009c15  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009c1c  test    rax, rax
0x180009c1f  jz      short loc_180009C2A
0x180009c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c26  test    al, al
0x180009c28  jnz     short loc_180009C5A
0x180009c2a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009c31  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009c36  test    al, al
0x180009c38  jz      short loc_180009C5A
0x180009c3a  mov     rdx, cs:qword_18001B148; SRWLock
0x180009c41  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009c48  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180009c4d  mov     rcx, cs:qword_18001B148; SRWLock
0x180009c54  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009c59  nop
0x180009c5a  jmp     loc_180009D0B
0x180009c5f  bt      r8d, 1Eh
0x180009c64  jnb     short loc_180009C7C
0x180009c66  mov     r9d, eax; unsigned int
0x180009c69  mov     edx, ecx; unsigned int
0x180009c6b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009c72  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009c77  jmp     loc_180009D0B
0x180009c7c  test    eax, eax
0x180009c7e  jnz     short loc_180009CFA
0x180009c80  cmp     r8d, 0FEh
0x180009c87  jz      short loc_180009CFA
0x180009c89  mov     [rsp+38h+var_18], 0
0x180009c92  mov     dword ptr [rsp+38h+var_18], ecx
0x180009c96  mov     word ptr [rsp+38h+var_18+4], r8w
0x180009c9c  test    edx, edx
0x180009c9e  jns     short loc_180009CA6
0x180009ca0  or      word ptr [rsp+38h+var_18+6], 1
0x180009ca6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180009cad  test    rax, rax
0x180009cb0  jnz     short loc_180009CEE
0x180009cb2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009cb9  test    rax, rax
0x180009cbc  jnz     short loc_180009CD2
0x180009cbe  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009cc5  call    cs:__imp_GetModuleHandleW
0x180009ccb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009cd2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009cd9  mov     rcx, rax; hModule
0x180009cdc  call    cs:__imp_GetProcAddress
0x180009ce2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009ce9  test    rax, rax
0x180009cec  jz      short loc_180009D0B
0x180009cee  lea     rcx, [rsp+38h+var_18]
0x180009cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cf8  jmp     short loc_180009D0B
0x180009cfa  mov     r9, rax
0x180009cfd  mov     edx, ecx
0x180009cff  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009d06  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180009d0b  add     rsp, 38h
0x180009d0f  retn
```
