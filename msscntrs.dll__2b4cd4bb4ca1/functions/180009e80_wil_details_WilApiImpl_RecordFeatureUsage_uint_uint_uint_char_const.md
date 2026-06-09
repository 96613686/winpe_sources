# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009e80`
- end: `0x180009fa0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180005b64`
- `0x180007304`
- `0x180007508`
- `0x180007af4`
- `0x180007cf0`
- `0x180009e80`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f55`

## string_xrefs

- `0x180009f4e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180021178[25], qword_180021178);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180021178);
  }
}

```

## disassembly

```asm
0x180009e80  sub     rsp, 38h
0x180009e84  mov     eax, r8d
0x180009e87  mov     r8d, edx
0x180009e8a  btr     r8d, 1Fh; unsigned __int16
0x180009e8f  test    ecx, ecx
0x180009e91  jnz     short loc_180009EEF
0x180009e93  test    eax, eax
0x180009e95  jnz     short loc_180009EEF
0x180009e97  test    r8d, r8d
0x180009e9a  jnz     short loc_180009EEF
0x180009e9c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180009ea3  jnz     short loc_180009EEA
0x180009ea5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009eac  test    rax, rax
0x180009eaf  jz      short loc_180009EBA
0x180009eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eb6  test    al, al
0x180009eb8  jnz     short loc_180009EEA
0x180009eba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009ec1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009ec6  test    al, al
0x180009ec8  jz      short loc_180009EEA
0x180009eca  mov     rdx, cs:qword_180021178; SRWLock
0x180009ed1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009ed8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180009edd  mov     rcx, cs:qword_180021178; SRWLock
0x180009ee4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009ee9  nop
0x180009eea  jmp     loc_180009F9B
0x180009eef  bt      r8d, 1Eh
0x180009ef4  jnb     short loc_180009F0C
0x180009ef6  mov     r9d, eax; unsigned int
0x180009ef9  mov     edx, ecx; unsigned int
0x180009efb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009f02  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009f07  jmp     loc_180009F9B
0x180009f0c  test    eax, eax
0x180009f0e  jnz     short loc_180009F8A
0x180009f10  cmp     r8d, 0FEh
0x180009f17  jz      short loc_180009F8A
0x180009f19  mov     [rsp+38h+var_18], 0
0x180009f22  mov     dword ptr [rsp+38h+var_18], ecx
0x180009f26  mov     word ptr [rsp+38h+var_18+4], r8w
0x180009f2c  test    edx, edx
0x180009f2e  jns     short loc_180009F36
0x180009f30  or      word ptr [rsp+38h+var_18+6], 1
0x180009f36  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180009f3d  test    rax, rax
0x180009f40  jnz     short loc_180009F7E
0x180009f42  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009f49  test    rax, rax
0x180009f4c  jnz     short loc_180009F62
0x180009f4e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180009f55  call    cs:__imp_GetModuleHandleW
0x180009f5b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009f62  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009f69  mov     rcx, rax; hModule
0x180009f6c  call    cs:__imp_GetProcAddress
0x180009f72  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009f79  test    rax, rax
0x180009f7c  jz      short loc_180009F9B
0x180009f7e  lea     rcx, [rsp+38h+var_18]
0x180009f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f88  jmp     short loc_180009F9B
0x180009f8a  mov     r9, rax
0x180009f8d  mov     edx, ecx
0x180009f8f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009f96  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180009f9b  add     rsp, 38h
0x180009f9f  retn
```
