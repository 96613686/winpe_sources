# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000f7e0`
- end: `0x18000f900`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180009bf4`
- `0x18000ab7c`
- `0x18000acdc`
- `0x18000b40c`
- `0x18000b5d0`
- `0x18000f7e0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f8b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f8b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f8cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f8cc`

## string_xrefs

- `0x18000f8ae`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18003F060[25], qword_18003F060);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18003F060);
  }
}

```

## disassembly

```asm
0x18000f7e0  sub     rsp, 38h
0x18000f7e4  mov     eax, r8d
0x18000f7e7  mov     r8d, edx
0x18000f7ea  btr     r8d, 1Fh; unsigned __int16
0x18000f7ef  test    ecx, ecx
0x18000f7f1  jnz     short loc_18000F84F
0x18000f7f3  test    eax, eax
0x18000f7f5  jnz     short loc_18000F84F
0x18000f7f7  test    r8d, r8d
0x18000f7fa  jnz     short loc_18000F84F
0x18000f7fc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000f803  jnz     short loc_18000F84A
0x18000f805  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f80c  test    rax, rax
0x18000f80f  jz      short loc_18000F81A
0x18000f811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f816  test    al, al
0x18000f818  jnz     short loc_18000F84A
0x18000f81a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000f821  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000f826  test    al, al
0x18000f828  jz      short loc_18000F84A
0x18000f82a  mov     rdx, cs:qword_18003F060; SRWLock
0x18000f831  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000f838  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000f83d  mov     rcx, cs:qword_18003F060; SRWLock
0x18000f844  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000f849  nop
0x18000f84a  jmp     loc_18000F8FB
0x18000f84f  bt      r8d, 1Eh
0x18000f854  jnb     short loc_18000F86C
0x18000f856  mov     r9d, eax; unsigned int
0x18000f859  mov     edx, ecx; unsigned int
0x18000f85b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000f862  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000f867  jmp     loc_18000F8FB
0x18000f86c  test    eax, eax
0x18000f86e  jnz     short loc_18000F8EA
0x18000f870  cmp     r8d, 0FEh
0x18000f877  jz      short loc_18000F8EA
0x18000f879  mov     [rsp+38h+var_18], 0
0x18000f882  mov     dword ptr [rsp+38h+var_18], ecx
0x18000f886  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000f88c  test    edx, edx
0x18000f88e  jns     short loc_18000F896
0x18000f890  or      word ptr [rsp+38h+var_18+6], 1
0x18000f896  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000f89d  test    rax, rax
0x18000f8a0  jnz     short loc_18000F8DE
0x18000f8a2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f8a9  test    rax, rax
0x18000f8ac  jnz     short loc_18000F8C2
0x18000f8ae  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000f8b5  call    cs:__imp_GetModuleHandleW
0x18000f8bb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f8c2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000f8c9  mov     rcx, rax; hModule
0x18000f8cc  call    cs:__imp_GetProcAddress
0x18000f8d2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000f8d9  test    rax, rax
0x18000f8dc  jz      short loc_18000F8FB
0x18000f8de  lea     rcx, [rsp+38h+var_18]
0x18000f8e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8e8  jmp     short loc_18000F8FB
0x18000f8ea  mov     r9, rax
0x18000f8ed  mov     edx, ecx
0x18000f8ef  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000f8f6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000f8fb  add     rsp, 38h
0x18000f8ff  retn
```
