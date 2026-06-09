# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180019354`
- end: `0x1800194da`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `390`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180019580`

## callees

- `0x18000ce0c`
- `0x18000cfb4`
- `0x180013bfc`
- `0x180019354`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800193a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800193a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800194b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800194b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001943a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001943a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001946e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001946e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001949f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001949f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019455`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019455`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 48), 0x10u) )
      {
        memcpy_s(
          *((void *const *)pv + 7),
          (*((_QWORD *)pv + 8) - *((_QWORD *)pv + 7)) & -(__int64)(*((_QWORD *)pv + 7) < *((_QWORD *)pv + 8)),
          Source,
          0x10u);
        *((_QWORD *)pv + 7) += 16LL;
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
0x180019354  mov     [rsp+arg_8], rbx
0x180019359  mov     [rsp+arg_10], rbp
0x18001935e  push    rsi
0x18001935f  push    rdi
0x180019360  push    r14
0x180019362  sub     rsp, 30h
0x180019366  mov     rbp, r8
0x180019369  mov     r14d, edx
0x18001936c  mov     rdi, rcx
0x18001936f  mov     eax, [rcx]
0x180019371  test    eax, eax
0x180019373  jz      loc_1800194C6
0x180019379  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180019380  jnz     loc_1800194C6
0x180019386  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001938d  test    rax, rax
0x180019390  jz      short loc_18001939F
0x180019392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019397  test    al, al
0x180019399  jnz     loc_1800194C6
0x18001939f  lea     rsi, [rdi+8]
0x1800193a3  mov     rcx, rsi; SRWLock
0x1800193a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800193ad  nop     dword ptr [rax+rax+00h]
0x1800193b2  mov     eax, [rdi]
0x1800193b4  test    eax, eax
0x1800193b6  jz      loc_1800194B1
0x1800193bc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800193c3  jnz     loc_1800194B1
0x1800193c9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800193d0  test    rax, rax
0x1800193d3  jz      short loc_1800193E2
0x1800193d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193da  test    al, al
0x1800193dc  jnz     loc_1800194B1
0x1800193e2  mov     [rsp+48h+Source], r14d
0x1800193e7  xor     eax, eax
0x1800193e9  mov     [rsp+48h+var_24], eax
0x1800193ed  mov     [rsp+48h+var_20], rbp
0x1800193f2  lea     ebp, [rax+10h]
0x1800193f5  mov     edx, ebp; unsigned __int64
0x1800193f7  lea     rcx, [rdi+30h]; this
0x1800193fb  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180019400  test    al, al
0x180019402  jz      short loc_18001942A
0x180019404  mov     rcx, [rdi+38h]; Destination
0x180019408  mov     rax, [rdi+40h]
0x18001940c  sub     rax, rcx
0x18001940f  cmp     rcx, [rdi+40h]
0x180019413  sbb     rdx, rdx
0x180019416  and     rdx, rax; DestinationSize
0x180019419  mov     r9d, ebp; SourceSize
0x18001941c  lea     r8, [rsp+48h+Source]; Source
0x180019421  call    memcpy_s
0x180019426  add     [rdi+38h], rbp
0x18001942a  cmp     byte ptr [rdi+18h], 0
0x18001942e  jnz     short loc_1800194AF
0x180019430  lea     r14, [rdi+10h]
0x180019434  cmp     qword ptr [r14], 0
0x180019438  jnz     short loc_18001947A
0x18001943a  call    cs:__imp_GetLastError
0x180019441  nop     dword ptr [rax+rax+00h]
0x180019446  mov     ebx, eax
0x180019448  xor     r8d, r8d; pcbe
0x18001944b  mov     rdx, rdi; pv
0x18001944e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019455  call    cs:__imp_CreateThreadpoolTimer
0x18001945c  nop     dword ptr [rax+rax+00h]
0x180019461  mov     rdx, rax
0x180019464  mov     rcx, r14
0x180019467  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001946c  mov     ecx, ebx; dwErrCode
0x18001946e  call    cs:__imp_SetLastError
0x180019475  nop     dword ptr [rax+rax+00h]
0x18001947a  mov     rcx, [r14]; pti
0x18001947d  test    rcx, rcx
0x180019480  jz      short loc_1800194AF
0x180019482  mov     rax, 0FFFFFFFF4D2FA200h
0x18001948c  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180019491  mov     r9d, 124F8h; msWindowLength
0x180019497  xor     r8d, r8d; msPeriod
0x18001949a  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001949f  call    cs:__imp_SetThreadpoolTimer
0x1800194a6  nop     dword ptr [rax+rax+00h]
0x1800194ab  mov     byte ptr [rdi+18h], 1
0x1800194af  jmp     short $+2
0x1800194b1  test    rsi, rsi
0x1800194b4  jz      short loc_1800194C6
0x1800194b6  mov     rcx, rsi; SRWLock
0x1800194b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800194c0  nop     dword ptr [rax+rax+00h]
0x1800194c5  nop
0x1800194c6  mov     rbx, [rsp+48h+arg_8]
0x1800194cb  mov     rbp, [rsp+48h+arg_10]
0x1800194d0  add     rsp, 30h
0x1800194d4  pop     r14
0x1800194d6  pop     rdi
0x1800194d7  pop     rsi
0x1800194d8  retn
```
