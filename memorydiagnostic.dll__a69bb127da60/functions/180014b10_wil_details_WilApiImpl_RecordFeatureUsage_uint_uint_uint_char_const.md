# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180014b10`
- end: `0x180014c30`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000ac74`
- `0x18000e5dc`
- `0x18000eacc`
- `0x18000f294`
- `0x18000f490`
- `0x180014b10`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180014be5`
- `KERNEL32!GetModuleHandleW` at `0x180014be5`
- `KERNEL32!GetProcAddress` at `0x180014bfc`
- `KERNEL32!GetProcAddress` at `0x180014bfc`

## string_xrefs

- `0x180014bde`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18002F0A0[25], qword_18002F0A0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18002F0A0);
  }
}

```

## disassembly

```asm
0x180014b10  sub     rsp, 38h
0x180014b14  mov     eax, r8d
0x180014b17  mov     r8d, edx
0x180014b1a  btr     r8d, 1Fh; unsigned __int16
0x180014b1f  test    ecx, ecx
0x180014b21  jnz     short loc_180014B7F
0x180014b23  test    eax, eax
0x180014b25  jnz     short loc_180014B7F
0x180014b27  test    r8d, r8d
0x180014b2a  jnz     short loc_180014B7F
0x180014b2c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180014b33  jnz     short loc_180014B7A
0x180014b35  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014b3c  test    rax, rax
0x180014b3f  jz      short loc_180014B4A
0x180014b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b46  test    al, al
0x180014b48  jnz     short loc_180014B7A
0x180014b4a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180014b51  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180014b56  test    al, al
0x180014b58  jz      short loc_180014B7A
0x180014b5a  mov     rdx, cs:qword_18002F0A0; SRWLock
0x180014b61  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180014b68  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180014b6d  mov     rcx, cs:qword_18002F0A0; SRWLock
0x180014b74  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180014b79  nop
0x180014b7a  jmp     loc_180014C2B
0x180014b7f  bt      r8d, 1Eh
0x180014b84  jnb     short loc_180014B9C
0x180014b86  mov     r9d, eax; unsigned int
0x180014b89  mov     edx, ecx; unsigned int
0x180014b8b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180014b92  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180014b97  jmp     loc_180014C2B
0x180014b9c  test    eax, eax
0x180014b9e  jnz     short loc_180014C1A
0x180014ba0  cmp     r8d, 0FEh
0x180014ba7  jz      short loc_180014C1A
0x180014ba9  mov     [rsp+38h+var_18], 0
0x180014bb2  mov     dword ptr [rsp+38h+var_18], ecx
0x180014bb6  mov     word ptr [rsp+38h+var_18+4], r8w
0x180014bbc  test    edx, edx
0x180014bbe  jns     short loc_180014BC6
0x180014bc0  or      word ptr [rsp+38h+var_18+6], 1
0x180014bc6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180014bcd  test    rax, rax
0x180014bd0  jnz     short loc_180014C0E
0x180014bd2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014bd9  test    rax, rax
0x180014bdc  jnz     short loc_180014BF2
0x180014bde  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180014be5  call    cs:__imp_GetModuleHandleW
0x180014beb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014bf2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180014bf9  mov     rcx, rax; hModule
0x180014bfc  call    cs:__imp_GetProcAddress
0x180014c02  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180014c09  test    rax, rax
0x180014c0c  jz      short loc_180014C2B
0x180014c0e  lea     rcx, [rsp+38h+var_18]
0x180014c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c18  jmp     short loc_180014C2B
0x180014c1a  mov     r9, rax
0x180014c1d  mov     edx, ecx
0x180014c1f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180014c26  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180014c2b  add     rsp, 38h
0x180014c2f  retn
```
