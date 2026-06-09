# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180012600`
- end: `0x18001272b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180010c2c`
- `0x1800110e4`
- `0x1800111a8`
- `0x180011534`
- `0x1800116b4`
- `0x180012600`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800126f7`
- `KERNEL32!GetProcAddress` at `0x1800126f7`
- `KERNEL32!GetModuleHandleW` at `0x1800126e0`
- `KERNEL32!GetModuleHandleW` at `0x1800126e0`

## string_xrefs

- `0x1800126d9`: `ntdll.dll`

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
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001A250[25], qword_18001A250);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001A250);
  }
}

```

## disassembly

```asm
0x180012600  sub     rsp, 38h
0x180012604  mov     eax, r8d
0x180012607  mov     r8d, edx
0x18001260a  btr     r8d, 1Fh; unsigned __int16
0x18001260f  test    ecx, ecx
0x180012611  jnz     short loc_18001267A
0x180012613  test    eax, eax
0x180012615  jnz     short loc_18001267A
0x180012617  test    r8d, r8d
0x18001261a  jnz     short loc_18001267A
0x18001261c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180012623  jnz     loc_180012726
0x180012629  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180012630  test    rax, rax
0x180012633  jz      short loc_180012642
0x180012635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001263a  test    al, al
0x18001263c  jnz     loc_180012726
0x180012642  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180012649  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001264e  test    al, al
0x180012650  jz      loc_180012726
0x180012656  mov     rdx, cs:qword_18001A250; SRWLock
0x18001265d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180012664  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180012669  mov     rcx, cs:qword_18001A250; SRWLock
0x180012670  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180012675  jmp     loc_180012726
0x18001267a  bt      r8d, 1Eh
0x18001267f  jnb     short loc_180012697
0x180012681  mov     edx, ecx; unsigned int
0x180012683  mov     r9d, eax; unsigned int
0x180012686  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001268d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180012692  jmp     loc_180012726
0x180012697  test    eax, eax
0x180012699  jnz     short loc_180012715
0x18001269b  cmp     r8d, 0FEh
0x1800126a2  jz      short loc_180012715
0x1800126a4  mov     [rsp+38h+var_18], 0
0x1800126ad  mov     dword ptr [rsp+38h+var_18], ecx
0x1800126b1  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800126b7  test    edx, edx
0x1800126b9  jns     short loc_1800126C1
0x1800126bb  or      word ptr [rsp+38h+var_18+6], 1
0x1800126c1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800126c8  test    rax, rax
0x1800126cb  jnz     short loc_180012709
0x1800126cd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800126d4  test    rax, rax
0x1800126d7  jnz     short loc_1800126ED
0x1800126d9  lea     rcx, ModuleName; "ntdll.dll"
0x1800126e0  call    cs:__imp_GetModuleHandleW
0x1800126e6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800126ed  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800126f4  mov     rcx, rax; hModule
0x1800126f7  call    cs:__imp_GetProcAddress
0x1800126fd  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180012704  test    rax, rax
0x180012707  jz      short loc_180012726
0x180012709  lea     rcx, [rsp+38h+var_18]
0x18001270e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012713  jmp     short loc_180012726
0x180012715  mov     edx, ecx
0x180012717  mov     r9, rax
0x18001271a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180012721  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180012726  add     rsp, 38h
0x18001272a  retn
```
