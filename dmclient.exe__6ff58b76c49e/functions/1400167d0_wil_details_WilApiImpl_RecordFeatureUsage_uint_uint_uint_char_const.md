# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1400167d0`
- end: `0x1400168f0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140013728`
- `0x1400149c8`
- `0x140014a8c`
- `0x140014e18`
- `0x140014f9c`
- `0x1400167d0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400168bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400168bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400168a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400168a5`

## string_xrefs

- `0x14001689e`: `ntdll.dll`

## pseudocode

```c
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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400270F0[25], qword_1400270F0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400270F0);
  }
}

```

## disassembly

```asm
0x1400167d0  sub     rsp, 38h
0x1400167d4  mov     eax, r8d
0x1400167d7  mov     r8d, edx
0x1400167da  btr     r8d, 1Fh; unsigned __int16
0x1400167df  test    ecx, ecx
0x1400167e1  jnz     short loc_14001683F
0x1400167e3  test    eax, eax
0x1400167e5  jnz     short loc_14001683F
0x1400167e7  test    r8d, r8d
0x1400167ea  jnz     short loc_14001683F
0x1400167ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1400167f3  jnz     short loc_14001683A
0x1400167f5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400167fc  test    rax, rax
0x1400167ff  jz      short loc_14001680A
0x140016801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016806  test    al, al
0x140016808  jnz     short loc_14001683A
0x14001680a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140016811  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140016816  test    al, al
0x140016818  jz      short loc_14001683A
0x14001681a  mov     rdx, cs:qword_1400270F0; SRWLock
0x140016821  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140016828  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14001682d  mov     rcx, cs:qword_1400270F0; SRWLock
0x140016834  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140016839  nop
0x14001683a  jmp     loc_1400168EB
0x14001683f  bt      r8d, 1Eh
0x140016844  jnb     short loc_14001685C
0x140016846  mov     r9d, eax; unsigned int
0x140016849  mov     edx, ecx; unsigned int
0x14001684b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140016852  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140016857  jmp     loc_1400168EB
0x14001685c  test    eax, eax
0x14001685e  jnz     short loc_1400168DA
0x140016860  cmp     r8d, 0FEh
0x140016867  jz      short loc_1400168DA
0x140016869  mov     [rsp+38h+var_18], 0
0x140016872  mov     dword ptr [rsp+38h+var_18], ecx
0x140016876  mov     word ptr [rsp+38h+var_18+4], r8w
0x14001687c  test    edx, edx
0x14001687e  jns     short loc_140016886
0x140016880  or      word ptr [rsp+38h+var_18+6], 1
0x140016886  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14001688d  test    rax, rax
0x140016890  jnz     short loc_1400168CE
0x140016892  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016899  test    rax, rax
0x14001689c  jnz     short loc_1400168B2
0x14001689e  lea     rcx, ModuleName; "ntdll.dll"
0x1400168a5  call    cs:__imp_GetModuleHandleW
0x1400168ab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400168b2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1400168b9  mov     rcx, rax; hModule
0x1400168bc  call    cs:__imp_GetProcAddress
0x1400168c2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1400168c9  test    rax, rax
0x1400168cc  jz      short loc_1400168EB
0x1400168ce  lea     rcx, [rsp+38h+var_18]
0x1400168d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400168d8  jmp     short loc_1400168EB
0x1400168da  mov     r9, rax
0x1400168dd  mov     edx, ecx
0x1400168df  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400168e6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1400168eb  add     rsp, 38h
0x1400168ef  retn
```
