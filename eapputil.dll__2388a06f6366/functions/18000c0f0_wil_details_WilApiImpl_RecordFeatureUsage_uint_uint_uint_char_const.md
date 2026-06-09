# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000c0f0`
- end: `0x18000c210`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180009d58`
- `0x18000a4b8`
- `0x18000a618`
- `0x18000accc`
- `0x18000ae90`
- `0x18000c0f0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c1c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c1c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1dc`

## string_xrefs

- `0x18000c1be`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180043378[25], qword_180043378);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180043378);
  }
}

```

## disassembly

```asm
0x18000c0f0  sub     rsp, 38h
0x18000c0f4  mov     eax, r8d
0x18000c0f7  mov     r8d, edx
0x18000c0fa  btr     r8d, 1Fh; unsigned __int16
0x18000c0ff  test    ecx, ecx
0x18000c101  jnz     short loc_18000C15F
0x18000c103  test    eax, eax
0x18000c105  jnz     short loc_18000C15F
0x18000c107  test    r8d, r8d
0x18000c10a  jnz     short loc_18000C15F
0x18000c10c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000c113  jnz     short loc_18000C15A
0x18000c115  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c11c  test    rax, rax
0x18000c11f  jz      short loc_18000C12A
0x18000c121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c126  test    al, al
0x18000c128  jnz     short loc_18000C15A
0x18000c12a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c131  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000c136  test    al, al
0x18000c138  jz      short loc_18000C15A
0x18000c13a  mov     rdx, cs:qword_180043378; SRWLock
0x18000c141  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000c148  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000c14d  mov     rcx, cs:qword_180043378; SRWLock
0x18000c154  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c159  nop
0x18000c15a  jmp     loc_18000C20B
0x18000c15f  bt      r8d, 1Eh
0x18000c164  jnb     short loc_18000C17C
0x18000c166  mov     r9d, eax; unsigned int
0x18000c169  mov     edx, ecx; unsigned int
0x18000c16b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000c172  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000c177  jmp     loc_18000C20B
0x18000c17c  test    eax, eax
0x18000c17e  jnz     short loc_18000C1FA
0x18000c180  cmp     r8d, 0FEh
0x18000c187  jz      short loc_18000C1FA
0x18000c189  mov     [rsp+38h+var_18], 0
0x18000c192  mov     dword ptr [rsp+38h+var_18], ecx
0x18000c196  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000c19c  test    edx, edx
0x18000c19e  jns     short loc_18000C1A6
0x18000c1a0  or      word ptr [rsp+38h+var_18+6], 1
0x18000c1a6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c1ad  test    rax, rax
0x18000c1b0  jnz     short loc_18000C1EE
0x18000c1b2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c1b9  test    rax, rax
0x18000c1bc  jnz     short loc_18000C1D2
0x18000c1be  lea     rcx, ModuleName; "ntdll.dll"
0x18000c1c5  call    cs:__imp_GetModuleHandleW
0x18000c1cb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c1d2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c1d9  mov     rcx, rax; hModule
0x18000c1dc  call    cs:__imp_GetProcAddress
0x18000c1e2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c1e9  test    rax, rax
0x18000c1ec  jz      short loc_18000C20B
0x18000c1ee  lea     rcx, [rsp+38h+var_18]
0x18000c1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1f8  jmp     short loc_18000C20B
0x18000c1fa  mov     r9, rax
0x18000c1fd  mov     edx, ecx
0x18000c1ff  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c206  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000c20b  add     rsp, 38h
0x18000c20f  retn
```
