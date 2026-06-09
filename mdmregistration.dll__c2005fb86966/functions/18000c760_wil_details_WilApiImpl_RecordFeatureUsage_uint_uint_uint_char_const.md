# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000c760`
- end: `0x18000c899`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180007c04`
- `0x1800094e0`
- `0x1800099e0`
- `0x180009fb4`
- `0x18000a1d4`
- `0x18000c760`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c83d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c83d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c85a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c85a`

## string_xrefs

- `0x18000c836`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800703F8[25], qword_1800703F8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800703F8);
  }
}

```

## disassembly

```asm
0x18000c760  sub     rsp, 38h
0x18000c764  mov     eax, r8d
0x18000c767  mov     r8d, edx
0x18000c76a  btr     r8d, 1Fh; unsigned __int16
0x18000c76f  test    ecx, ecx
0x18000c771  jnz     short loc_18000C7D0
0x18000c773  test    eax, eax
0x18000c775  jnz     short loc_18000C7D0
0x18000c777  test    r8d, r8d
0x18000c77a  jnz     short loc_18000C7D0
0x18000c77c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000c783  jnz     short loc_18000C7CA
0x18000c785  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c78c  test    rax, rax
0x18000c78f  jz      short loc_18000C79A
0x18000c791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c796  test    al, al
0x18000c798  jnz     short loc_18000C7CA
0x18000c79a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c7a1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000c7a6  test    al, al
0x18000c7a8  jz      short loc_18000C7CA
0x18000c7aa  mov     rdx, cs:qword_1800703F8; SRWLock
0x18000c7b1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000c7b8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000c7bd  mov     rcx, cs:qword_1800703F8; SRWLock
0x18000c7c4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c7c9  nop
0x18000c7ca  add     rsp, 38h
0x18000c7ce  retn
0x18000c7d0  bt      r8d, 1Eh
0x18000c7d5  jnb     short loc_18000C7EC
0x18000c7d7  mov     r9d, eax; unsigned int
0x18000c7da  mov     edx, ecx; unsigned int
0x18000c7dc  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000c7e3  add     rsp, 38h
0x18000c7e7  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000c7ec  test    eax, eax
0x18000c7ee  jnz     loc_18000C882
0x18000c7f4  cmp     r8d, 0FEh
0x18000c7fb  jz      loc_18000C882
0x18000c801  mov     [rsp+38h+var_18], 0
0x18000c80a  mov     dword ptr [rsp+38h+var_18], ecx
0x18000c80e  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000c814  test    edx, edx
0x18000c816  jns     short loc_18000C81E
0x18000c818  or      word ptr [rsp+38h+var_18+6], 1
0x18000c81e  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c825  test    rax, rax
0x18000c828  jnz     short loc_18000C872
0x18000c82a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c831  test    rax, rax
0x18000c834  jnz     short loc_18000C850
0x18000c836  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000c83d  call    cs:__imp_GetModuleHandleW
0x18000c844  nop     dword ptr [rax+rax+00h]
0x18000c849  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c850  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c857  mov     rcx, rax; hModule
0x18000c85a  call    cs:__imp_GetProcAddress
0x18000c861  nop     dword ptr [rax+rax+00h]
0x18000c866  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c86d  test    rax, rax
0x18000c870  jz      short loc_18000C893
0x18000c872  lea     rcx, [rsp+38h+var_18]
0x18000c877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c87c  add     rsp, 38h
0x18000c880  retn
0x18000c882  mov     r9, rax
0x18000c885  mov     edx, ecx
0x18000c887  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c88e  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000c893  add     rsp, 38h
0x18000c897  retn
```
