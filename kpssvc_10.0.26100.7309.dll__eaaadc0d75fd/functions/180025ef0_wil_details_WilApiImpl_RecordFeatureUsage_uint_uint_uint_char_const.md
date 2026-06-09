# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180025ef0`
- end: `0x18002602a`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `314`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18001d064`
- `0x18002336c`
- `0x1800235e0`
- `0x180023c84`
- `0x180023eb4`
- `0x180025ef0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025fe8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025fe8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025fcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025fcb`

## string_xrefs

- `0x180025fc4`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // edx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (v4 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        v4,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)v4;
      if ( a2 < 0 )
        HIWORD(v8) |= 1u;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_19;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18003A068[25], qword_18003A068);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18003A068);
  }
}

```

## disassembly

```asm
0x180025ef0  sub     rsp, 38h
0x180025ef4  mov     eax, edx
0x180025ef6  btr     edx, 1Fh
0x180025efa  test    ecx, ecx
0x180025efc  jnz     short loc_180025F63
0x180025efe  test    r8d, r8d
0x180025f01  jnz     short loc_180025F63
0x180025f03  test    edx, edx
0x180025f05  jnz     short loc_180025F63
0x180025f07  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x180025f0d  jnz     loc_180026024
0x180025f13  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180025f1a  test    rax, rax
0x180025f1d  jz      short loc_180025F2C
0x180025f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f24  test    al, al
0x180025f26  jnz     loc_180026024
0x180025f2c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180025f33  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180025f38  test    al, al
0x180025f3a  jz      loc_180026024
0x180025f40  mov     rdx, cs:qword_18003A068; SRWLock
0x180025f47  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180025f4e  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180025f53  mov     rcx, cs:qword_18003A068; SRWLock
0x180025f5a  add     rsp, 38h
0x180025f5e  jmp     ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180025f63  bt      edx, 1Eh
0x180025f67  jnb     short loc_180025F82
0x180025f69  mov     r9d, r8d; unsigned int
0x180025f6c  movzx   r8d, dx; unsigned __int16
0x180025f70  mov     edx, ecx; unsigned int
0x180025f72  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180025f79  add     rsp, 38h
0x180025f7d  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180025f82  test    r8d, r8d
0x180025f85  jnz     loc_180026010
0x180025f8b  cmp     edx, 0FEh
0x180025f91  jz      short loc_180026010
0x180025f93  and     [rsp+38h+var_18], 0
0x180025f99  mov     dword ptr [rsp+38h+var_18], ecx
0x180025f9d  mov     word ptr [rsp+38h+var_18+4], dx
0x180025fa2  test    eax, eax
0x180025fa4  jns     short loc_180025FAC
0x180025fa6  or      word ptr [rsp+38h+var_18+6], 1
0x180025fac  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180025fb3  test    rax, rax
0x180025fb6  jnz     short loc_180026000
0x180025fb8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025fbf  test    rax, rax
0x180025fc2  jnz     short loc_180025FDE
0x180025fc4  lea     rcx, ModuleName; "ntdll.dll"
0x180025fcb  call    cs:__imp_GetModuleHandleW
0x180025fd2  nop     dword ptr [rax+rax+00h]
0x180025fd7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025fde  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180025fe5  mov     rcx, rax; hModule
0x180025fe8  call    cs:__imp_GetProcAddress
0x180025fef  nop     dword ptr [rax+rax+00h]
0x180025ff4  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180025ffb  test    rax, rax
0x180025ffe  jz      short loc_180026024
0x180026000  lea     rcx, [rsp+38h+var_18]
0x180026005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002600a  add     rsp, 38h
0x18002600e  retn
0x180026010  mov     r9d, r8d
0x180026013  mov     r8d, edx
0x180026016  mov     edx, ecx
0x180026018  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18002601f  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180026024  add     rsp, 38h
0x180026028  retn
```
