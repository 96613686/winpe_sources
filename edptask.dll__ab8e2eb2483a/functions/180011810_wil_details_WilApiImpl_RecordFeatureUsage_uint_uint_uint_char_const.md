# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180011810`
- end: `0x180011930`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180008400`
- `0x18000edc4`
- `0x18000ef24`
- `0x18000f624`
- `0x18000f7e0`
- `0x180011810`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800118e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800118e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800118fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800118fc`

## string_xrefs

- `0x1800118de`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001D078[25], qword_18001D078);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001D078);
  }
}

```

## disassembly

```asm
0x180011810  sub     rsp, 38h
0x180011814  mov     eax, r8d
0x180011817  mov     r8d, edx
0x18001181a  btr     r8d, 1Fh; unsigned __int16
0x18001181f  test    ecx, ecx
0x180011821  jnz     short loc_18001187F
0x180011823  test    eax, eax
0x180011825  jnz     short loc_18001187F
0x180011827  test    r8d, r8d
0x18001182a  jnz     short loc_18001187F
0x18001182c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180011833  jnz     short loc_18001187A
0x180011835  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001183c  test    rax, rax
0x18001183f  jz      short loc_18001184A
0x180011841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011846  test    al, al
0x180011848  jnz     short loc_18001187A
0x18001184a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180011851  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180011856  test    al, al
0x180011858  jz      short loc_18001187A
0x18001185a  mov     rdx, cs:qword_18001D078; SRWLock
0x180011861  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180011868  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001186d  mov     rcx, cs:qword_18001D078; SRWLock
0x180011874  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180011879  nop
0x18001187a  jmp     loc_18001192B
0x18001187f  bt      r8d, 1Eh
0x180011884  jnb     short loc_18001189C
0x180011886  mov     r9d, eax; unsigned int
0x180011889  mov     edx, ecx; unsigned int
0x18001188b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180011892  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180011897  jmp     loc_18001192B
0x18001189c  test    eax, eax
0x18001189e  jnz     short loc_18001191A
0x1800118a0  cmp     r8d, 0FEh
0x1800118a7  jz      short loc_18001191A
0x1800118a9  mov     [rsp+38h+var_18], 0
0x1800118b2  mov     dword ptr [rsp+38h+var_18], ecx
0x1800118b6  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800118bc  test    edx, edx
0x1800118be  jns     short loc_1800118C6
0x1800118c0  or      word ptr [rsp+38h+var_18+6], 1
0x1800118c6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800118cd  test    rax, rax
0x1800118d0  jnz     short loc_18001190E
0x1800118d2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800118d9  test    rax, rax
0x1800118dc  jnz     short loc_1800118F2
0x1800118de  lea     rcx, ModuleName; "ntdll.dll"
0x1800118e5  call    cs:__imp_GetModuleHandleW
0x1800118eb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800118f2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800118f9  mov     rcx, rax; hModule
0x1800118fc  call    cs:__imp_GetProcAddress
0x180011902  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180011909  test    rax, rax
0x18001190c  jz      short loc_18001192B
0x18001190e  lea     rcx, [rsp+38h+var_18]
0x180011913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011918  jmp     short loc_18001192B
0x18001191a  mov     r9, rax
0x18001191d  mov     edx, ecx
0x18001191f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011926  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001192b  add     rsp, 38h
0x18001192f  retn
```
