# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180008980`
- end: `0x180008aa0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004584`
- `0x180005f78`
- `0x18000617c`
- `0x1800067a4`
- `0x1800069a0`
- `0x180008980`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a6c`

## string_xrefs

- `0x180008a4e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18002A058[25], qword_18002A058);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18002A058);
  }
}

```

## disassembly

```asm
0x180008980  sub     rsp, 38h
0x180008984  mov     eax, r8d
0x180008987  mov     r8d, edx
0x18000898a  btr     r8d, 1Fh; unsigned __int16
0x18000898f  test    ecx, ecx
0x180008991  jnz     short loc_1800089EF
0x180008993  test    eax, eax
0x180008995  jnz     short loc_1800089EF
0x180008997  test    r8d, r8d
0x18000899a  jnz     short loc_1800089EF
0x18000899c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800089a3  jnz     short loc_1800089EA
0x1800089a5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800089ac  test    rax, rax
0x1800089af  jz      short loc_1800089BA
0x1800089b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089b6  test    al, al
0x1800089b8  jnz     short loc_1800089EA
0x1800089ba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800089c1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800089c6  test    al, al
0x1800089c8  jz      short loc_1800089EA
0x1800089ca  mov     rdx, cs:qword_18002A058; SRWLock
0x1800089d1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800089d8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800089dd  mov     rcx, cs:qword_18002A058; SRWLock
0x1800089e4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800089e9  nop
0x1800089ea  jmp     loc_180008A9B
0x1800089ef  bt      r8d, 1Eh
0x1800089f4  jnb     short loc_180008A0C
0x1800089f6  mov     r9d, eax; unsigned int
0x1800089f9  mov     edx, ecx; unsigned int
0x1800089fb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180008a02  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180008a07  jmp     loc_180008A9B
0x180008a0c  test    eax, eax
0x180008a0e  jnz     short loc_180008A8A
0x180008a10  cmp     r8d, 0FEh
0x180008a17  jz      short loc_180008A8A
0x180008a19  mov     [rsp+38h+var_18], 0
0x180008a22  mov     dword ptr [rsp+38h+var_18], ecx
0x180008a26  mov     word ptr [rsp+38h+var_18+4], r8w
0x180008a2c  test    edx, edx
0x180008a2e  jns     short loc_180008A36
0x180008a30  or      word ptr [rsp+38h+var_18+6], 1
0x180008a36  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180008a3d  test    rax, rax
0x180008a40  jnz     short loc_180008A7E
0x180008a42  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a49  test    rax, rax
0x180008a4c  jnz     short loc_180008A62
0x180008a4e  lea     rcx, ModuleName; "ntdll.dll"
0x180008a55  call    cs:__imp_GetModuleHandleW
0x180008a5b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a62  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008a69  mov     rcx, rax; hModule
0x180008a6c  call    cs:__imp_GetProcAddress
0x180008a72  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008a79  test    rax, rax
0x180008a7c  jz      short loc_180008A9B
0x180008a7e  lea     rcx, [rsp+38h+var_18]
0x180008a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a88  jmp     short loc_180008A9B
0x180008a8a  mov     r9, rax
0x180008a8d  mov     edx, ecx
0x180008a8f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008a96  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180008a9b  add     rsp, 38h
0x180008a9f  retn
```
