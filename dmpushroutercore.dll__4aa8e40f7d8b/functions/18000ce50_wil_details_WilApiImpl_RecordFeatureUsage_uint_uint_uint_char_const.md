# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000ce50`
- end: `0x18000cf70`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800089a4`
- `0x18000a1f4`
- `0x18000a484`
- `0x18000aa74`
- `0x18000ac70`
- `0x18000ce50`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cf25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cf25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cf3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cf3c`

## string_xrefs

- `0x18000cf1e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800502C8[25], qword_1800502C8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800502C8);
  }
}

```

## disassembly

```asm
0x18000ce50  sub     rsp, 38h
0x18000ce54  mov     eax, r8d
0x18000ce57  mov     r8d, edx
0x18000ce5a  btr     r8d, 1Fh; unsigned __int16
0x18000ce5f  test    ecx, ecx
0x18000ce61  jnz     short loc_18000CEBF
0x18000ce63  test    eax, eax
0x18000ce65  jnz     short loc_18000CEBF
0x18000ce67  test    r8d, r8d
0x18000ce6a  jnz     short loc_18000CEBF
0x18000ce6c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000ce73  jnz     short loc_18000CEBA
0x18000ce75  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ce7c  test    rax, rax
0x18000ce7f  jz      short loc_18000CE8A
0x18000ce81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce86  test    al, al
0x18000ce88  jnz     short loc_18000CEBA
0x18000ce8a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000ce91  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000ce96  test    al, al
0x18000ce98  jz      short loc_18000CEBA
0x18000ce9a  mov     rdx, cs:qword_1800502C8; SRWLock
0x18000cea1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000cea8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000cead  mov     rcx, cs:qword_1800502C8; SRWLock
0x18000ceb4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ceb9  nop
0x18000ceba  jmp     loc_18000CF6B
0x18000cebf  bt      r8d, 1Eh
0x18000cec4  jnb     short loc_18000CEDC
0x18000cec6  mov     r9d, eax; unsigned int
0x18000cec9  mov     edx, ecx; unsigned int
0x18000cecb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000ced2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000ced7  jmp     loc_18000CF6B
0x18000cedc  test    eax, eax
0x18000cede  jnz     short loc_18000CF5A
0x18000cee0  cmp     r8d, 0FEh
0x18000cee7  jz      short loc_18000CF5A
0x18000cee9  mov     [rsp+38h+var_18], 0
0x18000cef2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000cef6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000cefc  test    edx, edx
0x18000cefe  jns     short loc_18000CF06
0x18000cf00  or      word ptr [rsp+38h+var_18+6], 1
0x18000cf06  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000cf0d  test    rax, rax
0x18000cf10  jnz     short loc_18000CF4E
0x18000cf12  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cf19  test    rax, rax
0x18000cf1c  jnz     short loc_18000CF32
0x18000cf1e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000cf25  call    cs:__imp_GetModuleHandleW
0x18000cf2b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cf32  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000cf39  mov     rcx, rax; hModule
0x18000cf3c  call    cs:__imp_GetProcAddress
0x18000cf42  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000cf49  test    rax, rax
0x18000cf4c  jz      short loc_18000CF6B
0x18000cf4e  lea     rcx, [rsp+38h+var_18]
0x18000cf53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf58  jmp     short loc_18000CF6B
0x18000cf5a  mov     r9, rax
0x18000cf5d  mov     edx, ecx
0x18000cf5f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000cf66  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000cf6b  add     rsp, 38h
0x18000cf6f  retn
```
