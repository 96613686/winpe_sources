# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000a9d0`
- end: `0x14000aaf0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140006930`
- `0x140008284`
- `0x14000849c`
- `0x140008884`
- `0x140008a40`
- `0x14000a9d0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000aaa5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000aaa5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000aabc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000aabc`

## string_xrefs

- `0x14000aa9e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_14001D050[25], qword_14001D050);
    wil::details_abi::FeatureStateData::RecordUsage(qword_14001D050);
  }
}

```

## disassembly

```asm
0x14000a9d0  sub     rsp, 38h
0x14000a9d4  mov     eax, r8d
0x14000a9d7  mov     r8d, edx
0x14000a9da  btr     r8d, 1Fh; unsigned __int16
0x14000a9df  test    ecx, ecx
0x14000a9e1  jnz     short loc_14000AA3F
0x14000a9e3  test    eax, eax
0x14000a9e5  jnz     short loc_14000AA3F
0x14000a9e7  test    r8d, r8d
0x14000a9ea  jnz     short loc_14000AA3F
0x14000a9ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000a9f3  jnz     short loc_14000AA3A
0x14000a9f5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a9fc  test    rax, rax
0x14000a9ff  jz      short loc_14000AA0A
0x14000aa01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa06  test    al, al
0x14000aa08  jnz     short loc_14000AA3A
0x14000aa0a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000aa11  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000aa16  test    al, al
0x14000aa18  jz      short loc_14000AA3A
0x14000aa1a  mov     rdx, cs:qword_14001D050; SRWLock
0x14000aa21  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000aa28  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000aa2d  mov     rcx, cs:qword_14001D050; SRWLock
0x14000aa34  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000aa39  nop
0x14000aa3a  jmp     loc_14000AAEB
0x14000aa3f  bt      r8d, 1Eh
0x14000aa44  jnb     short loc_14000AA5C
0x14000aa46  mov     r9d, eax; unsigned int
0x14000aa49  mov     edx, ecx; unsigned int
0x14000aa4b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000aa52  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000aa57  jmp     loc_14000AAEB
0x14000aa5c  test    eax, eax
0x14000aa5e  jnz     short loc_14000AADA
0x14000aa60  cmp     r8d, 0FEh
0x14000aa67  jz      short loc_14000AADA
0x14000aa69  mov     [rsp+38h+var_18], 0
0x14000aa72  mov     dword ptr [rsp+38h+var_18], ecx
0x14000aa76  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000aa7c  test    edx, edx
0x14000aa7e  jns     short loc_14000AA86
0x14000aa80  or      word ptr [rsp+38h+var_18+6], 1
0x14000aa86  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000aa8d  test    rax, rax
0x14000aa90  jnz     short loc_14000AACE
0x14000aa92  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000aa99  test    rax, rax
0x14000aa9c  jnz     short loc_14000AAB2
0x14000aa9e  lea     rcx, ModuleName; "ntdll.dll"
0x14000aaa5  call    cs:__imp_GetModuleHandleW
0x14000aaab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000aab2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000aab9  mov     rcx, rax; hModule
0x14000aabc  call    cs:__imp_GetProcAddress
0x14000aac2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000aac9  test    rax, rax
0x14000aacc  jz      short loc_14000AAEB
0x14000aace  lea     rcx, [rsp+38h+var_18]
0x14000aad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aad8  jmp     short loc_14000AAEB
0x14000aada  mov     r9, rax
0x14000aadd  mov     edx, ecx
0x14000aadf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000aae6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000aaeb  add     rsp, 38h
0x14000aaef  retn
```
