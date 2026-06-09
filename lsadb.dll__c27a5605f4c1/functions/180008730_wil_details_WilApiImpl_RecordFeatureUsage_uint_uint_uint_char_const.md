# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180008730`
- end: `0x18000885b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800045b4`
- `0x180006474`
- `0x180006678`
- `0x180006c14`
- `0x180006e00`
- `0x180008730`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008810`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008810`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008827`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008827`

## string_xrefs

- `0x180008809`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180047508[25], qword_180047508);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180047508);
  }
}

```

## disassembly

```asm
0x180008730  sub     rsp, 38h
0x180008734  mov     eax, r8d
0x180008737  mov     r8d, edx
0x18000873a  btr     r8d, 1Fh; unsigned __int16
0x18000873f  test    ecx, ecx
0x180008741  jnz     short loc_1800087AA
0x180008743  test    eax, eax
0x180008745  jnz     short loc_1800087AA
0x180008747  test    r8d, r8d
0x18000874a  jnz     short loc_1800087AA
0x18000874c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180008753  jnz     loc_180008856
0x180008759  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008760  test    rax, rax
0x180008763  jz      short loc_180008772
0x180008765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000876a  test    al, al
0x18000876c  jnz     loc_180008856
0x180008772  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180008779  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000877e  test    al, al
0x180008780  jz      loc_180008856
0x180008786  mov     rdx, cs:qword_180047508; SRWLock
0x18000878d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008794  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180008799  mov     rcx, cs:qword_180047508; SRWLock
0x1800087a0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800087a5  jmp     loc_180008856
0x1800087aa  bt      r8d, 1Eh
0x1800087af  jnb     short loc_1800087C7
0x1800087b1  mov     edx, ecx; unsigned int
0x1800087b3  mov     r9d, eax; unsigned int
0x1800087b6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800087bd  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800087c2  jmp     loc_180008856
0x1800087c7  test    eax, eax
0x1800087c9  jnz     short loc_180008845
0x1800087cb  cmp     r8d, 0FEh
0x1800087d2  jz      short loc_180008845
0x1800087d4  mov     [rsp+38h+var_18], 0
0x1800087dd  mov     dword ptr [rsp+38h+var_18], ecx
0x1800087e1  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800087e7  test    edx, edx
0x1800087e9  jns     short loc_1800087F1
0x1800087eb  or      word ptr [rsp+38h+var_18+6], 1
0x1800087f1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800087f8  test    rax, rax
0x1800087fb  jnz     short loc_180008839
0x1800087fd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008804  test    rax, rax
0x180008807  jnz     short loc_18000881D
0x180008809  lea     rcx, ModuleName; "ntdll.dll"
0x180008810  call    cs:__imp_GetModuleHandleW
0x180008816  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000881d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008824  mov     rcx, rax; hModule
0x180008827  call    cs:__imp_GetProcAddress
0x18000882d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008834  test    rax, rax
0x180008837  jz      short loc_180008856
0x180008839  lea     rcx, [rsp+38h+var_18]
0x18000883e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008843  jmp     short loc_180008856
0x180008845  mov     edx, ecx
0x180008847  mov     r9, rax
0x18000884a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008851  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180008856  add     rsp, 38h
0x18000885a  retn
```
