# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000f6f0`
- end: `0x14000f810`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400083cc`
- `0x14000a84c`
- `0x14000ab34`
- `0x14000b304`
- `0x14000b4c0`
- `0x14000f6f0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f7dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f7dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f7c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f7c5`

## string_xrefs

- `0x14000f7be`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_14001A088[25], qword_14001A088);
    wil::details_abi::FeatureStateData::RecordUsage(qword_14001A088);
  }
}

```

## disassembly

```asm
0x14000f6f0  sub     rsp, 38h
0x14000f6f4  mov     eax, r8d
0x14000f6f7  mov     r8d, edx
0x14000f6fa  btr     r8d, 1Fh; unsigned __int16
0x14000f6ff  test    ecx, ecx
0x14000f701  jnz     short loc_14000F75F
0x14000f703  test    eax, eax
0x14000f705  jnz     short loc_14000F75F
0x14000f707  test    r8d, r8d
0x14000f70a  jnz     short loc_14000F75F
0x14000f70c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000f713  jnz     short loc_14000F75A
0x14000f715  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000f71c  test    rax, rax
0x14000f71f  jz      short loc_14000F72A
0x14000f721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f726  test    al, al
0x14000f728  jnz     short loc_14000F75A
0x14000f72a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000f731  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000f736  test    al, al
0x14000f738  jz      short loc_14000F75A
0x14000f73a  mov     rdx, cs:qword_14001A088; SRWLock
0x14000f741  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000f748  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000f74d  mov     rcx, cs:qword_14001A088; SRWLock
0x14000f754  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000f759  nop
0x14000f75a  jmp     loc_14000F80B
0x14000f75f  bt      r8d, 1Eh
0x14000f764  jnb     short loc_14000F77C
0x14000f766  mov     r9d, eax; unsigned int
0x14000f769  mov     edx, ecx; unsigned int
0x14000f76b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000f772  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000f777  jmp     loc_14000F80B
0x14000f77c  test    eax, eax
0x14000f77e  jnz     short loc_14000F7FA
0x14000f780  cmp     r8d, 0FEh
0x14000f787  jz      short loc_14000F7FA
0x14000f789  mov     [rsp+38h+var_18], 0
0x14000f792  mov     dword ptr [rsp+38h+var_18], ecx
0x14000f796  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000f79c  test    edx, edx
0x14000f79e  jns     short loc_14000F7A6
0x14000f7a0  or      word ptr [rsp+38h+var_18+6], 1
0x14000f7a6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000f7ad  test    rax, rax
0x14000f7b0  jnz     short loc_14000F7EE
0x14000f7b2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f7b9  test    rax, rax
0x14000f7bc  jnz     short loc_14000F7D2
0x14000f7be  lea     rcx, ModuleName; "ntdll.dll"
0x14000f7c5  call    cs:__imp_GetModuleHandleW
0x14000f7cb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f7d2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000f7d9  mov     rcx, rax; hModule
0x14000f7dc  call    cs:__imp_GetProcAddress
0x14000f7e2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000f7e9  test    rax, rax
0x14000f7ec  jz      short loc_14000F80B
0x14000f7ee  lea     rcx, [rsp+38h+var_18]
0x14000f7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7f8  jmp     short loc_14000F80B
0x14000f7fa  mov     r9, rax
0x14000f7fd  mov     edx, ecx
0x14000f7ff  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000f806  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000f80b  add     rsp, 38h
0x14000f80f  retn
```
