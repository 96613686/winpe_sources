# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180015940`
- end: `0x180015a6d`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000adb0`
- `0x18000edfc`
- `0x18000f42c`
- `0x18000fb84`
- `0x18000fdb4`
- `0x180015940`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180015a12`
- `KERNEL32!GetModuleHandleW` at `0x180015a12`
- `KERNEL32!GetProcAddress` at `0x180015a2f`
- `KERNEL32!GetProcAddress` at `0x180015a2f`

## string_xrefs

- `0x180015a0b`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // edx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (v4 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        v4,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)v4;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800300A0[25], qword_1800300A0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800300A0);
  }
}

```

## disassembly

```asm
0x180015940  sub     rsp, 38h
0x180015944  mov     eax, edx
0x180015946  btr     edx, 1Fh
0x18001594a  test    ecx, ecx
0x18001594c  jnz     short loc_1800159A9
0x18001594e  test    r8d, r8d
0x180015951  jnz     short loc_1800159A9
0x180015953  test    edx, edx
0x180015955  jnz     short loc_1800159A9
0x180015957  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x18001595d  jnz     short loc_1800159A4
0x18001595f  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180015966  test    rax, rax
0x180015969  jz      short loc_180015974
0x18001596b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015970  test    al, al
0x180015972  jnz     short loc_1800159A4
0x180015974  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001597b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180015980  test    al, al
0x180015982  jz      short loc_1800159A4
0x180015984  mov     rdx, cs:qword_1800300A0; SRWLock
0x18001598b  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180015992  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180015997  mov     rcx, cs:qword_1800300A0; SRWLock
0x18001599e  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800159a3  nop
0x1800159a4  jmp     loc_180015A67
0x1800159a9  bt      edx, 1Eh
0x1800159ad  jnb     short loc_1800159C9
0x1800159af  mov     r9d, r8d; unsigned int
0x1800159b2  movzx   r8d, dx; unsigned __int16
0x1800159b6  mov     edx, ecx; unsigned int
0x1800159b8  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800159bf  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800159c4  jmp     loc_180015A67
0x1800159c9  test    r8d, r8d
0x1800159cc  jnz     loc_180015A53
0x1800159d2  cmp     edx, 0FEh
0x1800159d8  jz      short loc_180015A53
0x1800159da  and     [rsp+38h+var_18], 0
0x1800159e0  mov     dword ptr [rsp+38h+var_18], ecx
0x1800159e4  mov     word ptr [rsp+38h+var_18+4], dx
0x1800159e9  test    eax, eax
0x1800159eb  jns     short loc_1800159F3
0x1800159ed  or      word ptr [rsp+38h+var_18+6], 1
0x1800159f3  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800159fa  test    rax, rax
0x1800159fd  jnz     short loc_180015A47
0x1800159ff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015a06  test    rax, rax
0x180015a09  jnz     short loc_180015A25
0x180015a0b  lea     rcx, ModuleName; "ntdll.dll"
0x180015a12  call    cs:__imp_GetModuleHandleW
0x180015a19  nop     dword ptr [rax+rax+00h]
0x180015a1e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015a25  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180015a2c  mov     rcx, rax; hModule
0x180015a2f  call    cs:__imp_GetProcAddress
0x180015a36  nop     dword ptr [rax+rax+00h]
0x180015a3b  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180015a42  test    rax, rax
0x180015a45  jz      short loc_180015A67
0x180015a47  lea     rcx, [rsp+38h+var_18]
0x180015a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a51  jmp     short loc_180015A67
0x180015a53  mov     r9d, r8d
0x180015a56  mov     r8d, edx
0x180015a59  mov     edx, ecx
0x180015a5b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180015a62  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180015a67  add     rsp, 38h
0x180015a6b  retn
```
