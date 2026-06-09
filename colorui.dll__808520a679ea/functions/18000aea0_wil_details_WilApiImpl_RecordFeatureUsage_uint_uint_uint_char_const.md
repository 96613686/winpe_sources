# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000aea0`
- end: `0x18000afcb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180005400`
- `0x18000724c`
- `0x180007818`
- `0x180007d94`
- `0x180007f80`
- `0x18000aea0`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000af97`
- `KERNEL32!GetProcAddress` at `0x18000af97`
- `KERNEL32!GetModuleHandleW` at `0x18000af80`
- `KERNEL32!GetModuleHandleW` at `0x18000af80`

## string_xrefs

- `0x18000af79`: `ntdll.dll`

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
        goto LABEL_19;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_19:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180021188[25], qword_180021188);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180021188);
  }
}

```

## disassembly

```asm
0x18000aea0  sub     rsp, 38h
0x18000aea4  mov     eax, r8d
0x18000aea7  mov     r8d, edx
0x18000aeaa  btr     r8d, 1Fh; unsigned __int16
0x18000aeaf  test    ecx, ecx
0x18000aeb1  jnz     short loc_18000AF1A
0x18000aeb3  test    eax, eax
0x18000aeb5  jnz     short loc_18000AF1A
0x18000aeb7  test    r8d, r8d
0x18000aeba  jnz     short loc_18000AF1A
0x18000aebc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000aec3  jnz     loc_18000AFC6
0x18000aec9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000aed0  test    rax, rax
0x18000aed3  jz      short loc_18000AEE2
0x18000aed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeda  test    al, al
0x18000aedc  jnz     loc_18000AFC6
0x18000aee2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000aee9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000aeee  test    al, al
0x18000aef0  jz      loc_18000AFC6
0x18000aef6  mov     rdx, cs:qword_180021188; SRWLock
0x18000aefd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000af04  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000af09  mov     rcx, cs:qword_180021188; SRWLock
0x18000af10  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000af15  jmp     loc_18000AFC6
0x18000af1a  bt      r8d, 1Eh
0x18000af1f  jnb     short loc_18000AF37
0x18000af21  mov     edx, ecx; unsigned int
0x18000af23  mov     r9d, eax; unsigned int
0x18000af26  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000af2d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000af32  jmp     loc_18000AFC6
0x18000af37  test    eax, eax
0x18000af39  jnz     short loc_18000AFB5
0x18000af3b  cmp     r8d, 0FEh
0x18000af42  jz      short loc_18000AFB5
0x18000af44  mov     [rsp+38h+var_18], 0
0x18000af4d  mov     dword ptr [rsp+38h+var_18], ecx
0x18000af51  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000af57  test    edx, edx
0x18000af59  jns     short loc_18000AF61
0x18000af5b  or      word ptr [rsp+38h+var_18+6], 1
0x18000af61  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000af68  test    rax, rax
0x18000af6b  jnz     short loc_18000AFA9
0x18000af6d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000af74  test    rax, rax
0x18000af77  jnz     short loc_18000AF8D
0x18000af79  lea     rcx, ModuleName; "ntdll.dll"
0x18000af80  call    cs:__imp_GetModuleHandleW
0x18000af86  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000af8d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000af94  mov     rcx, rax; hModule
0x18000af97  call    cs:__imp_GetProcAddress
0x18000af9d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000afa4  test    rax, rax
0x18000afa7  jz      short loc_18000AFC6
0x18000afa9  lea     rcx, [rsp+38h+var_18]
0x18000afae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb3  jmp     short loc_18000AFC6
0x18000afb5  mov     edx, ecx
0x18000afb7  mov     r9, rax
0x18000afba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000afc1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000afc6  add     rsp, 38h
0x18000afca  retn
```
