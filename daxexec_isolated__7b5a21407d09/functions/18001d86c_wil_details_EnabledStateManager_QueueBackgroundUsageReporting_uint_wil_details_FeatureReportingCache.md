# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001d86c`
- end: `0x18001d9ee`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `386`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ec84`

## callees

- `0x18001108c`
- `0x18001d86c`
- `0x1800217b8`
- `0x180021d08`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d8bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d8bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d9cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d9cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d984`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d950`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d9b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d9b5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d96b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d96b`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v6; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v9; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v11; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( *(_DWORD *)pv
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v11 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 32), 0x10u) )
      {
        memcpy_s(
          *((void *const *)pv + 5),
          (*((_QWORD *)pv + 6) - *((_QWORD *)pv + 5)) & -(__int64)(*((_QWORD *)pv + 5) < *((_QWORD *)pv + 6)),
          Source,
          0x10u);
        *((_QWORD *)pv + 5) += 16LL;
      }
      if ( !pv[24] )
      {
        v6 = (struct _TP_TIMER **)(pv + 16);
        if ( !*((_QWORD *)pv + 2) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)pv + 2,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v9 = *v6;
        if ( *v6 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v9, &pftDueTime, 0, 0x124F8u);
          pv[24] = 1;
        }
      }
    }
    if ( pv != (char *)-8LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
  }
}

```

## disassembly

```asm
0x18001d86c  mov     [rsp+arg_8], rbx
0x18001d871  mov     [rsp+arg_10], rbp
0x18001d876  push    rsi
0x18001d877  push    rdi
0x18001d878  push    r14
0x18001d87a  sub     rsp, 30h
0x18001d87e  mov     rbx, r8
0x18001d881  mov     ebp, edx
0x18001d883  mov     rdi, rcx
0x18001d886  mov     eax, [rcx]
0x18001d888  test    eax, eax
0x18001d88a  jz      loc_18001D9DA
0x18001d890  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d897  jnz     loc_18001D9DA
0x18001d89d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d8a4  test    rax, rax
0x18001d8a7  jz      short loc_18001D8B6
0x18001d8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8ae  test    al, al
0x18001d8b0  jnz     loc_18001D9DA
0x18001d8b6  lea     rsi, [rdi+8]
0x18001d8ba  mov     rcx, rsi; SRWLock
0x18001d8bd  call    cs:__imp_AcquireSRWLockExclusive
0x18001d8c4  nop     dword ptr [rax+rax+00h]
0x18001d8c9  mov     eax, [rdi]
0x18001d8cb  test    eax, eax
0x18001d8cd  jz      loc_18001D9C5
0x18001d8d3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d8da  jnz     loc_18001D9C5
0x18001d8e0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d8e7  test    rax, rax
0x18001d8ea  jz      short loc_18001D8F9
0x18001d8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8f1  test    al, al
0x18001d8f3  jnz     loc_18001D9C5
0x18001d8f9  mov     [rsp+48h+Source], ebp
0x18001d8fd  xor     eax, eax
0x18001d8ff  mov     [rsp+48h+var_24], eax
0x18001d903  mov     [rsp+48h+var_20], rbx
0x18001d908  lea     ebp, [rax+10h]
0x18001d90b  mov     edx, ebp; unsigned __int64
0x18001d90d  lea     rcx, [rdi+20h]; this
0x18001d911  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001d916  test    al, al
0x18001d918  jz      short loc_18001D940
0x18001d91a  mov     rcx, [rdi+28h]; Destination
0x18001d91e  mov     rax, [rdi+30h]
0x18001d922  sub     rax, rcx
0x18001d925  cmp     rcx, [rdi+30h]
0x18001d929  sbb     rdx, rdx
0x18001d92c  and     rdx, rax; DestinationSize
0x18001d92f  mov     r9d, ebp; SourceSize
0x18001d932  lea     r8, [rsp+48h+Source]; Source
0x18001d937  call    memcpy_s
0x18001d93c  add     [rdi+28h], rbp
0x18001d940  cmp     byte ptr [rdi+18h], 0
0x18001d944  jnz     short loc_18001D9C5
0x18001d946  lea     r14, [rdi+10h]
0x18001d94a  cmp     qword ptr [r14], 0
0x18001d94e  jnz     short loc_18001D990
0x18001d950  call    cs:__imp_GetLastError
0x18001d957  nop     dword ptr [rax+rax+00h]
0x18001d95c  mov     ebx, eax
0x18001d95e  xor     r8d, r8d; pcbe
0x18001d961  mov     rdx, rdi; pv
0x18001d964  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d96b  call    cs:__imp_CreateThreadpoolTimer
0x18001d972  nop     dword ptr [rax+rax+00h]
0x18001d977  mov     rdx, rax
0x18001d97a  mov     rcx, r14
0x18001d97d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001d982  mov     ecx, ebx; dwErrCode
0x18001d984  call    cs:__imp_SetLastError
0x18001d98b  nop     dword ptr [rax+rax+00h]
0x18001d990  mov     rcx, [r14]; pti
0x18001d993  test    rcx, rcx
0x18001d996  jz      short loc_18001D9C5
0x18001d998  mov     rax, 0FFFFFFFF4D2FA200h
0x18001d9a2  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18001d9a7  mov     r9d, 124F8h; msWindowLength
0x18001d9ad  xor     r8d, r8d; msPeriod
0x18001d9b0  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001d9b5  call    cs:__imp_SetThreadpoolTimer
0x18001d9bc  nop     dword ptr [rax+rax+00h]
0x18001d9c1  mov     byte ptr [rdi+18h], 1
0x18001d9c5  test    rsi, rsi
0x18001d9c8  jz      short loc_18001D9DA
0x18001d9ca  mov     rcx, rsi; SRWLock
0x18001d9cd  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d9d4  nop     dword ptr [rax+rax+00h]
0x18001d9d9  nop
0x18001d9da  mov     rbx, [rsp+48h+arg_8]
0x18001d9df  mov     rbp, [rsp+48h+arg_10]
0x18001d9e4  add     rsp, 30h
0x18001d9e8  pop     r14
0x18001d9ea  pop     rdi
0x18001d9eb  pop     rsi
0x18001d9ec  retn
```
