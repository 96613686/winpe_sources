# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800079d0`
- end: `0x180007b12`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `322`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000419c`
- `0x180005820`
- `0x1800059d0`
- `0x180005d94`
- `0x180005f78`
- `0x1800079d0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ad3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ad3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ab6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ab6`

## string_xrefs

- `0x180007aaf`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&SRWLock[25], SRWLock);
    wil::details_abi::FeatureStateData::RecordUsage(SRWLock);
  }
}

```

## disassembly

```asm
0x1800079d0  sub     rsp, 38h
0x1800079d4  mov     eax, r8d
0x1800079d7  mov     r8d, edx
0x1800079da  btr     r8d, 1Fh; unsigned __int16
0x1800079df  test    ecx, ecx
0x1800079e1  jnz     short loc_180007A49
0x1800079e3  test    eax, eax
0x1800079e5  jnz     short loc_180007A49
0x1800079e7  test    r8d, r8d
0x1800079ea  jnz     short loc_180007A49
0x1800079ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800079f3  jnz     loc_180007B0C
0x1800079f9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007a00  test    rax, rax
0x180007a03  jz      short loc_180007A12
0x180007a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a0a  test    al, al
0x180007a0c  jnz     loc_180007B0C
0x180007a12  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007a19  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007a1e  test    al, al
0x180007a20  jz      loc_180007B0C
0x180007a26  mov     rdx, cs:SRWLock; SRWLock
0x180007a2d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007a34  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180007a39  mov     rcx, cs:SRWLock; SRWLock
0x180007a40  add     rsp, 38h
0x180007a44  jmp     ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007a49  bt      r8d, 1Eh
0x180007a4e  jnb     short loc_180007A65
0x180007a50  mov     edx, ecx; unsigned int
0x180007a52  mov     r9d, eax; unsigned int
0x180007a55  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180007a5c  add     rsp, 38h
0x180007a60  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180007a65  test    eax, eax
0x180007a67  jnz     loc_180007AFB
0x180007a6d  cmp     r8d, 0FEh
0x180007a74  jz      loc_180007AFB
0x180007a7a  mov     [rsp+38h+var_18], 0
0x180007a83  mov     dword ptr [rsp+38h+var_18], ecx
0x180007a87  mov     word ptr [rsp+38h+var_18+4], r8w
0x180007a8d  test    edx, edx
0x180007a8f  jns     short loc_180007A97
0x180007a91  or      word ptr [rsp+38h+var_18+6], 1
0x180007a97  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180007a9e  test    rax, rax
0x180007aa1  jnz     short loc_180007AEB
0x180007aa3  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007aaa  test    rax, rax
0x180007aad  jnz     short loc_180007AC9
0x180007aaf  lea     rcx, ModuleName; "ntdll.dll"
0x180007ab6  call    cs:__imp_GetModuleHandleW
0x180007abd  nop     dword ptr [rax+rax+00h]
0x180007ac2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007ac9  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180007ad0  mov     rcx, rax; hModule
0x180007ad3  call    cs:__imp_GetProcAddress
0x180007ada  nop     dword ptr [rax+rax+00h]
0x180007adf  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180007ae6  test    rax, rax
0x180007ae9  jz      short loc_180007B0C
0x180007aeb  lea     rcx, [rsp+38h+var_18]
0x180007af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af5  add     rsp, 38h
0x180007af9  retn
0x180007afb  mov     edx, ecx
0x180007afd  mov     r9, rax
0x180007b00  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007b07  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180007b0c  add     rsp, 38h
0x180007b10  retn
```
