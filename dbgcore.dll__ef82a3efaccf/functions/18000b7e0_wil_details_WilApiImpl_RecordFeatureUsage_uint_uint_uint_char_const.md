# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000b7e0`
- end: `0x18000b909`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `297`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000657c`
- `0x180008ac8`
- `0x180008cd0`
- `0x1800090c4`
- `0x180009288`
- `0x18000b7e0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b8d5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b8d5`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b8be`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b8be`

## string_xrefs

- `0x18000b8b7`: `ntdll.dll`

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
  __int64 v9; // [rsp+28h] [rbp-10h]

  v9 = -2;
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
         && (!wil::details::g_pfnDllShutdownInProgress
          || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this))
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18003C078[25], qword_18003C078);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18003C078);
  }
}

```

## disassembly

```asm
0x18000b7e0  sub     rsp, 38h
0x18000b7e4  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFEh
0x18000b7ed  mov     eax, r8d
0x18000b7f0  mov     r8d, edx
0x18000b7f3  btr     r8d, 1Fh; unsigned __int16
0x18000b7f8  test    ecx, ecx
0x18000b7fa  jnz     short loc_18000B858
0x18000b7fc  test    eax, eax
0x18000b7fe  jnz     short loc_18000B858
0x18000b800  test    r8d, r8d
0x18000b803  jnz     short loc_18000B858
0x18000b805  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000b80c  jnz     short loc_18000B853
0x18000b80e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b815  test    rax, rax
0x18000b818  jz      short loc_18000B823
0x18000b81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b81f  test    al, al
0x18000b821  jnz     short loc_18000B853
0x18000b823  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b82a  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b82f  test    al, al
0x18000b831  jz      short loc_18000B853
0x18000b833  mov     rdx, cs:qword_18003C078; SRWLock
0x18000b83a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000b841  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000b846  mov     rcx, cs:qword_18003C078; SRWLock
0x18000b84d  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b852  nop
0x18000b853  jmp     loc_18000B904
0x18000b858  bt      r8d, 1Eh
0x18000b85d  jnb     short loc_18000B875
0x18000b85f  mov     r9d, eax; unsigned int
0x18000b862  mov     edx, ecx; unsigned int
0x18000b864  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000b86b  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000b870  jmp     loc_18000B904
0x18000b875  test    eax, eax
0x18000b877  jnz     short loc_18000B8F3
0x18000b879  cmp     r8d, 0FEh
0x18000b880  jz      short loc_18000B8F3
0x18000b882  mov     [rsp+38h+var_18], 0
0x18000b88b  mov     dword ptr [rsp+38h+var_18], ecx
0x18000b88f  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000b895  test    edx, edx
0x18000b897  jns     short loc_18000B89F
0x18000b899  or      word ptr [rsp+38h+var_18+6], 1
0x18000b89f  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b8a6  test    rax, rax
0x18000b8a9  jnz     short loc_18000B8E7
0x18000b8ab  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b8b2  test    rax, rax
0x18000b8b5  jnz     short loc_18000B8CB
0x18000b8b7  lea     rcx, ModuleName; "ntdll.dll"
0x18000b8be  call    cs:__imp_GetModuleHandleW
0x18000b8c4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b8cb  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b8d2  mov     rcx, rax; hModule
0x18000b8d5  call    cs:__imp_GetProcAddress
0x18000b8db  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b8e2  test    rax, rax
0x18000b8e5  jz      short loc_18000B904
0x18000b8e7  lea     rcx, [rsp+38h+var_18]
0x18000b8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f1  jmp     short loc_18000B904
0x18000b8f3  mov     r9, rax
0x18000b8f6  mov     edx, ecx
0x18000b8f8  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b8ff  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000b904  add     rsp, 38h
0x18000b908  retn
```
