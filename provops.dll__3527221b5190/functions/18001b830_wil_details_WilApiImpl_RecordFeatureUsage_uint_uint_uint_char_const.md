# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18001b830`
- end: `0x18001b950`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800123f8`
- `0x180013dd8`
- `0x180014b0c`
- `0x1800151f4`
- `0x1800153b0`
- `0x18001b830`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b905`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b905`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b91c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b91c`

## string_xrefs

- `0x18001b8fe`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18004A0C8[25], qword_18004A0C8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18004A0C8);
  }
}

```

## disassembly

```asm
0x18001b830  sub     rsp, 38h
0x18001b834  mov     eax, r8d
0x18001b837  mov     r8d, edx
0x18001b83a  btr     r8d, 1Fh; unsigned __int16
0x18001b83f  test    ecx, ecx
0x18001b841  jnz     short loc_18001B89F
0x18001b843  test    eax, eax
0x18001b845  jnz     short loc_18001B89F
0x18001b847  test    r8d, r8d
0x18001b84a  jnz     short loc_18001B89F
0x18001b84c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18001b853  jnz     short loc_18001B89A
0x18001b855  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001b85c  test    rax, rax
0x18001b85f  jz      short loc_18001B86A
0x18001b861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b866  test    al, al
0x18001b868  jnz     short loc_18001B89A
0x18001b86a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001b871  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001b876  test    al, al
0x18001b878  jz      short loc_18001B89A
0x18001b87a  mov     rdx, cs:qword_18004A0C8; SRWLock
0x18001b881  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001b888  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001b88d  mov     rcx, cs:qword_18004A0C8; SRWLock
0x18001b894  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001b899  nop
0x18001b89a  jmp     loc_18001B94B
0x18001b89f  bt      r8d, 1Eh
0x18001b8a4  jnb     short loc_18001B8BC
0x18001b8a6  mov     r9d, eax; unsigned int
0x18001b8a9  mov     edx, ecx; unsigned int
0x18001b8ab  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001b8b2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18001b8b7  jmp     loc_18001B94B
0x18001b8bc  test    eax, eax
0x18001b8be  jnz     short loc_18001B93A
0x18001b8c0  cmp     r8d, 0FEh
0x18001b8c7  jz      short loc_18001B93A
0x18001b8c9  mov     [rsp+38h+var_18], 0
0x18001b8d2  mov     dword ptr [rsp+38h+var_18], ecx
0x18001b8d6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18001b8dc  test    edx, edx
0x18001b8de  jns     short loc_18001B8E6
0x18001b8e0  or      word ptr [rsp+38h+var_18+6], 1
0x18001b8e6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001b8ed  test    rax, rax
0x18001b8f0  jnz     short loc_18001B92E
0x18001b8f2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001b8f9  test    rax, rax
0x18001b8fc  jnz     short loc_18001B912
0x18001b8fe  lea     rcx, ModuleName; "ntdll.dll"
0x18001b905  call    cs:__imp_GetModuleHandleW
0x18001b90b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001b912  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001b919  mov     rcx, rax; hModule
0x18001b91c  call    cs:__imp_GetProcAddress
0x18001b922  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001b929  test    rax, rax
0x18001b92c  jz      short loc_18001B94B
0x18001b92e  lea     rcx, [rsp+38h+var_18]
0x18001b933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b938  jmp     short loc_18001B94B
0x18001b93a  mov     r9, rax
0x18001b93d  mov     edx, ecx
0x18001b93f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001b946  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001b94b  add     rsp, 38h
0x18001b94f  retn
```
