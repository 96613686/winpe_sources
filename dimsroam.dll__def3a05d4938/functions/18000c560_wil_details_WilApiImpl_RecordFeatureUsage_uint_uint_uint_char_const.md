# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000c560`
- end: `0x18000c68b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180009154`
- `0x18000a734`
- `0x18000a89c`
- `0x18000ac64`
- `0x18000ae1c`
- `0x18000c560`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c640`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c640`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c657`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c657`

## string_xrefs

- `0x18000c639`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180013038[25], qword_180013038);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180013038);
  }
}

```

## disassembly

```asm
0x18000c560  sub     rsp, 38h
0x18000c564  mov     eax, r8d
0x18000c567  mov     r8d, edx
0x18000c56a  btr     r8d, 1Fh; unsigned __int16
0x18000c56f  test    ecx, ecx
0x18000c571  jnz     short loc_18000C5DA
0x18000c573  test    eax, eax
0x18000c575  jnz     short loc_18000C5DA
0x18000c577  test    r8d, r8d
0x18000c57a  jnz     short loc_18000C5DA
0x18000c57c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000c583  jnz     loc_18000C686
0x18000c589  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c590  test    rax, rax
0x18000c593  jz      short loc_18000C5A2
0x18000c595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c59a  test    al, al
0x18000c59c  jnz     loc_18000C686
0x18000c5a2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c5a9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000c5ae  test    al, al
0x18000c5b0  jz      loc_18000C686
0x18000c5b6  mov     rdx, cs:qword_180013038; SRWLock
0x18000c5bd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000c5c4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000c5c9  mov     rcx, cs:qword_180013038; SRWLock
0x18000c5d0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c5d5  jmp     loc_18000C686
0x18000c5da  bt      r8d, 1Eh
0x18000c5df  jnb     short loc_18000C5F7
0x18000c5e1  mov     edx, ecx; unsigned int
0x18000c5e3  mov     r9d, eax; unsigned int
0x18000c5e6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000c5ed  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000c5f2  jmp     loc_18000C686
0x18000c5f7  test    eax, eax
0x18000c5f9  jnz     short loc_18000C675
0x18000c5fb  cmp     r8d, 0FEh
0x18000c602  jz      short loc_18000C675
0x18000c604  mov     [rsp+38h+var_18], 0
0x18000c60d  mov     dword ptr [rsp+38h+var_18], ecx
0x18000c611  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000c617  test    edx, edx
0x18000c619  jns     short loc_18000C621
0x18000c61b  or      word ptr [rsp+38h+var_18+6], 1
0x18000c621  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c628  test    rax, rax
0x18000c62b  jnz     short loc_18000C669
0x18000c62d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c634  test    rax, rax
0x18000c637  jnz     short loc_18000C64D
0x18000c639  lea     rcx, ModuleName; "ntdll.dll"
0x18000c640  call    cs:__imp_GetModuleHandleW
0x18000c646  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c64d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c654  mov     rcx, rax; hModule
0x18000c657  call    cs:__imp_GetProcAddress
0x18000c65d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c664  test    rax, rax
0x18000c667  jz      short loc_18000C686
0x18000c669  lea     rcx, [rsp+38h+var_18]
0x18000c66e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c673  jmp     short loc_18000C686
0x18000c675  mov     edx, ecx
0x18000c677  mov     r9, rax
0x18000c67a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c681  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000c686  add     rsp, 38h
0x18000c68a  retn
```
