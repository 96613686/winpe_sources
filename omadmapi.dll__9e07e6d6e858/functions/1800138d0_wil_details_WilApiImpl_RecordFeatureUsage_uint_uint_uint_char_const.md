# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800138d0`
- end: `0x180013a09`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000bd0c`
- `0x18000ff20`
- `0x180010220`
- `0x180010900`
- `0x180010b24`
- `0x1800138d0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800139ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800139ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800139ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800139ca`

## string_xrefs

- `0x1800139a6`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180032248[25], qword_180032248);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180032248);
  }
}

```

## disassembly

```asm
0x1800138d0  sub     rsp, 38h
0x1800138d4  mov     eax, r8d
0x1800138d7  mov     r8d, edx
0x1800138da  btr     r8d, 1Fh; unsigned __int16
0x1800138df  test    ecx, ecx
0x1800138e1  jnz     short loc_180013940
0x1800138e3  test    eax, eax
0x1800138e5  jnz     short loc_180013940
0x1800138e7  test    r8d, r8d
0x1800138ea  jnz     short loc_180013940
0x1800138ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800138f3  jnz     short loc_18001393A
0x1800138f5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800138fc  test    rax, rax
0x1800138ff  jz      short loc_18001390A
0x180013901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013906  test    al, al
0x180013908  jnz     short loc_18001393A
0x18001390a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180013911  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180013916  test    al, al
0x180013918  jz      short loc_18001393A
0x18001391a  mov     rdx, cs:qword_180032248; SRWLock
0x180013921  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180013928  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001392d  mov     rcx, cs:qword_180032248; SRWLock
0x180013934  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180013939  nop
0x18001393a  add     rsp, 38h
0x18001393e  retn
0x180013940  bt      r8d, 1Eh
0x180013945  jnb     short loc_18001395C
0x180013947  mov     r9d, eax; unsigned int
0x18001394a  mov     edx, ecx; unsigned int
0x18001394c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180013953  add     rsp, 38h
0x180013957  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18001395c  test    eax, eax
0x18001395e  jnz     loc_1800139F2
0x180013964  cmp     r8d, 0FEh
0x18001396b  jz      loc_1800139F2
0x180013971  mov     [rsp+38h+var_18], 0
0x18001397a  mov     dword ptr [rsp+38h+var_18], ecx
0x18001397e  mov     word ptr [rsp+38h+var_18+4], r8w
0x180013984  test    edx, edx
0x180013986  jns     short loc_18001398E
0x180013988  or      word ptr [rsp+38h+var_18+6], 1
0x18001398e  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180013995  test    rax, rax
0x180013998  jnz     short loc_1800139E2
0x18001399a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800139a1  test    rax, rax
0x1800139a4  jnz     short loc_1800139C0
0x1800139a6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800139ad  call    cs:__imp_GetModuleHandleW
0x1800139b4  nop     dword ptr [rax+rax+00h]
0x1800139b9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800139c0  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800139c7  mov     rcx, rax; hModule
0x1800139ca  call    cs:__imp_GetProcAddress
0x1800139d1  nop     dword ptr [rax+rax+00h]
0x1800139d6  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800139dd  test    rax, rax
0x1800139e0  jz      short loc_180013A03
0x1800139e2  lea     rcx, [rsp+38h+var_18]
0x1800139e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139ec  add     rsp, 38h
0x1800139f0  retn
0x1800139f2  mov     r9, rax
0x1800139f5  mov     edx, ecx
0x1800139f7  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800139fe  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180013a03  add     rsp, 38h
0x180013a07  retn
```
