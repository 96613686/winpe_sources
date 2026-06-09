# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000c040`
- end: `0x18000c160`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180005844`
- `0x180007db4`
- `0x180007fb8`
- `0x180008724`
- `0x180008920`
- `0x18000c040`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c115`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c115`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c12c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c12c`

## string_xrefs

- `0x18000c10e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001E3C8[25], qword_18001E3C8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001E3C8);
  }
}

```

## disassembly

```asm
0x18000c040  sub     rsp, 38h
0x18000c044  mov     eax, r8d
0x18000c047  mov     r8d, edx
0x18000c04a  btr     r8d, 1Fh; unsigned __int16
0x18000c04f  test    ecx, ecx
0x18000c051  jnz     short loc_18000C0AF
0x18000c053  test    eax, eax
0x18000c055  jnz     short loc_18000C0AF
0x18000c057  test    r8d, r8d
0x18000c05a  jnz     short loc_18000C0AF
0x18000c05c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000c063  jnz     short loc_18000C0AA
0x18000c065  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c06c  test    rax, rax
0x18000c06f  jz      short loc_18000C07A
0x18000c071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c076  test    al, al
0x18000c078  jnz     short loc_18000C0AA
0x18000c07a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c081  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000c086  test    al, al
0x18000c088  jz      short loc_18000C0AA
0x18000c08a  mov     rdx, cs:qword_18001E3C8; SRWLock
0x18000c091  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000c098  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000c09d  mov     rcx, cs:qword_18001E3C8; SRWLock
0x18000c0a4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c0a9  nop
0x18000c0aa  jmp     loc_18000C15B
0x18000c0af  bt      r8d, 1Eh
0x18000c0b4  jnb     short loc_18000C0CC
0x18000c0b6  mov     r9d, eax; unsigned int
0x18000c0b9  mov     edx, ecx; unsigned int
0x18000c0bb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000c0c2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000c0c7  jmp     loc_18000C15B
0x18000c0cc  test    eax, eax
0x18000c0ce  jnz     short loc_18000C14A
0x18000c0d0  cmp     r8d, 0FEh
0x18000c0d7  jz      short loc_18000C14A
0x18000c0d9  mov     [rsp+38h+var_18], 0
0x18000c0e2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000c0e6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000c0ec  test    edx, edx
0x18000c0ee  jns     short loc_18000C0F6
0x18000c0f0  or      word ptr [rsp+38h+var_18+6], 1
0x18000c0f6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c0fd  test    rax, rax
0x18000c100  jnz     short loc_18000C13E
0x18000c102  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c109  test    rax, rax
0x18000c10c  jnz     short loc_18000C122
0x18000c10e  lea     rcx, ModuleName; "ntdll.dll"
0x18000c115  call    cs:__imp_GetModuleHandleW
0x18000c11b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c122  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c129  mov     rcx, rax; hModule
0x18000c12c  call    cs:__imp_GetProcAddress
0x18000c132  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c139  test    rax, rax
0x18000c13c  jz      short loc_18000C15B
0x18000c13e  lea     rcx, [rsp+38h+var_18]
0x18000c143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c148  jmp     short loc_18000C15B
0x18000c14a  mov     r9, rax
0x18000c14d  mov     edx, ecx
0x18000c14f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c156  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000c15b  add     rsp, 38h
0x18000c15f  retn
```
