# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000c920`
- end: `0x14000ca59`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140007bdc`
- `0x140009640`
- `0x140009940`
- `0x140009f14`
- `0x14000a134`
- `0x14000c920`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ca1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ca1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c9fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c9fd`

## string_xrefs

- `0x14000c9f6`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400842B8[25], qword_1400842B8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400842B8);
  }
}

```

## disassembly

```asm
0x14000c920  sub     rsp, 38h
0x14000c924  mov     eax, r8d
0x14000c927  mov     r8d, edx
0x14000c92a  btr     r8d, 1Fh; unsigned __int16
0x14000c92f  test    ecx, ecx
0x14000c931  jnz     short loc_14000C990
0x14000c933  test    eax, eax
0x14000c935  jnz     short loc_14000C990
0x14000c937  test    r8d, r8d
0x14000c93a  jnz     short loc_14000C990
0x14000c93c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000c943  jnz     short loc_14000C98A
0x14000c945  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000c94c  test    rax, rax
0x14000c94f  jz      short loc_14000C95A
0x14000c951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c956  test    al, al
0x14000c958  jnz     short loc_14000C98A
0x14000c95a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000c961  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000c966  test    al, al
0x14000c968  jz      short loc_14000C98A
0x14000c96a  mov     rdx, cs:qword_1400842B8; SRWLock
0x14000c971  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000c978  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000c97d  mov     rcx, cs:qword_1400842B8; SRWLock
0x14000c984  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000c989  nop
0x14000c98a  add     rsp, 38h
0x14000c98e  retn
0x14000c990  bt      r8d, 1Eh
0x14000c995  jnb     short loc_14000C9AC
0x14000c997  mov     r9d, eax; unsigned int
0x14000c99a  mov     edx, ecx; unsigned int
0x14000c99c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000c9a3  add     rsp, 38h
0x14000c9a7  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000c9ac  test    eax, eax
0x14000c9ae  jnz     loc_14000CA42
0x14000c9b4  cmp     r8d, 0FEh
0x14000c9bb  jz      loc_14000CA42
0x14000c9c1  mov     [rsp+38h+var_18], 0
0x14000c9ca  mov     dword ptr [rsp+38h+var_18], ecx
0x14000c9ce  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000c9d4  test    edx, edx
0x14000c9d6  jns     short loc_14000C9DE
0x14000c9d8  or      word ptr [rsp+38h+var_18+6], 1
0x14000c9de  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000c9e5  test    rax, rax
0x14000c9e8  jnz     short loc_14000CA32
0x14000c9ea  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c9f1  test    rax, rax
0x14000c9f4  jnz     short loc_14000CA10
0x14000c9f6  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000c9fd  call    cs:__imp_GetModuleHandleW
0x14000ca04  nop     dword ptr [rax+rax+00h]
0x14000ca09  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ca10  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000ca17  mov     rcx, rax; hModule
0x14000ca1a  call    cs:__imp_GetProcAddress
0x14000ca21  nop     dword ptr [rax+rax+00h]
0x14000ca26  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000ca2d  test    rax, rax
0x14000ca30  jz      short loc_14000CA53
0x14000ca32  lea     rcx, [rsp+38h+var_18]
0x14000ca37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca3c  add     rsp, 38h
0x14000ca40  retn
0x14000ca42  mov     r9, rax
0x14000ca45  mov     edx, ecx
0x14000ca47  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000ca4e  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000ca53  add     rsp, 38h
0x14000ca57  retn
```
