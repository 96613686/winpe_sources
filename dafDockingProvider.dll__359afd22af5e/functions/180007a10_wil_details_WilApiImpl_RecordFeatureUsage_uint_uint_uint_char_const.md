# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180007a10`
- end: `0x180007b30`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800041e4`
- `0x180005714`
- `0x18000587c`
- `0x180005c44`
- `0x180005e00`
- `0x180007a10`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007afc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007afc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ae5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ae5`

## string_xrefs

- `0x180007ade`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180026068[25], qword_180026068);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180026068);
  }
}

```

## disassembly

```asm
0x180007a10  sub     rsp, 38h
0x180007a14  mov     eax, r8d
0x180007a17  mov     r8d, edx
0x180007a1a  btr     r8d, 1Fh; unsigned __int16
0x180007a1f  test    ecx, ecx
0x180007a21  jnz     short loc_180007A7F
0x180007a23  test    eax, eax
0x180007a25  jnz     short loc_180007A7F
0x180007a27  test    r8d, r8d
0x180007a2a  jnz     short loc_180007A7F
0x180007a2c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180007a33  jnz     short loc_180007A7A
0x180007a35  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007a3c  test    rax, rax
0x180007a3f  jz      short loc_180007A4A
0x180007a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a46  test    al, al
0x180007a48  jnz     short loc_180007A7A
0x180007a4a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007a51  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007a56  test    al, al
0x180007a58  jz      short loc_180007A7A
0x180007a5a  mov     rdx, cs:qword_180026068; SRWLock
0x180007a61  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007a68  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180007a6d  mov     rcx, cs:qword_180026068; SRWLock
0x180007a74  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007a79  nop
0x180007a7a  jmp     loc_180007B2B
0x180007a7f  bt      r8d, 1Eh
0x180007a84  jnb     short loc_180007A9C
0x180007a86  mov     r9d, eax; unsigned int
0x180007a89  mov     edx, ecx; unsigned int
0x180007a8b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180007a92  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180007a97  jmp     loc_180007B2B
0x180007a9c  test    eax, eax
0x180007a9e  jnz     short loc_180007B1A
0x180007aa0  cmp     r8d, 0FEh
0x180007aa7  jz      short loc_180007B1A
0x180007aa9  mov     [rsp+38h+var_18], 0
0x180007ab2  mov     dword ptr [rsp+38h+var_18], ecx
0x180007ab6  mov     word ptr [rsp+38h+var_18+4], r8w
0x180007abc  test    edx, edx
0x180007abe  jns     short loc_180007AC6
0x180007ac0  or      word ptr [rsp+38h+var_18+6], 1
0x180007ac6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180007acd  test    rax, rax
0x180007ad0  jnz     short loc_180007B0E
0x180007ad2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007ad9  test    rax, rax
0x180007adc  jnz     short loc_180007AF2
0x180007ade  lea     rcx, ModuleName; "ntdll.dll"
0x180007ae5  call    cs:__imp_GetModuleHandleW
0x180007aeb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007af2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180007af9  mov     rcx, rax; hModule
0x180007afc  call    cs:__imp_GetProcAddress
0x180007b02  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180007b09  test    rax, rax
0x180007b0c  jz      short loc_180007B2B
0x180007b0e  lea     rcx, [rsp+38h+var_18]
0x180007b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b18  jmp     short loc_180007B2B
0x180007b1a  mov     r9, rax
0x180007b1d  mov     edx, ecx
0x180007b1f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007b26  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180007b2b  add     rsp, 38h
0x180007b2f  retn
```
