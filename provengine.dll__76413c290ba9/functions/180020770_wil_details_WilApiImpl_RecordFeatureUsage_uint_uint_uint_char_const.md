# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180020770`
- end: `0x180020890`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180013544`
- `0x180017fa4`
- `0x18001b478`
- `0x18001baa4`
- `0x18001bc28`
- `0x180020770`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002085c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002085c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020845`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020845`

## string_xrefs

- `0x18002083e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18005A198[25], qword_18005A198);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18005A198);
  }
}

```

## disassembly

```asm
0x180020770  sub     rsp, 38h
0x180020774  mov     eax, r8d
0x180020777  mov     r8d, edx
0x18002077a  btr     r8d, 1Fh; unsigned __int16
0x18002077f  test    ecx, ecx
0x180020781  jnz     short loc_1800207DF
0x180020783  test    eax, eax
0x180020785  jnz     short loc_1800207DF
0x180020787  test    r8d, r8d
0x18002078a  jnz     short loc_1800207DF
0x18002078c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180020793  jnz     short loc_1800207DA
0x180020795  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002079c  test    rax, rax
0x18002079f  jz      short loc_1800207AA
0x1800207a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207a6  test    al, al
0x1800207a8  jnz     short loc_1800207DA
0x1800207aa  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800207b1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800207b6  test    al, al
0x1800207b8  jz      short loc_1800207DA
0x1800207ba  mov     rdx, cs:qword_18005A198; SRWLock
0x1800207c1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800207c8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800207cd  mov     rcx, cs:qword_18005A198; SRWLock
0x1800207d4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800207d9  nop
0x1800207da  jmp     loc_18002088B
0x1800207df  bt      r8d, 1Eh
0x1800207e4  jnb     short loc_1800207FC
0x1800207e6  mov     r9d, eax; unsigned int
0x1800207e9  mov     edx, ecx; unsigned int
0x1800207eb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800207f2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800207f7  jmp     loc_18002088B
0x1800207fc  test    eax, eax
0x1800207fe  jnz     short loc_18002087A
0x180020800  cmp     r8d, 0FEh
0x180020807  jz      short loc_18002087A
0x180020809  mov     [rsp+38h+var_18], 0
0x180020812  mov     dword ptr [rsp+38h+var_18], ecx
0x180020816  mov     word ptr [rsp+38h+var_18+4], r8w
0x18002081c  test    edx, edx
0x18002081e  jns     short loc_180020826
0x180020820  or      word ptr [rsp+38h+var_18+6], 1
0x180020826  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18002082d  test    rax, rax
0x180020830  jnz     short loc_18002086E
0x180020832  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180020839  test    rax, rax
0x18002083c  jnz     short loc_180020852
0x18002083e  lea     rcx, ModuleName; "ntdll.dll"
0x180020845  call    cs:__imp_GetModuleHandleW
0x18002084b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180020852  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180020859  mov     rcx, rax; hModule
0x18002085c  call    cs:__imp_GetProcAddress
0x180020862  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180020869  test    rax, rax
0x18002086c  jz      short loc_18002088B
0x18002086e  lea     rcx, [rsp+38h+var_18]
0x180020873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020878  jmp     short loc_18002088B
0x18002087a  mov     r9, rax
0x18002087d  mov     edx, ecx
0x18002087f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180020886  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18002088b  add     rsp, 38h
0x18002088f  retn
```
