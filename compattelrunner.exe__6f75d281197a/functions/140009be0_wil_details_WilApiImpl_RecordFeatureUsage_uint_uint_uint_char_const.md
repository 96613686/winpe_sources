# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140009be0`
- end: `0x140009d00`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400050a4`
- `0x140006dc4`
- `0x140006fc8`
- `0x140007734`
- `0x140007930`
- `0x140009be0`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009cb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009cb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009ccc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009ccc`

## string_xrefs

- `0x140009cae`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400C81C8[25], qword_1400C81C8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400C81C8);
  }
}

```

## disassembly

```asm
0x140009be0  sub     rsp, 38h
0x140009be4  mov     eax, r8d
0x140009be7  mov     r8d, edx
0x140009bea  btr     r8d, 1Fh; unsigned __int16
0x140009bef  test    ecx, ecx
0x140009bf1  jnz     short loc_140009C4F
0x140009bf3  test    eax, eax
0x140009bf5  jnz     short loc_140009C4F
0x140009bf7  test    r8d, r8d
0x140009bfa  jnz     short loc_140009C4F
0x140009bfc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140009c03  jnz     short loc_140009C4A
0x140009c05  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140009c0c  test    rax, rax
0x140009c0f  jz      short loc_140009C1A
0x140009c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c16  test    al, al
0x140009c18  jnz     short loc_140009C4A
0x140009c1a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140009c21  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140009c26  test    al, al
0x140009c28  jz      short loc_140009C4A
0x140009c2a  mov     rdx, cs:qword_1400C81C8; SRWLock
0x140009c31  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140009c38  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x140009c3d  mov     rcx, cs:qword_1400C81C8; SRWLock
0x140009c44  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140009c49  nop
0x140009c4a  jmp     loc_140009CFB
0x140009c4f  bt      r8d, 1Eh
0x140009c54  jnb     short loc_140009C6C
0x140009c56  mov     r9d, eax; unsigned int
0x140009c59  mov     edx, ecx; unsigned int
0x140009c5b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140009c62  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140009c67  jmp     loc_140009CFB
0x140009c6c  test    eax, eax
0x140009c6e  jnz     short loc_140009CEA
0x140009c70  cmp     r8d, 0FEh
0x140009c77  jz      short loc_140009CEA
0x140009c79  mov     [rsp+38h+var_18], 0
0x140009c82  mov     dword ptr [rsp+38h+var_18], ecx
0x140009c86  mov     word ptr [rsp+38h+var_18+4], r8w
0x140009c8c  test    edx, edx
0x140009c8e  jns     short loc_140009C96
0x140009c90  or      word ptr [rsp+38h+var_18+6], 1
0x140009c96  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140009c9d  test    rax, rax
0x140009ca0  jnz     short loc_140009CDE
0x140009ca2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009ca9  test    rax, rax
0x140009cac  jnz     short loc_140009CC2
0x140009cae  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140009cb5  call    cs:__imp_GetModuleHandleW
0x140009cbb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009cc2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140009cc9  mov     rcx, rax; hModule
0x140009ccc  call    cs:__imp_GetProcAddress
0x140009cd2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140009cd9  test    rax, rax
0x140009cdc  jz      short loc_140009CFB
0x140009cde  lea     rcx, [rsp+38h+var_18]
0x140009ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ce8  jmp     short loc_140009CFB
0x140009cea  mov     r9, rax
0x140009ced  mov     edx, ecx
0x140009cef  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140009cf6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140009cfb  add     rsp, 38h
0x140009cff  retn
```
