# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000b8c0`
- end: `0x18000b9f1`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `305`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000691c`
- `0x1800087ac`
- `0x180008a1c`
- `0x180008e24`
- `0x180009008`
- `0x18000b8c0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b999`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b999`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9b6`

## string_xrefs

- `0x18000b992`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        &wil::details::g_featureStateManager,
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&SRWLock[25], SRWLock);
    wil::details_abi::FeatureStateData::RecordUsage(SRWLock);
  }
}

```

## disassembly

```asm
0x18000b8c0  sub     rsp, 38h
0x18000b8c4  mov     eax, r8d
0x18000b8c7  mov     r8d, edx
0x18000b8ca  btr     r8d, 1Fh; unsigned __int16
0x18000b8cf  test    ecx, ecx
0x18000b8d1  jnz     short loc_18000B92F
0x18000b8d3  test    eax, eax
0x18000b8d5  jnz     short loc_18000B92F
0x18000b8d7  test    r8d, r8d
0x18000b8da  jnz     short loc_18000B92F
0x18000b8dc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000b8e3  jnz     short loc_18000B92A
0x18000b8e5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b8ec  test    rax, rax
0x18000b8ef  jz      short loc_18000B8FA
0x18000b8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f6  test    al, al
0x18000b8f8  jnz     short loc_18000B92A
0x18000b8fa  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b901  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b906  test    al, al
0x18000b908  jz      short loc_18000B92A
0x18000b90a  mov     rdx, cs:SRWLock; SRWLock
0x18000b911  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000b918  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000b91d  mov     rcx, cs:SRWLock; SRWLock
0x18000b924  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b929  nop
0x18000b92a  jmp     loc_18000B9EB
0x18000b92f  bt      r8d, 1Eh
0x18000b934  jnb     short loc_18000B94C
0x18000b936  mov     r9d, eax; unsigned int
0x18000b939  mov     edx, ecx; unsigned int
0x18000b93b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000b942  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000b947  jmp     loc_18000B9EB
0x18000b94c  test    eax, eax
0x18000b94e  jnz     loc_18000B9DA
0x18000b954  cmp     r8d, 0FEh
0x18000b95b  jz      short loc_18000B9DA
0x18000b95d  mov     [rsp+38h+var_18], 0
0x18000b966  mov     dword ptr [rsp+38h+var_18], ecx
0x18000b96a  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000b970  test    edx, edx
0x18000b972  jns     short loc_18000B97A
0x18000b974  or      word ptr [rsp+38h+var_18+6], 1
0x18000b97a  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b981  test    rax, rax
0x18000b984  jnz     short loc_18000B9CE
0x18000b986  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b98d  test    rax, rax
0x18000b990  jnz     short loc_18000B9AC
0x18000b992  lea     rcx, ModuleName; "ntdll.dll"
0x18000b999  call    cs:__imp_GetModuleHandleW
0x18000b9a0  nop     dword ptr [rax+rax+00h]
0x18000b9a5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b9ac  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b9b3  mov     rcx, rax; hModule
0x18000b9b6  call    cs:__imp_GetProcAddress
0x18000b9bd  nop     dword ptr [rax+rax+00h]
0x18000b9c2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b9c9  test    rax, rax
0x18000b9cc  jz      short loc_18000B9EB
0x18000b9ce  lea     rcx, [rsp+38h+var_18]
0x18000b9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9d8  jmp     short loc_18000B9EB
0x18000b9da  mov     r9, rax
0x18000b9dd  mov     edx, ecx
0x18000b9df  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b9e6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000b9eb  add     rsp, 38h
0x18000b9ef  retn
```
