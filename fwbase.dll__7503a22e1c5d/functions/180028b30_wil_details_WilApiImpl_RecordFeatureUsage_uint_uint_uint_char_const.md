# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180028b30`
- end: `0x180028dd3`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `675`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callees

- `0x18001e1d0`
- `0x18001eae6`
- `0x18001eb54`
- `0x1800238e0`
- `0x180025bc0`
- `0x1800265d0`
- `0x1800268c0`
- `0x180028b30`
- `0x180029710`
- `0x180029820`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180028c51`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180028c83`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180028c51`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180028c83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028d87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028d87`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028d70`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028d70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028c05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028c05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028d1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028d1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ce1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cb1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180028cca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180028cca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028d0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028d0a`

## string_xrefs

- `0x180028d69`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  DWORD v4; // ebp
  unsigned int v5; // edi
  size_t v6; // rbx
  _DWORD *v7; // r9
  struct _TP_TIMER *v8; // rcx
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-38h] BYREF

  v4 = (unsigned int)this;
  v5 = a2 & 0x7FFFFFFF;
  if ( !(_DWORD)this && !a3 && !v5 )
  {
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
    {
      wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18003C028[25], qword_18003C028);
      wil::details_abi::FeatureStateData::RecordUsage(qword_18003C028);
    }
    return;
  }
  if ( (a2 & 0x40000000) != 0 )
  {
    if ( !wil::details::g_featureStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
      return;
    }
    AcquireSRWLockExclusive(&stru_18003C038);
    v6 = 0;
    pftDueTime.dwLowDateTime = v4;
    pftDueTime.dwHighDateTime = (unsigned __int16)v5;
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(&xmmword_18003C0F0 + 1), 0xCu) )
      goto LABEL_24;
    v7 = xmmword_18003C100;
    if ( xmmword_18003C100 < *(&xmmword_18003C100 + 1) )
      v6 = (_BYTE *)*(&xmmword_18003C100 + 1) - (_BYTE *)xmmword_18003C100;
    if ( xmmword_18003C100 )
    {
      if ( v6 >= 0xC )
      {
        *(struct _FILETIME *)xmmword_18003C100 = pftDueTime;
        v7[2] = a3;
LABEL_23:
        xmmword_18003C100 = (char *)xmmword_18003C100 + 12;
LABEL_24:
        if ( !byte_18003C050 )
        {
          v8 = pti;
          if ( pti
            || (LastError = GetLastError(),
                ThreadpoolTimer = CreateThreadpoolTimer(
                                    _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                                    &wil::details::g_featureStateManager,
                                    0),
                wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
                  &pti,
                  ThreadpoolTimer),
                SetLastError(LastError),
                (v8 = pti) != 0) )
          {
            pftDueTime = (struct _FILETIME)-50000000LL;
            SetThreadpoolTimer(v8, &pftDueTime, 0, 0x4E2u);
            byte_18003C050 = 1;
          }
        }
        ReleaseSRWLockExclusive(&stru_18003C038);
        return;
      }
      memset_0(xmmword_18003C100, 0, v6);
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_23;
  }
  if ( a3 || v5 == 254 )
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
      goto LABEL_38;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_38:
      ((void (__fastcall *)(struct _FILETIME *))ProcAddress)(&pftDueTime);
  }
}

```

## disassembly

```asm
0x180028b30  mov     [rsp+arg_18], rbx
0x180028b35  push    rbp
0x180028b36  push    rsi
0x180028b37  push    rdi
0x180028b38  sub     rsp, 40h
0x180028b3c  mov     rax, cs:__security_cookie
0x180028b43  xor     rax, rsp
0x180028b46  mov     [rsp+58h+var_28], rax
0x180028b4b  mov     esi, r8d
0x180028b4e  mov     ebp, ecx
0x180028b50  mov     edi, edx
0x180028b52  btr     edi, 1Fh
0x180028b56  test    ecx, ecx
0x180028b58  jnz     short loc_180028BC1
0x180028b5a  test    r8d, r8d
0x180028b5d  jnz     short loc_180028BC1
0x180028b5f  test    edi, edi
0x180028b61  jnz     short loc_180028BC1
0x180028b63  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dil; bool wil::details::g_processShutdownInProgress
0x180028b6a  jnz     loc_180028D25
0x180028b70  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180028b77  test    rax, rax
0x180028b7a  jz      short loc_180028B89
0x180028b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b81  test    al, al
0x180028b83  jnz     loc_180028D25
0x180028b89  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180028b90  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180028b95  test    al, al
0x180028b97  jz      loc_180028D25
0x180028b9d  mov     rdx, cs:qword_18003C028; SRWLock
0x180028ba4  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180028bab  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180028bb0  mov     rcx, cs:qword_18003C028; SRWLock
0x180028bb7  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180028bbc  jmp     loc_180028D25
0x180028bc1  bt      edi, 1Eh
0x180028bc5  jnb     loc_180028D2A
0x180028bcb  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180028bd2  jz      loc_180028D25
0x180028bd8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180028bdf  jnz     loc_180028D25
0x180028be5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180028bec  test    rax, rax
0x180028bef  jz      short loc_180028BFE
0x180028bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bf6  test    al, al
0x180028bf8  jnz     loc_180028D25
0x180028bfe  lea     rcx, stru_18003C038; SRWLock
0x180028c05  call    cs:__imp_AcquireSRWLockExclusive
0x180028c0b  xor     ebx, ebx
0x180028c0d  mov     word ptr [rsp+58h+pftDueTime.dwHighDateTime+2], bx
0x180028c12  mov     [rsp+58h+pftDueTime.dwLowDateTime], ebp
0x180028c16  mov     word ptr [rsp+58h+pftDueTime.dwHighDateTime], di
0x180028c1b  mov     edx, 0Ch; unsigned __int64
0x180028c20  lea     rcx, xmmword_18003C0F0+8; this
0x180028c27  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180028c2c  test    al, al
0x180028c2e  jz      short loc_180028C9C
0x180028c30  mov     r9, qword ptr cs:xmmword_18003C100
0x180028c37  mov     rax, qword ptr cs:xmmword_18003C100+8
0x180028c3e  sub     rax, r9
0x180028c41  cmp     r9, qword ptr cs:xmmword_18003C100+8
0x180028c48  cmovb   rbx, rax
0x180028c4c  test    r9, r9
0x180028c4f  jnz     short loc_180028C5F
0x180028c51  call    cs:__imp__o__errno
0x180028c57  mov     dword ptr [rax], 16h
0x180028c5d  jmp     short loc_180028C8F
0x180028c5f  cmp     rbx, 0Ch
0x180028c63  jb      short loc_180028C76
0x180028c65  movsd   xmm0, qword ptr [rsp+58h+pftDueTime.dwLowDateTime]
0x180028c6b  movsd   qword ptr [r9], xmm0
0x180028c70  mov     [r9+8], esi
0x180028c74  jmp     short loc_180028C94
0x180028c76  mov     r8, rbx; Size
0x180028c79  xor     edx, edx; Val
0x180028c7b  mov     rcx, r9; void *
0x180028c7e  call    memset_0
0x180028c83  call    cs:__imp__o__errno
0x180028c89  mov     dword ptr [rax], 22h ; '"'
0x180028c8f  call    _invalid_parameter_noinfo
0x180028c94  add     qword ptr cs:xmmword_18003C100, 0Ch
0x180028c9c  cmp     cs:byte_18003C050, 0
0x180028ca3  jnz     short loc_180028D17
0x180028ca5  mov     rcx, cs:pti
0x180028cac  test    rcx, rcx
0x180028caf  jnz     short loc_180028CF3
0x180028cb1  call    cs:__imp_GetLastError
0x180028cb7  mov     ebx, eax
0x180028cb9  xor     r8d, r8d; pcbe
0x180028cbc  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180028cc3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180028cca  call    cs:__imp_CreateThreadpoolTimer
0x180028cd0  mov     rdx, rax
0x180028cd3  lea     rcx, pti
0x180028cda  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180028cdf  mov     ecx, ebx; dwErrCode
0x180028ce1  call    cs:__imp_SetLastError
0x180028ce7  mov     rcx, cs:pti; pti
0x180028cee  test    rcx, rcx
0x180028cf1  jz      short loc_180028D17
0x180028cf3  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180028cfc  mov     r9d, 4E2h; msWindowLength
0x180028d02  xor     r8d, r8d; msPeriod
0x180028d05  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180028d0a  call    cs:__imp_SetThreadpoolTimer
0x180028d10  mov     cs:byte_18003C050, 1
0x180028d17  lea     rcx, stru_18003C038; SRWLock
0x180028d1e  call    cs:__imp_ReleaseSRWLockExclusive
0x180028d24  nop
0x180028d25  jmp     loc_180028DB9
0x180028d2a  test    r8d, r8d
0x180028d2d  jnz     short loc_180028DA5
0x180028d2f  cmp     edi, 0FEh
0x180028d35  jz      short loc_180028DA5
0x180028d37  xor     ebx, ebx
0x180028d39  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rbx
0x180028d3e  mov     [rsp+58h+pftDueTime.dwLowDateTime], ebp
0x180028d42  mov     word ptr [rsp+58h+pftDueTime.dwHighDateTime], di
0x180028d47  test    edx, edx
0x180028d49  jns     short loc_180028D51
0x180028d4b  or      word ptr [rsp+58h+pftDueTime.dwHighDateTime+2], 1
0x180028d51  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180028d58  test    rax, rax
0x180028d5b  jnz     short loc_180028D99
0x180028d5d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180028d64  test    rax, rax
0x180028d67  jnz     short loc_180028D7D
0x180028d69  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180028d70  call    cs:__imp_GetModuleHandleW
0x180028d76  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180028d7d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180028d84  mov     rcx, rax; hModule
0x180028d87  call    cs:__imp_GetProcAddress
0x180028d8d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180028d94  test    rax, rax
0x180028d97  jz      short loc_180028DB9
0x180028d99  lea     rcx, [rsp+58h+pftDueTime]
0x180028d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028da3  jmp     short loc_180028DB9
0x180028da5  mov     r9, rsi
0x180028da8  mov     r8d, edi
0x180028dab  mov     edx, ebp
0x180028dad  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180028db4  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180028db9  mov     rcx, [rsp+58h+var_28]
0x180028dbe  xor     rcx, rsp; StackCookie
0x180028dc1  call    __security_check_cookie
0x180028dc6  mov     rbx, [rsp+58h+arg_18]
0x180028dcb  add     rsp, 40h
0x180028dcf  pop     rdi
0x180028dd0  pop     rsi
0x180028dd1  pop     rbp
0x180028dd2  retn
```
