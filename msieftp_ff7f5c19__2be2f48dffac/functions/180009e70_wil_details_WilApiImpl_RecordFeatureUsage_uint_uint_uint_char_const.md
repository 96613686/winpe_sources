# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009e70`
- end: `0x180009f9b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004f34`
- `0x1800073ac`
- `0x1800075b0`
- `0x180007d14`
- `0x180007f00`
- `0x180009e70`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f50`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f67`

## string_xrefs

- `0x180009f49`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180032198[25], qword_180032198);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180032198);
  }
}

```

## disassembly

```asm
0x180009e70  sub     rsp, 38h
0x180009e74  mov     eax, r8d
0x180009e77  mov     r8d, edx
0x180009e7a  btr     r8d, 1Fh; unsigned __int16
0x180009e7f  test    ecx, ecx
0x180009e81  jnz     short loc_180009EEA
0x180009e83  test    eax, eax
0x180009e85  jnz     short loc_180009EEA
0x180009e87  test    r8d, r8d
0x180009e8a  jnz     short loc_180009EEA
0x180009e8c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180009e93  jnz     loc_180009F96
0x180009e99  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009ea0  test    rax, rax
0x180009ea3  jz      short loc_180009EB2
0x180009ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eaa  test    al, al
0x180009eac  jnz     loc_180009F96
0x180009eb2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009eb9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009ebe  test    al, al
0x180009ec0  jz      loc_180009F96
0x180009ec6  mov     rdx, cs:qword_180032198; SRWLock
0x180009ecd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009ed4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180009ed9  mov     rcx, cs:qword_180032198; SRWLock
0x180009ee0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009ee5  jmp     loc_180009F96
0x180009eea  bt      r8d, 1Eh
0x180009eef  jnb     short loc_180009F07
0x180009ef1  mov     edx, ecx; unsigned int
0x180009ef3  mov     r9d, eax; unsigned int
0x180009ef6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009efd  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009f02  jmp     loc_180009F96
0x180009f07  test    eax, eax
0x180009f09  jnz     short loc_180009F85
0x180009f0b  cmp     r8d, 0FEh
0x180009f12  jz      short loc_180009F85
0x180009f14  mov     [rsp+38h+var_18], 0
0x180009f1d  mov     dword ptr [rsp+38h+var_18], ecx
0x180009f21  mov     word ptr [rsp+38h+var_18+4], r8w
0x180009f27  test    edx, edx
0x180009f29  jns     short loc_180009F31
0x180009f2b  or      word ptr [rsp+38h+var_18+6], 1
0x180009f31  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180009f38  test    rax, rax
0x180009f3b  jnz     short loc_180009F79
0x180009f3d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009f44  test    rax, rax
0x180009f47  jnz     short loc_180009F5D
0x180009f49  lea     rcx, ModuleName; "ntdll.dll"
0x180009f50  call    cs:__imp_GetModuleHandleW
0x180009f56  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009f5d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009f64  mov     rcx, rax; hModule
0x180009f67  call    cs:__imp_GetProcAddress
0x180009f6d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009f74  test    rax, rax
0x180009f77  jz      short loc_180009F96
0x180009f79  lea     rcx, [rsp+38h+var_18]
0x180009f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f83  jmp     short loc_180009F96
0x180009f85  mov     edx, ecx
0x180009f87  mov     r9, rax
0x180009f8a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009f91  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180009f96  add     rsp, 38h
0x180009f9a  retn
```
