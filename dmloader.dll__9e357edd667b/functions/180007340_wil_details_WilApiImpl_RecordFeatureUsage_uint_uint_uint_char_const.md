# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180007340`
- end: `0x18000746b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180003d34`
- `0x180005334`
- `0x180005500`
- `0x1800058e4`
- `0x180005a9c`
- `0x180007340`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007420`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007420`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007437`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007437`

## string_xrefs

- `0x180007419`: `ntdll.dll`

## pseudocode

```c
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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180015018[25], qword_180015018);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180015018);
  }
}

```

## disassembly

```asm
0x180007340  sub     rsp, 38h
0x180007344  mov     eax, r8d
0x180007347  mov     r8d, edx
0x18000734a  btr     r8d, 1Fh; unsigned __int16
0x18000734f  test    ecx, ecx
0x180007351  jnz     short loc_1800073BA
0x180007353  test    eax, eax
0x180007355  jnz     short loc_1800073BA
0x180007357  test    r8d, r8d
0x18000735a  jnz     short loc_1800073BA
0x18000735c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180007363  jnz     loc_180007466
0x180007369  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007370  test    rax, rax
0x180007373  jz      short loc_180007382
0x180007375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000737a  test    al, al
0x18000737c  jnz     loc_180007466
0x180007382  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007389  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000738e  test    al, al
0x180007390  jz      loc_180007466
0x180007396  mov     rdx, cs:qword_180015018; SRWLock
0x18000739d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800073a4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800073a9  mov     rcx, cs:qword_180015018; SRWLock
0x1800073b0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800073b5  jmp     loc_180007466
0x1800073ba  bt      r8d, 1Eh
0x1800073bf  jnb     short loc_1800073D7
0x1800073c1  mov     edx, ecx; unsigned int
0x1800073c3  mov     r9d, eax; unsigned int
0x1800073c6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800073cd  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800073d2  jmp     loc_180007466
0x1800073d7  test    eax, eax
0x1800073d9  jnz     short loc_180007455
0x1800073db  cmp     r8d, 0FEh
0x1800073e2  jz      short loc_180007455
0x1800073e4  mov     [rsp+38h+var_18], 0
0x1800073ed  mov     dword ptr [rsp+38h+var_18], ecx
0x1800073f1  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800073f7  test    edx, edx
0x1800073f9  jns     short loc_180007401
0x1800073fb  or      word ptr [rsp+38h+var_18+6], 1
0x180007401  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180007408  test    rax, rax
0x18000740b  jnz     short loc_180007449
0x18000740d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007414  test    rax, rax
0x180007417  jnz     short loc_18000742D
0x180007419  lea     rcx, ModuleName; "ntdll.dll"
0x180007420  call    cs:__imp_GetModuleHandleW
0x180007426  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000742d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180007434  mov     rcx, rax; hModule
0x180007437  call    cs:__imp_GetProcAddress
0x18000743d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180007444  test    rax, rax
0x180007447  jz      short loc_180007466
0x180007449  lea     rcx, [rsp+38h+var_18]
0x18000744e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007453  jmp     short loc_180007466
0x180007455  mov     edx, ecx
0x180007457  mov     r9, rax
0x18000745a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007461  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180007466  add     rsp, 38h
0x18000746a  retn
```
