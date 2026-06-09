# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1400171f0`
- end: `0x14001731b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140013de4`
- `0x1400153c4`
- `0x14001552c`
- `0x1400158f4`
- `0x140015aac`
- `0x1400171f0`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400172e7`
- `KERNEL32!GetProcAddress` at `0x1400172e7`
- `KERNEL32!GetModuleHandleW` at `0x1400172d0`
- `KERNEL32!GetModuleHandleW` at `0x1400172d0`

## string_xrefs

- `0x1400172c9`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140020168[25], qword_140020168);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140020168);
  }
}

```

## disassembly

```asm
0x1400171f0  sub     rsp, 38h
0x1400171f4  mov     eax, r8d
0x1400171f7  mov     r8d, edx
0x1400171fa  btr     r8d, 1Fh; unsigned __int16
0x1400171ff  test    ecx, ecx
0x140017201  jnz     short loc_14001726A
0x140017203  test    eax, eax
0x140017205  jnz     short loc_14001726A
0x140017207  test    r8d, r8d
0x14001720a  jnz     short loc_14001726A
0x14001720c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140017213  jnz     loc_140017316
0x140017219  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140017220  test    rax, rax
0x140017223  jz      short loc_140017232
0x140017225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001722a  test    al, al
0x14001722c  jnz     loc_140017316
0x140017232  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140017239  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14001723e  test    al, al
0x140017240  jz      loc_140017316
0x140017246  mov     rdx, cs:qword_140020168; SRWLock
0x14001724d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140017254  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x140017259  mov     rcx, cs:qword_140020168; SRWLock
0x140017260  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140017265  jmp     loc_140017316
0x14001726a  bt      r8d, 1Eh
0x14001726f  jnb     short loc_140017287
0x140017271  mov     edx, ecx; unsigned int
0x140017273  mov     r9d, eax; unsigned int
0x140017276  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14001727d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140017282  jmp     loc_140017316
0x140017287  test    eax, eax
0x140017289  jnz     short loc_140017305
0x14001728b  cmp     r8d, 0FEh
0x140017292  jz      short loc_140017305
0x140017294  mov     [rsp+38h+var_18], 0
0x14001729d  mov     dword ptr [rsp+38h+var_18], ecx
0x1400172a1  mov     word ptr [rsp+38h+var_18+4], r8w
0x1400172a7  test    edx, edx
0x1400172a9  jns     short loc_1400172B1
0x1400172ab  or      word ptr [rsp+38h+var_18+6], 1
0x1400172b1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1400172b8  test    rax, rax
0x1400172bb  jnz     short loc_1400172F9
0x1400172bd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400172c4  test    rax, rax
0x1400172c7  jnz     short loc_1400172DD
0x1400172c9  lea     rcx, ModuleName; "ntdll.dll"
0x1400172d0  call    cs:__imp_GetModuleHandleW
0x1400172d6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400172dd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1400172e4  mov     rcx, rax; hModule
0x1400172e7  call    cs:__imp_GetProcAddress
0x1400172ed  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1400172f4  test    rax, rax
0x1400172f7  jz      short loc_140017316
0x1400172f9  lea     rcx, [rsp+38h+var_18]
0x1400172fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017303  jmp     short loc_140017316
0x140017305  mov     edx, ecx
0x140017307  mov     r9, rax
0x14001730a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140017311  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140017316  add     rsp, 38h
0x14001731a  retn
```
