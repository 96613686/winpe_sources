# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000a030`
- end: `0x18000a15b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800059d4`
- `0x180007f74`
- `0x180008178`
- `0x1800086f4`
- `0x1800088e0`
- `0x18000a030`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a127`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a127`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a110`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a110`

## string_xrefs

- `0x18000a109`: `ntdll.dll`

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
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180014018[25], qword_180014018);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180014018);
  }
}

```

## disassembly

```asm
0x18000a030  sub     rsp, 38h
0x18000a034  mov     eax, r8d
0x18000a037  mov     r8d, edx
0x18000a03a  btr     r8d, 1Fh; unsigned __int16
0x18000a03f  test    ecx, ecx
0x18000a041  jnz     short loc_18000A0AA
0x18000a043  test    eax, eax
0x18000a045  jnz     short loc_18000A0AA
0x18000a047  test    r8d, r8d
0x18000a04a  jnz     short loc_18000A0AA
0x18000a04c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000a053  jnz     loc_18000A156
0x18000a059  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a060  test    rax, rax
0x18000a063  jz      short loc_18000A072
0x18000a065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a06a  test    al, al
0x18000a06c  jnz     loc_18000A156
0x18000a072  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000a079  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a07e  test    al, al
0x18000a080  jz      loc_18000A156
0x18000a086  mov     rdx, cs:qword_180014018; SRWLock
0x18000a08d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000a094  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000a099  mov     rcx, cs:qword_180014018; SRWLock
0x18000a0a0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a0a5  jmp     loc_18000A156
0x18000a0aa  bt      r8d, 1Eh
0x18000a0af  jnb     short loc_18000A0C7
0x18000a0b1  mov     edx, ecx; unsigned int
0x18000a0b3  mov     r9d, eax; unsigned int
0x18000a0b6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000a0bd  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000a0c2  jmp     loc_18000A156
0x18000a0c7  test    eax, eax
0x18000a0c9  jnz     short loc_18000A145
0x18000a0cb  cmp     r8d, 0FEh
0x18000a0d2  jz      short loc_18000A145
0x18000a0d4  mov     [rsp+38h+var_18], 0
0x18000a0dd  mov     dword ptr [rsp+38h+var_18], ecx
0x18000a0e1  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000a0e7  test    edx, edx
0x18000a0e9  jns     short loc_18000A0F1
0x18000a0eb  or      word ptr [rsp+38h+var_18+6], 1
0x18000a0f1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000a0f8  test    rax, rax
0x18000a0fb  jnz     short loc_18000A139
0x18000a0fd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a104  test    rax, rax
0x18000a107  jnz     short loc_18000A11D
0x18000a109  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a110  call    cs:__imp_GetModuleHandleW
0x18000a116  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a11d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000a124  mov     rcx, rax; hModule
0x18000a127  call    cs:__imp_GetProcAddress
0x18000a12d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000a134  test    rax, rax
0x18000a137  jz      short loc_18000A156
0x18000a139  lea     rcx, [rsp+38h+var_18]
0x18000a13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a143  jmp     short loc_18000A156
0x18000a145  mov     edx, ecx
0x18000a147  mov     r9, rax
0x18000a14a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a151  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000a156  add     rsp, 38h
0x18000a15a  retn
```
