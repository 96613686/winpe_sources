# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140009880`
- end: `0x1400099b9`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140004cbc`
- `0x140006670`
- `0x140006b24`
- `0x140007284`
- `0x1400074a4`
- `0x140009880`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000995d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000995d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000997a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000997a`

## string_xrefs

- `0x140009956`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140023190[25], qword_140023190);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140023190);
  }
}

```

## disassembly

```asm
0x140009880  sub     rsp, 38h
0x140009884  mov     eax, r8d
0x140009887  mov     r8d, edx
0x14000988a  btr     r8d, 1Fh; unsigned __int16
0x14000988f  test    ecx, ecx
0x140009891  jnz     short loc_1400098F0
0x140009893  test    eax, eax
0x140009895  jnz     short loc_1400098F0
0x140009897  test    r8d, r8d
0x14000989a  jnz     short loc_1400098F0
0x14000989c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1400098a3  jnz     short loc_1400098EA
0x1400098a5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400098ac  test    rax, rax
0x1400098af  jz      short loc_1400098BA
0x1400098b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098b6  test    al, al
0x1400098b8  jnz     short loc_1400098EA
0x1400098ba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1400098c1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400098c6  test    al, al
0x1400098c8  jz      short loc_1400098EA
0x1400098ca  mov     rdx, cs:qword_140023190; SRWLock
0x1400098d1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400098d8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1400098dd  mov     rcx, cs:qword_140023190; SRWLock
0x1400098e4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400098e9  nop
0x1400098ea  add     rsp, 38h
0x1400098ee  retn
0x1400098f0  bt      r8d, 1Eh
0x1400098f5  jnb     short loc_14000990C
0x1400098f7  mov     r9d, eax; unsigned int
0x1400098fa  mov     edx, ecx; unsigned int
0x1400098fc  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140009903  add     rsp, 38h
0x140009907  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000990c  test    eax, eax
0x14000990e  jnz     loc_1400099A2
0x140009914  cmp     r8d, 0FEh
0x14000991b  jz      loc_1400099A2
0x140009921  mov     [rsp+38h+var_18], 0
0x14000992a  mov     dword ptr [rsp+38h+var_18], ecx
0x14000992e  mov     word ptr [rsp+38h+var_18+4], r8w
0x140009934  test    edx, edx
0x140009936  jns     short loc_14000993E
0x140009938  or      word ptr [rsp+38h+var_18+6], 1
0x14000993e  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140009945  test    rax, rax
0x140009948  jnz     short loc_140009992
0x14000994a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009951  test    rax, rax
0x140009954  jnz     short loc_140009970
0x140009956  lea     rcx, ModuleName; "ntdll.dll"
0x14000995d  call    cs:__imp_GetModuleHandleW
0x140009964  nop     dword ptr [rax+rax+00h]
0x140009969  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009970  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140009977  mov     rcx, rax; hModule
0x14000997a  call    cs:__imp_GetProcAddress
0x140009981  nop     dword ptr [rax+rax+00h]
0x140009986  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000998d  test    rax, rax
0x140009990  jz      short loc_1400099B3
0x140009992  lea     rcx, [rsp+38h+var_18]
0x140009997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000999c  add     rsp, 38h
0x1400099a0  retn
0x1400099a2  mov     r9, rax
0x1400099a5  mov     edx, ecx
0x1400099a7  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400099ae  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1400099b3  add     rsp, 38h
0x1400099b7  retn
```
