# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180022630`
- end: `0x180022769`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180016c58`
- `0x180020a54`
- `0x180020c50`
- `0x180020fd8`
- `0x18002117c`
- `0x180022630`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002272a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002272a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002270d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002270d`

## string_xrefs

- `0x180022706`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800496B8[25], qword_1800496B8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800496B8);
  }
}

```

## disassembly

```asm
0x180022630  sub     rsp, 38h
0x180022634  mov     eax, r8d
0x180022637  mov     r8d, edx
0x18002263a  btr     r8d, 1Fh; unsigned __int16
0x18002263f  test    ecx, ecx
0x180022641  jnz     short loc_1800226A0
0x180022643  test    eax, eax
0x180022645  jnz     short loc_1800226A0
0x180022647  test    r8d, r8d
0x18002264a  jnz     short loc_1800226A0
0x18002264c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180022653  jnz     short loc_18002269A
0x180022655  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002265c  test    rax, rax
0x18002265f  jz      short loc_18002266A
0x180022661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022666  test    al, al
0x180022668  jnz     short loc_18002269A
0x18002266a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180022671  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180022676  test    al, al
0x180022678  jz      short loc_18002269A
0x18002267a  mov     rdx, cs:qword_1800496B8; SRWLock
0x180022681  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180022688  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18002268d  mov     rcx, cs:qword_1800496B8; SRWLock
0x180022694  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180022699  nop
0x18002269a  add     rsp, 38h
0x18002269e  retn
0x1800226a0  bt      r8d, 1Eh
0x1800226a5  jnb     short loc_1800226BC
0x1800226a7  mov     r9d, eax; unsigned int
0x1800226aa  mov     edx, ecx; unsigned int
0x1800226ac  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800226b3  add     rsp, 38h
0x1800226b7  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800226bc  test    eax, eax
0x1800226be  jnz     loc_180022752
0x1800226c4  cmp     r8d, 0FEh
0x1800226cb  jz      loc_180022752
0x1800226d1  mov     [rsp+38h+var_18], 0
0x1800226da  mov     dword ptr [rsp+38h+var_18], ecx
0x1800226de  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800226e4  test    edx, edx
0x1800226e6  jns     short loc_1800226EE
0x1800226e8  or      word ptr [rsp+38h+var_18+6], 1
0x1800226ee  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800226f5  test    rax, rax
0x1800226f8  jnz     short loc_180022742
0x1800226fa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022701  test    rax, rax
0x180022704  jnz     short loc_180022720
0x180022706  lea     rcx, ModuleName; "ntdll.dll"
0x18002270d  call    cs:__imp_GetModuleHandleW
0x180022714  nop     dword ptr [rax+rax+00h]
0x180022719  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022720  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180022727  mov     rcx, rax; hModule
0x18002272a  call    cs:__imp_GetProcAddress
0x180022731  nop     dword ptr [rax+rax+00h]
0x180022736  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18002273d  test    rax, rax
0x180022740  jz      short loc_180022763
0x180022742  lea     rcx, [rsp+38h+var_18]
0x180022747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002274c  add     rsp, 38h
0x180022750  retn
0x180022752  mov     r9, rax
0x180022755  mov     edx, ecx
0x180022757  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18002275e  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180022763  add     rsp, 38h
0x180022767  retn
```
