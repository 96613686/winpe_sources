# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14001edd0`
- end: `0x14001ef01`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `305`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400194d0`
- `0x14001ac24`
- `0x14001c1c4`
- `0x14001c7f0`
- `0x14001c994`
- `0x14001edd0`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001eec6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001eec6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001eea9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001eea9`

## string_xrefs

- `0x14001eea2`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_14003E198[25], qword_14003E198);
    wil::details_abi::FeatureStateData::RecordUsage(qword_14003E198);
  }
}

```

## disassembly

```asm
0x14001edd0  sub     rsp, 38h
0x14001edd4  mov     eax, r8d
0x14001edd7  mov     r8d, edx
0x14001edda  btr     r8d, 1Fh; unsigned __int16
0x14001eddf  test    ecx, ecx
0x14001ede1  jnz     short loc_14001EE3F
0x14001ede3  test    eax, eax
0x14001ede5  jnz     short loc_14001EE3F
0x14001ede7  test    r8d, r8d
0x14001edea  jnz     short loc_14001EE3F
0x14001edec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14001edf3  jnz     short loc_14001EE3A
0x14001edf5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14001edfc  test    rax, rax
0x14001edff  jz      short loc_14001EE0A
0x14001ee01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ee06  test    al, al
0x14001ee08  jnz     short loc_14001EE3A
0x14001ee0a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14001ee11  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14001ee16  test    al, al
0x14001ee18  jz      short loc_14001EE3A
0x14001ee1a  mov     rdx, cs:qword_14003E198; SRWLock
0x14001ee21  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14001ee28  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14001ee2d  mov     rcx, cs:qword_14003E198; SRWLock
0x14001ee34  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14001ee39  nop
0x14001ee3a  jmp     loc_14001EEFB
0x14001ee3f  bt      r8d, 1Eh
0x14001ee44  jnb     short loc_14001EE5C
0x14001ee46  mov     r9d, eax; unsigned int
0x14001ee49  mov     edx, ecx; unsigned int
0x14001ee4b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14001ee52  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14001ee57  jmp     loc_14001EEFB
0x14001ee5c  test    eax, eax
0x14001ee5e  jnz     loc_14001EEEA
0x14001ee64  cmp     r8d, 0FEh
0x14001ee6b  jz      short loc_14001EEEA
0x14001ee6d  mov     [rsp+38h+var_18], 0
0x14001ee76  mov     dword ptr [rsp+38h+var_18], ecx
0x14001ee7a  mov     word ptr [rsp+38h+var_18+4], r8w
0x14001ee80  test    edx, edx
0x14001ee82  jns     short loc_14001EE8A
0x14001ee84  or      word ptr [rsp+38h+var_18+6], 1
0x14001ee8a  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14001ee91  test    rax, rax
0x14001ee94  jnz     short loc_14001EEDE
0x14001ee96  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14001ee9d  test    rax, rax
0x14001eea0  jnz     short loc_14001EEBC
0x14001eea2  lea     rcx, ModuleName; "ntdll.dll"
0x14001eea9  call    cs:__imp_GetModuleHandleW
0x14001eeb0  nop     dword ptr [rax+rax+00h]
0x14001eeb5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14001eebc  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14001eec3  mov     rcx, rax; hModule
0x14001eec6  call    cs:__imp_GetProcAddress
0x14001eecd  nop     dword ptr [rax+rax+00h]
0x14001eed2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14001eed9  test    rax, rax
0x14001eedc  jz      short loc_14001EEFB
0x14001eede  lea     rcx, [rsp+38h+var_18]
0x14001eee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eee8  jmp     short loc_14001EEFB
0x14001eeea  mov     r9, rax
0x14001eeed  mov     edx, ecx
0x14001eeef  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14001eef6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14001eefb  add     rsp, 38h
0x14001eeff  retn
```
