# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140018430`
- end: `0x140018569`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400163bc`
- `0x140016b94`
- `0x140016d68`
- `0x1400170f0`
- `0x140017294`
- `0x140018430`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001852a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001852a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001850d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001850d`

## string_xrefs

- `0x140018506`: `ntdll.dll`

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
0x140018430  sub     rsp, 38h
0x140018434  mov     eax, r8d
0x140018437  mov     r8d, edx
0x14001843a  btr     r8d, 1Fh; unsigned __int16
0x14001843f  test    ecx, ecx
0x140018441  jnz     short loc_1400184A0
0x140018443  test    eax, eax
0x140018445  jnz     short loc_1400184A0
0x140018447  test    r8d, r8d
0x14001844a  jnz     short loc_1400184A0
0x14001844c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140018453  jnz     short loc_14001849A
0x140018455  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14001845c  test    rax, rax
0x14001845f  jz      short loc_14001846A
0x140018461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018466  test    al, al
0x140018468  jnz     short loc_14001849A
0x14001846a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140018471  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140018476  test    al, al
0x140018478  jz      short loc_14001849A
0x14001847a  mov     rdx, cs:SRWLock; SRWLock
0x140018481  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140018488  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14001848d  mov     rcx, cs:SRWLock; SRWLock
0x140018494  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140018499  nop
0x14001849a  add     rsp, 38h
0x14001849e  retn
0x1400184a0  bt      r8d, 1Eh
0x1400184a5  jnb     short loc_1400184BC
0x1400184a7  mov     r9d, eax; unsigned int
0x1400184aa  mov     edx, ecx; unsigned int
0x1400184ac  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1400184b3  add     rsp, 38h
0x1400184b7  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1400184bc  test    eax, eax
0x1400184be  jnz     loc_140018552
0x1400184c4  cmp     r8d, 0FEh
0x1400184cb  jz      loc_140018552
0x1400184d1  mov     [rsp+38h+var_18], 0
0x1400184da  mov     dword ptr [rsp+38h+var_18], ecx
0x1400184de  mov     word ptr [rsp+38h+var_18+4], r8w
0x1400184e4  test    edx, edx
0x1400184e6  jns     short loc_1400184EE
0x1400184e8  or      word ptr [rsp+38h+var_18+6], 1
0x1400184ee  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1400184f5  test    rax, rax
0x1400184f8  jnz     short loc_140018542
0x1400184fa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140018501  test    rax, rax
0x140018504  jnz     short loc_140018520
0x140018506  lea     rcx, ModuleName; "ntdll.dll"
0x14001850d  call    cs:__imp_GetModuleHandleW
0x140018514  nop     dword ptr [rax+rax+00h]
0x140018519  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140018520  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140018527  mov     rcx, rax; hModule
0x14001852a  call    cs:__imp_GetProcAddress
0x140018531  nop     dword ptr [rax+rax+00h]
0x140018536  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14001853d  test    rax, rax
0x140018540  jz      short loc_140018563
0x140018542  lea     rcx, [rsp+38h+var_18]
0x140018547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001854c  add     rsp, 38h
0x140018550  retn
0x140018552  mov     r9, rax
0x140018555  mov     edx, ecx
0x140018557  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14001855e  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140018563  add     rsp, 38h
0x140018567  retn
```
