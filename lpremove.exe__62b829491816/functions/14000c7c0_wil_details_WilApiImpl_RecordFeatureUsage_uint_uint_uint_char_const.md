# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000c7c0`
- end: `0x14000c8e0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140006b78`
- `0x140008fbc`
- `0x140009124`
- `0x1400095d4`
- `0x140009790`
- `0x14000c7c0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000c895`
- `KERNEL32!GetModuleHandleW` at `0x14000c895`
- `KERNEL32!GetProcAddress` at `0x14000c8ac`
- `KERNEL32!GetProcAddress` at `0x14000c8ac`

## string_xrefs

- `0x14000c88e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400180B0[25], qword_1400180B0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400180B0);
  }
}

```

## disassembly

```asm
0x14000c7c0  sub     rsp, 38h
0x14000c7c4  mov     eax, r8d
0x14000c7c7  mov     r8d, edx
0x14000c7ca  btr     r8d, 1Fh; unsigned __int16
0x14000c7cf  test    ecx, ecx
0x14000c7d1  jnz     short loc_14000C82F
0x14000c7d3  test    eax, eax
0x14000c7d5  jnz     short loc_14000C82F
0x14000c7d7  test    r8d, r8d
0x14000c7da  jnz     short loc_14000C82F
0x14000c7dc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000c7e3  jnz     short loc_14000C82A
0x14000c7e5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000c7ec  test    rax, rax
0x14000c7ef  jz      short loc_14000C7FA
0x14000c7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7f6  test    al, al
0x14000c7f8  jnz     short loc_14000C82A
0x14000c7fa  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000c801  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000c806  test    al, al
0x14000c808  jz      short loc_14000C82A
0x14000c80a  mov     rdx, cs:qword_1400180B0; SRWLock
0x14000c811  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000c818  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000c81d  mov     rcx, cs:qword_1400180B0; SRWLock
0x14000c824  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000c829  nop
0x14000c82a  jmp     loc_14000C8DB
0x14000c82f  bt      r8d, 1Eh
0x14000c834  jnb     short loc_14000C84C
0x14000c836  mov     r9d, eax; unsigned int
0x14000c839  mov     edx, ecx; unsigned int
0x14000c83b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000c842  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000c847  jmp     loc_14000C8DB
0x14000c84c  test    eax, eax
0x14000c84e  jnz     short loc_14000C8CA
0x14000c850  cmp     r8d, 0FEh
0x14000c857  jz      short loc_14000C8CA
0x14000c859  mov     [rsp+38h+var_18], 0
0x14000c862  mov     dword ptr [rsp+38h+var_18], ecx
0x14000c866  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000c86c  test    edx, edx
0x14000c86e  jns     short loc_14000C876
0x14000c870  or      word ptr [rsp+38h+var_18+6], 1
0x14000c876  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000c87d  test    rax, rax
0x14000c880  jnz     short loc_14000C8BE
0x14000c882  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c889  test    rax, rax
0x14000c88c  jnz     short loc_14000C8A2
0x14000c88e  lea     rcx, ModuleName; "ntdll.dll"
0x14000c895  call    cs:__imp_GetModuleHandleW
0x14000c89b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c8a2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000c8a9  mov     rcx, rax; hModule
0x14000c8ac  call    cs:__imp_GetProcAddress
0x14000c8b2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000c8b9  test    rax, rax
0x14000c8bc  jz      short loc_14000C8DB
0x14000c8be  lea     rcx, [rsp+38h+var_18]
0x14000c8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8c8  jmp     short loc_14000C8DB
0x14000c8ca  mov     r9, rax
0x14000c8cd  mov     edx, ecx
0x14000c8cf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000c8d6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000c8db  add     rsp, 38h
0x14000c8df  retn
```
