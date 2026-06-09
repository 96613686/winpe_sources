# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180012910`
- end: `0x180012b53`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `579`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180002d90`
- `0x180004980`
- `0x180005750`
- `0x180006cf0`
- `0x18000b5e0`
- `0x180012910`
- `0x180015e30`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012aec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012aec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800129d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800129d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012a8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012a4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012a4e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012a77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012a77`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012a37`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012a37`

## string_xrefs

- `0x180012ae5`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  DWORD v4; // esi
  unsigned int v5; // ebx
  struct _TP_TIMER *v6; // rcx
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v12; // [rsp+28h] [rbp-10h]

  v4 = (unsigned int)this;
  v5 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v5 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      if ( wil::details::g_featureStateManager
        && !wil::details::g_processShutdownInProgress
        && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
      {
        AcquireSRWLockExclusive(&stru_1800ADB38);
        pftDueTime.dwLowDateTime = v4;
        pftDueTime.dwHighDateTime = (unsigned __int16)v5;
        v12 = a3;
        wil::details_abi::heap_buffer::push_back(
          (wil::details_abi::heap_buffer *)((char *)&xmmword_1800ADBF0 + 8),
          &pftDueTime,
          0xCu);
        if ( !(_BYTE)word_1800ADB50 )
        {
          v6 = (struct _TP_TIMER *)*((_QWORD *)&xmmword_1800ADB40 + 1);
          if ( *((_QWORD *)&xmmword_1800ADB40 + 1)
            || (LastError = GetLastError(),
                ThreadpoolTimer = CreateThreadpoolTimer(
                                    _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                                    &wil::details::g_featureStateManager,
                                    0),
                wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
                  (struct _TP_TIMER **)&xmmword_1800ADB40 + 1,
                  ThreadpoolTimer),
                SetLastError(LastError),
                (v6 = (struct _TP_TIMER *)*((_QWORD *)&xmmword_1800ADB40 + 1)) != 0) )
          {
            pftDueTime = (struct _FILETIME)-50000000LL;
            SetThreadpoolTimer(v6, &pftDueTime, 0, 0x4E2u);
            LOBYTE(word_1800ADB50) = 1;
          }
        }
        ReleaseSRWLockExclusive(&stru_1800ADB38);
      }
    }
    else if ( a3 || v5 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v5,
        a3);
    }
    else
    {
      pftDueTime.dwLowDateTime = (unsigned int)this;
      pftDueTime.dwHighDateTime = (unsigned __int16)a2;
      if ( a2 < 0 )
        HIWORD(pftDueTime.dwHighDateTime) |= 1u;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_28;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_28:
        ((void (__fastcall *)(struct _FILETIME *))ProcAddress)(&pftDueTime);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800ADB28[25], qword_1800ADB28);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800ADB28);
  }
}

```

## disassembly

```asm
0x180012910  mov     [rsp+arg_0], rbx
0x180012915  mov     [rsp+arg_8], rsi
0x18001291a  push    rdi
0x18001291b  sub     rsp, 30h
0x18001291f  mov     edi, r8d
0x180012922  mov     esi, ecx
0x180012924  mov     ebx, edx
0x180012926  btr     ebx, 1Fh
0x18001292a  test    ecx, ecx
0x18001292c  jnz     short loc_180012994
0x18001292e  test    r8d, r8d
0x180012931  jnz     short loc_180012994
0x180012933  test    ebx, ebx
0x180012935  jnz     short loc_180012994
0x180012937  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x18001293d  jnz     loc_180012A92
0x180012943  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001294a  test    rax, rax
0x18001294d  jz      short loc_18001295C
0x18001294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012954  test    al, al
0x180012956  jnz     loc_180012A92
0x18001295c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180012963  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180012968  test    al, al
0x18001296a  jz      loc_180012A92
0x180012970  mov     rdx, cs:qword_1800ADB28; SRWLock
0x180012977  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001297e  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180012983  mov     rcx, cs:qword_1800ADB28; SRWLock
0x18001298a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001298f  jmp     loc_180012A92
0x180012994  bt      ebx, 1Eh
0x180012998  jnb     loc_180012AA2
0x18001299e  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800129a5  jz      loc_180012A92
0x1800129ab  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800129b2  jnz     loc_180012A92
0x1800129b8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800129bf  test    rax, rax
0x1800129c2  jz      short loc_1800129D1
0x1800129c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129c9  test    al, al
0x1800129cb  jnz     loc_180012A92
0x1800129d1  lea     rcx, stru_1800ADB38; SRWLock
0x1800129d8  call    cs:__imp_AcquireSRWLockExclusive
0x1800129de  xor     eax, eax
0x1800129e0  mov     word ptr [rsp+38h+pftDueTime.dwHighDateTime+2], ax
0x1800129e5  mov     [rsp+38h+pftDueTime.dwLowDateTime], esi
0x1800129e9  mov     word ptr [rsp+38h+pftDueTime.dwHighDateTime], bx
0x1800129ee  mov     [rsp+38h+var_10], edi
0x1800129f2  mov     r8d, 0Ch; unsigned __int64
0x1800129f8  lea     rdx, [rsp+38h+pftDueTime]; void *
0x1800129fd  lea     rcx, xmmword_1800ADBF0+8; this
0x180012a04  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180012a09  cmp     byte ptr cs:word_1800ADB50, 0
0x180012a10  jnz     short loc_180012A84
0x180012a12  mov     rcx, qword ptr cs:xmmword_1800ADB40+8
0x180012a19  test    rcx, rcx
0x180012a1c  jnz     short loc_180012A60
0x180012a1e  call    cs:__imp_GetLastError
0x180012a24  mov     ebx, eax
0x180012a26  xor     r8d, r8d; pcbe
0x180012a29  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180012a30  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180012a37  call    cs:__imp_CreateThreadpoolTimer
0x180012a3d  mov     rdx, rax
0x180012a40  lea     rcx, xmmword_1800ADB40+8
0x180012a47  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180012a4c  mov     ecx, ebx; dwErrCode
0x180012a4e  call    cs:__imp_SetLastError
0x180012a54  mov     rcx, qword ptr cs:xmmword_1800ADB40+8; pti
0x180012a5b  test    rcx, rcx
0x180012a5e  jz      short loc_180012A84
0x180012a60  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180012a69  mov     r9d, 4E2h; msWindowLength
0x180012a6f  xor     r8d, r8d; msPeriod
0x180012a72  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180012a77  call    cs:__imp_SetThreadpoolTimer
0x180012a7d  mov     byte ptr cs:word_1800ADB50, 1
0x180012a84  lea     rcx, stru_1800ADB38; SRWLock
0x180012a8b  call    cs:__imp_ReleaseSRWLockExclusive
0x180012a91  nop
0x180012a92  mov     rbx, [rsp+38h+arg_0]
0x180012a97  mov     rsi, [rsp+38h+arg_8]
0x180012a9c  add     rsp, 30h
0x180012aa0  pop     rdi
0x180012aa1  retn
0x180012aa2  test    r8d, r8d
0x180012aa5  jnz     loc_180012B2F
0x180012aab  cmp     ebx, 0FEh
0x180012ab1  jz      short loc_180012B2F
0x180012ab3  xor     eax, eax
0x180012ab5  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180012aba  mov     [rsp+38h+pftDueTime.dwLowDateTime], esi
0x180012abe  mov     word ptr [rsp+38h+pftDueTime.dwHighDateTime], bx
0x180012ac3  test    edx, edx
0x180012ac5  jns     short loc_180012ACD
0x180012ac7  or      word ptr [rsp+38h+pftDueTime.dwHighDateTime+2], 1
0x180012acd  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180012ad4  test    rax, rax
0x180012ad7  jnz     short loc_180012B15
0x180012ad9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012ae0  test    rax, rax
0x180012ae3  jnz     short loc_180012AF9
0x180012ae5  lea     rcx, ModuleName; "ntdll.dll"
0x180012aec  call    cs:__imp_GetModuleHandleW
0x180012af2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012af9  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180012b00  mov     rcx, rax; hModule
0x180012b03  call    cs:__imp_GetProcAddress
0x180012b09  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180012b10  test    rax, rax
0x180012b13  jz      short loc_180012B43
0x180012b15  lea     rcx, [rsp+38h+pftDueTime]
0x180012b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b1f  mov     rbx, [rsp+38h+arg_0]
0x180012b24  mov     rsi, [rsp+38h+arg_8]
0x180012b29  add     rsp, 30h
0x180012b2d  pop     rdi
0x180012b2e  retn
0x180012b2f  mov     r9, rdi
0x180012b32  mov     r8d, ebx
0x180012b35  mov     edx, esi
0x180012b37  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180012b3e  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180012b43  mov     rbx, [rsp+38h+arg_0]
0x180012b48  mov     rsi, [rsp+38h+arg_8]
0x180012b4d  add     rsp, 30h
0x180012b51  pop     rdi
0x180012b52  retn
```
