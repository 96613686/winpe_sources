# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000b050`
- end: `0x18000b181`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `305`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000643c`
- `0x180007eac`
- `0x180008250`
- `0x180008824`
- `0x180008a44`
- `0x18000b050`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b146`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b146`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b129`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b129`

## string_xrefs

- `0x18000b122`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // r8d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        a2,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        (__int64)&wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180072360[25], qword_180072360);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180072360);
  }
}

```

## disassembly

```asm
0x18000b050  sub     rsp, 38h
0x18000b054  mov     eax, r8d
0x18000b057  mov     r8d, edx
0x18000b05a  btr     r8d, 1Fh; unsigned __int16
0x18000b05f  test    ecx, ecx
0x18000b061  jnz     short loc_18000B0BF
0x18000b063  test    eax, eax
0x18000b065  jnz     short loc_18000B0BF
0x18000b067  test    r8d, r8d
0x18000b06a  jnz     short loc_18000B0BF
0x18000b06c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000b073  jnz     short loc_18000B0BA
0x18000b075  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b07c  test    rax, rax
0x18000b07f  jz      short loc_18000B08A
0x18000b081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b086  test    al, al
0x18000b088  jnz     short loc_18000B0BA
0x18000b08a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b091  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b096  test    al, al
0x18000b098  jz      short loc_18000B0BA
0x18000b09a  mov     rdx, cs:qword_180072360; SRWLock
0x18000b0a1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000b0a8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000b0ad  mov     rcx, cs:qword_180072360; SRWLock
0x18000b0b4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b0b9  nop
0x18000b0ba  jmp     loc_18000B17B
0x18000b0bf  bt      r8d, 1Eh
0x18000b0c4  jnb     short loc_18000B0DC
0x18000b0c6  mov     r9d, eax; unsigned int
0x18000b0c9  mov     edx, ecx; unsigned int
0x18000b0cb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000b0d2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000b0d7  jmp     loc_18000B17B
0x18000b0dc  test    eax, eax
0x18000b0de  jnz     loc_18000B16A
0x18000b0e4  cmp     r8d, 0FEh
0x18000b0eb  jz      short loc_18000B16A
0x18000b0ed  mov     [rsp+38h+var_18], 0
0x18000b0f6  mov     dword ptr [rsp+38h+var_18], ecx
0x18000b0fa  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000b100  test    edx, edx
0x18000b102  jns     short loc_18000B10A
0x18000b104  or      word ptr [rsp+38h+var_18+6], 1
0x18000b10a  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b111  test    rax, rax
0x18000b114  jnz     short loc_18000B15E
0x18000b116  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b11d  test    rax, rax
0x18000b120  jnz     short loc_18000B13C
0x18000b122  lea     rcx, ModuleName; "ntdll.dll"
0x18000b129  call    cs:__imp_GetModuleHandleW
0x18000b130  nop     dword ptr [rax+rax+00h]
0x18000b135  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b13c  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b143  mov     rcx, rax; hModule
0x18000b146  call    cs:__imp_GetProcAddress
0x18000b14d  nop     dword ptr [rax+rax+00h]
0x18000b152  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b159  test    rax, rax
0x18000b15c  jz      short loc_18000B17B
0x18000b15e  lea     rcx, [rsp+38h+var_18]
0x18000b163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b168  jmp     short loc_18000B17B
0x18000b16a  mov     r9, rax
0x18000b16d  mov     edx, ecx
0x18000b16f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b176  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000b17b  add     rsp, 38h
0x18000b17f  retn
```
