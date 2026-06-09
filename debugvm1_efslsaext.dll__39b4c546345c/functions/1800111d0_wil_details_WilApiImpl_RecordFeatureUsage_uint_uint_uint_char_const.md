# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800111d0`
- end: `0x1800112fb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000e24c`
- `0x18000fc40`
- `0x18000fd04`
- `0x180010090`
- `0x180010210`
- `0x1800111d0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800112c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800112c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800112b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800112b0`

## string_xrefs

- `0x1800112a9`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001E0D0[25], qword_18001E0D0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001E0D0);
  }
}

```

## disassembly

```asm
0x1800111d0  sub     rsp, 38h
0x1800111d4  mov     eax, r8d
0x1800111d7  mov     r8d, edx
0x1800111da  btr     r8d, 1Fh; unsigned __int16
0x1800111df  test    ecx, ecx
0x1800111e1  jnz     short loc_18001124A
0x1800111e3  test    eax, eax
0x1800111e5  jnz     short loc_18001124A
0x1800111e7  test    r8d, r8d
0x1800111ea  jnz     short loc_18001124A
0x1800111ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800111f3  jnz     loc_1800112F6
0x1800111f9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011200  test    rax, rax
0x180011203  jz      short loc_180011212
0x180011205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001120a  test    al, al
0x18001120c  jnz     loc_1800112F6
0x180011212  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180011219  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001121e  test    al, al
0x180011220  jz      loc_1800112F6
0x180011226  mov     rdx, cs:qword_18001E0D0; SRWLock
0x18001122d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180011234  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180011239  mov     rcx, cs:qword_18001E0D0; SRWLock
0x180011240  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180011245  jmp     loc_1800112F6
0x18001124a  bt      r8d, 1Eh
0x18001124f  jnb     short loc_180011267
0x180011251  mov     edx, ecx; unsigned int
0x180011253  mov     r9d, eax; unsigned int
0x180011256  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001125d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180011262  jmp     loc_1800112F6
0x180011267  test    eax, eax
0x180011269  jnz     short loc_1800112E5
0x18001126b  cmp     r8d, 0FEh
0x180011272  jz      short loc_1800112E5
0x180011274  mov     [rsp+38h+var_18], 0
0x18001127d  mov     dword ptr [rsp+38h+var_18], ecx
0x180011281  mov     word ptr [rsp+38h+var_18+4], r8w
0x180011287  test    edx, edx
0x180011289  jns     short loc_180011291
0x18001128b  or      word ptr [rsp+38h+var_18+6], 1
0x180011291  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180011298  test    rax, rax
0x18001129b  jnz     short loc_1800112D9
0x18001129d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800112a4  test    rax, rax
0x1800112a7  jnz     short loc_1800112BD
0x1800112a9  lea     rcx, ModuleName; "ntdll.dll"
0x1800112b0  call    cs:__imp_GetModuleHandleW
0x1800112b6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800112bd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800112c4  mov     rcx, rax; hModule
0x1800112c7  call    cs:__imp_GetProcAddress
0x1800112cd  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800112d4  test    rax, rax
0x1800112d7  jz      short loc_1800112F6
0x1800112d9  lea     rcx, [rsp+38h+var_18]
0x1800112de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112e3  jmp     short loc_1800112F6
0x1800112e5  mov     edx, ecx
0x1800112e7  mov     r9, rax
0x1800112ea  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800112f1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800112f6  add     rsp, 38h
0x1800112fa  retn
```
