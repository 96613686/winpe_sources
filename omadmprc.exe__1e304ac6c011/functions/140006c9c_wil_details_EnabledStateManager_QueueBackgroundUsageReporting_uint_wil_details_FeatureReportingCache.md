# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140006c9c`
- end: `0x140006e25`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1400081cc`

## callees

- `0x140006c9c`
- `0x14000a33c`
- `0x14000a6e0`
- `0x140017010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140006d67`
- `msvcrt!memcpy_s` at `0x140006d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006dbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006dbb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006ced`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006ced`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006e04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006e04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006dec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006dec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006da2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006da2`

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
0x140006c9c  mov     [rsp+arg_8], rbx
0x140006ca1  mov     [rsp+arg_10], rbp
0x140006ca6  push    rsi
0x140006ca7  push    rdi
0x140006ca8  push    r14
0x140006caa  sub     rsp, 30h
0x140006cae  mov     rbx, r8
0x140006cb1  mov     ebp, edx
0x140006cb3  mov     rdi, rcx
0x140006cb6  mov     eax, [rcx]
0x140006cb8  test    eax, eax
0x140006cba  jz      loc_140006E11
0x140006cc0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140006cc7  jnz     loc_140006E11
0x140006ccd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140006cd4  test    rax, rax
0x140006cd7  jz      short loc_140006CE6
0x140006cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cde  test    al, al
0x140006ce0  jnz     loc_140006E11
0x140006ce6  lea     rsi, [rdi+8]
0x140006cea  mov     rcx, rsi; SRWLock
0x140006ced  call    cs:__imp_AcquireSRWLockExclusive
0x140006cf4  nop     dword ptr [rax+rax+00h]
0x140006cf9  mov     eax, [rdi]
0x140006cfb  test    eax, eax
0x140006cfd  jz      loc_140006DFC
0x140006d03  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140006d0a  jnz     loc_140006DFC
0x140006d10  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140006d17  test    rax, rax
0x140006d1a  jz      short loc_140006D29
0x140006d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d21  test    al, al
0x140006d23  jnz     loc_140006DFC
0x140006d29  mov     [rsp+48h+Source], ebp
0x140006d2d  xor     eax, eax
0x140006d2f  mov     [rsp+48h+var_24], eax
0x140006d33  mov     [rsp+48h+var_20], rbx
0x140006d38  lea     ebp, [rax+10h]
0x140006d3b  mov     edx, ebp; unsigned __int64
0x140006d3d  lea     rcx, [rdi+30h]; this
0x140006d41  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140006d46  test    al, al
0x140006d48  jz      short loc_140006D77
0x140006d4a  mov     rcx, [rdi+38h]; Destination
0x140006d4e  mov     rax, [rdi+40h]
0x140006d52  sub     rax, rcx
0x140006d55  cmp     rcx, [rdi+40h]
0x140006d59  sbb     rdx, rdx
0x140006d5c  and     rdx, rax; DestinationSize
0x140006d5f  mov     r9d, ebp; SourceSize
0x140006d62  lea     r8, [rsp+48h+Source]; Source
0x140006d67  call    cs:__imp_memcpy_s
0x140006d6e  nop     dword ptr [rax+rax+00h]
0x140006d73  add     [rdi+38h], rbp
0x140006d77  cmp     byte ptr [rdi+18h], 0
0x140006d7b  jnz     short loc_140006DFC
0x140006d7d  lea     r14, [rdi+10h]
0x140006d81  cmp     qword ptr [r14], 0
0x140006d85  jnz     short loc_140006DC7
0x140006d87  call    cs:__imp_GetLastError
0x140006d8e  nop     dword ptr [rax+rax+00h]
0x140006d93  mov     ebx, eax
0x140006d95  xor     r8d, r8d; pcbe
0x140006d98  mov     rdx, rdi; pv
0x140006d9b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140006da2  call    cs:__imp_CreateThreadpoolTimer
0x140006da9  nop     dword ptr [rax+rax+00h]
0x140006dae  mov     rdx, rax
0x140006db1  mov     rcx, r14
0x140006db4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140006db9  mov     ecx, ebx; dwErrCode
0x140006dbb  call    cs:__imp_SetLastError
0x140006dc2  nop     dword ptr [rax+rax+00h]
0x140006dc7  mov     rcx, [r14]; pti
0x140006dca  test    rcx, rcx
0x140006dcd  jz      short loc_140006DFC
0x140006dcf  mov     rax, 0FFFFFFFF4D2FA200h
0x140006dd9  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x140006dde  mov     r9d, 124F8h; msWindowLength
0x140006de4  xor     r8d, r8d; msPeriod
0x140006de7  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x140006dec  call    cs:__imp_SetThreadpoolTimer
0x140006df3  nop     dword ptr [rax+rax+00h]
0x140006df8  mov     byte ptr [rdi+18h], 1
0x140006dfc  test    rsi, rsi
0x140006dff  jz      short loc_140006E11
0x140006e01  mov     rcx, rsi; SRWLock
0x140006e04  call    cs:__imp_ReleaseSRWLockExclusive
0x140006e0b  nop     dword ptr [rax+rax+00h]
0x140006e10  nop
0x140006e11  mov     rbx, [rsp+48h+arg_8]
0x140006e16  mov     rbp, [rsp+48h+arg_10]
0x140006e1b  add     rsp, 30h
0x140006e1f  pop     r14
0x140006e21  pop     rdi
0x140006e22  pop     rsi
0x140006e23  retn
```
