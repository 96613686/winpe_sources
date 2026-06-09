# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180010384`
- end: `0x1800104f6`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `370`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800119b0`

## callees

- `0x18000649c`
- `0x180010384`
- `0x180013f2c`
- `0x1800142b8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010495`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010461`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800104de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800104de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800103cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800103cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001047c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001047c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800104c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800104c6`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v5; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v8; // rcx
  _QWORD Source[7]; // [rsp+20h] [rbp-38h] BYREF
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( *(_DWORD *)pv
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = 57312060;
      Source[1] = a3;
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
        v5 = (struct _TP_TIMER **)(pv + 16);
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
        v8 = *v5;
        if ( *v5 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v8, &pftDueTime, 0, 0x124F8u);
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
0x180010384  push    rbx
0x180010386  push    rsi
0x180010387  push    rdi
0x180010388  push    r14
0x18001038a  sub     rsp, 38h
0x18001038e  mov     rbx, r8
0x180010391  mov     rdi, rcx
0x180010394  mov     eax, [rcx]
0x180010396  test    eax, eax
0x180010398  jz      loc_1800104EB
0x18001039e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800103a5  jnz     loc_1800104EB
0x1800103ab  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800103b2  test    rax, rax
0x1800103b5  jz      short loc_1800103C4
0x1800103b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103bc  test    al, al
0x1800103be  jnz     loc_1800104EB
0x1800103c4  lea     rsi, [rdi+8]
0x1800103c8  mov     rcx, rsi; SRWLock
0x1800103cb  call    cs:__imp_AcquireSRWLockExclusive
0x1800103d2  nop     dword ptr [rax+rax+00h]
0x1800103d7  mov     eax, [rdi]
0x1800103d9  test    eax, eax
0x1800103db  jz      loc_1800104D6
0x1800103e1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800103e8  jnz     loc_1800104D6
0x1800103ee  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800103f5  test    rax, rax
0x1800103f8  jz      short loc_180010407
0x1800103fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ff  test    al, al
0x180010401  jnz     loc_1800104D6
0x180010407  mov     [rsp+58h+Source], 36A833Ch
0x180010410  mov     [rsp+58h+var_30], rbx
0x180010415  mov     r14d, 10h
0x18001041b  mov     edx, r14d; unsigned __int64
0x18001041e  lea     rcx, [rdi+30h]; this
0x180010422  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180010427  test    al, al
0x180010429  jz      short loc_180010451
0x18001042b  mov     rcx, [rdi+38h]; Destination
0x18001042f  mov     rax, [rdi+40h]
0x180010433  sub     rax, rcx
0x180010436  cmp     rcx, [rdi+40h]
0x18001043a  sbb     rdx, rdx
0x18001043d  and     rdx, rax; DestinationSize
0x180010440  mov     r9d, r14d; SourceSize
0x180010443  lea     r8, [rsp+58h+Source]; Source
0x180010448  call    memcpy_s
0x18001044d  add     [rdi+38h], r14
0x180010451  cmp     byte ptr [rdi+18h], 0
0x180010455  jnz     short loc_1800104D6
0x180010457  lea     r14, [rdi+10h]
0x18001045b  cmp     qword ptr [r14], 0
0x18001045f  jnz     short loc_1800104A1
0x180010461  call    cs:__imp_GetLastError
0x180010468  nop     dword ptr [rax+rax+00h]
0x18001046d  mov     ebx, eax
0x18001046f  xor     r8d, r8d; pcbe
0x180010472  mov     rdx, rdi; pv
0x180010475  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001047c  call    cs:__imp_CreateThreadpoolTimer
0x180010483  nop     dword ptr [rax+rax+00h]
0x180010488  mov     rdx, rax
0x18001048b  mov     rcx, r14
0x18001048e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180010493  mov     ecx, ebx; dwErrCode
0x180010495  call    cs:__imp_SetLastError
0x18001049c  nop     dword ptr [rax+rax+00h]
0x1800104a1  mov     rcx, [r14]; pti
0x1800104a4  test    rcx, rcx
0x1800104a7  jz      short loc_1800104D6
0x1800104a9  mov     rax, 0FFFFFFFF4D2FA200h
0x1800104b3  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x1800104b8  mov     r9d, 124F8h; msWindowLength
0x1800104be  xor     r8d, r8d; msPeriod
0x1800104c1  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x1800104c6  call    cs:__imp_SetThreadpoolTimer
0x1800104cd  nop     dword ptr [rax+rax+00h]
0x1800104d2  mov     byte ptr [rdi+18h], 1
0x1800104d6  test    rsi, rsi
0x1800104d9  jz      short loc_1800104EB
0x1800104db  mov     rcx, rsi; SRWLock
0x1800104de  call    cs:__imp_ReleaseSRWLockExclusive
0x1800104e5  nop     dword ptr [rax+rax+00h]
0x1800104ea  nop
0x1800104eb  add     rsp, 38h
0x1800104ef  pop     r14
0x1800104f1  pop     rdi
0x1800104f2  pop     rsi
0x1800104f3  pop     rbx
0x1800104f4  retn
```
