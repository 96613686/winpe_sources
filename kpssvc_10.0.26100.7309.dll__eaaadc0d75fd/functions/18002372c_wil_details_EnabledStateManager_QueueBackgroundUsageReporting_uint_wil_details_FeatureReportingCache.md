# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002372c`
- end: `0x18002385b`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `303`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180024d74`

## callees

- `0x18002372c`
- `0x180026440`
- `0x1800265e4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023838`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023838`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002377d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002377d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800237ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800237ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023820`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023820`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800237d6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800237d6`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v5; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v8; // rcx
  _QWORD Source[3]; // [rsp+20h] [rbp-18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Source[0] = 55623657;
    Source[1] = a3;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], Source, 0x10u);
    v5 = (struct _TP_TIMER **)&pv[2];
    if ( !LOBYTE(pv[3].Ptr) )
    {
      if ( !*v5 )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)&pv[2],
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v8 = *v5;
      if ( *v5 )
      {
        pftDueTime = (struct _FILETIME)-3000000000LL;
        SetThreadpoolTimer(v8, &pftDueTime, 0, 0x124F8u);
        LOBYTE(pv[3].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x18002372c  mov     [rsp+arg_8], rbx
0x180023731  mov     [rsp+arg_10], rsi
0x180023736  mov     [rsp+arg_18], rdi
0x18002373b  push    r14
0x18002373d  sub     rsp, 30h
0x180023741  cmp     byte ptr [rcx], 0
0x180023744  mov     rbx, r8
0x180023747  mov     rdi, rcx
0x18002374a  jz      loc_180023844
0x180023750  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180023757  jnz     loc_180023844
0x18002375d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180023764  test    rax, rax
0x180023767  jz      short loc_180023776
0x180023769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002376e  test    al, al
0x180023770  jnz     loc_180023844
0x180023776  lea     rsi, [rdi+8]
0x18002377a  mov     rcx, rsi; SRWLock
0x18002377d  call    cs:__imp_AcquireSRWLockExclusive
0x180023784  nop     dword ptr [rax+rax+00h]
0x180023789  lea     rcx, [rdi+30h]; this
0x18002378d  mov     [rsp+38h+Source], 350BFE9h
0x180023796  mov     r8d, 10h; SourceSize
0x18002379c  mov     [rsp+38h+var_10], rbx
0x1800237a1  lea     rdx, [rsp+38h+Source]; Source
0x1800237a6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800237ab  cmp     byte ptr [rdi+18h], 0
0x1800237af  lea     r14, [rdi+10h]
0x1800237b3  jnz     short loc_180023830
0x1800237b5  cmp     qword ptr [r14], 0
0x1800237b9  jnz     short loc_1800237FB
0x1800237bb  call    cs:__imp_GetLastError
0x1800237c2  nop     dword ptr [rax+rax+00h]
0x1800237c7  xor     r8d, r8d; pcbe
0x1800237ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800237d1  mov     rdx, rdi; pv
0x1800237d4  mov     ebx, eax
0x1800237d6  call    cs:__imp_CreateThreadpoolTimer
0x1800237dd  nop     dword ptr [rax+rax+00h]
0x1800237e2  mov     rdx, rax
0x1800237e5  mov     rcx, r14
0x1800237e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800237ed  mov     ecx, ebx; dwErrCode
0x1800237ef  call    cs:__imp_SetLastError
0x1800237f6  nop     dword ptr [rax+rax+00h]
0x1800237fb  mov     rcx, [r14]; pti
0x1800237fe  test    rcx, rcx
0x180023801  jz      short loc_180023830
0x180023803  mov     rax, 0FFFFFFFF4D2FA200h
0x18002380d  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180023812  mov     r9d, 124F8h; msWindowLength
0x180023818  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18002381d  xor     r8d, r8d; msPeriod
0x180023820  call    cs:__imp_SetThreadpoolTimer
0x180023827  nop     dword ptr [rax+rax+00h]
0x18002382c  mov     byte ptr [rdi+18h], 1
0x180023830  test    rsi, rsi
0x180023833  jz      short loc_180023844
0x180023835  mov     rcx, rsi; SRWLock
0x180023838  call    cs:__imp_ReleaseSRWLockExclusive
0x18002383f  nop     dword ptr [rax+rax+00h]
0x180023844  mov     rbx, [rsp+38h+arg_8]
0x180023849  mov     rsi, [rsp+38h+arg_10]
0x18002384e  mov     rdi, [rsp+38h+arg_18]
0x180023853  add     rsp, 30h
0x180023857  pop     r14
0x180023859  retn
```
