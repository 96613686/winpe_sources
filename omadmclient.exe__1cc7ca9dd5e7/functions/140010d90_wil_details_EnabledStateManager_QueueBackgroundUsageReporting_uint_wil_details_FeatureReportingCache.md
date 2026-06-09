# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140010d90`
- end: `0x140010f12`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `386`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140010fb8`

## callees

- `0x14000d0ac`
- `0x14000d1a4`
- `0x14000ded8`
- `0x140010d90`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010ef1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010de1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010de1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010e74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010ea8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010ea8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010ed9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010ed9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140010e8f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140010e8f`

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
0x140010d90  mov     [rsp+arg_8], rbx
0x140010d95  mov     [rsp+arg_10], rbp
0x140010d9a  push    rsi
0x140010d9b  push    rdi
0x140010d9c  push    r14
0x140010d9e  sub     rsp, 30h
0x140010da2  mov     rbx, r8
0x140010da5  mov     ebp, edx
0x140010da7  mov     rdi, rcx
0x140010daa  mov     eax, [rcx]
0x140010dac  test    eax, eax
0x140010dae  jz      loc_140010EFE
0x140010db4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140010dbb  jnz     loc_140010EFE
0x140010dc1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140010dc8  test    rax, rax
0x140010dcb  jz      short loc_140010DDA
0x140010dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010dd2  test    al, al
0x140010dd4  jnz     loc_140010EFE
0x140010dda  lea     rsi, [rdi+8]
0x140010dde  mov     rcx, rsi; SRWLock
0x140010de1  call    cs:__imp_AcquireSRWLockExclusive
0x140010de8  nop     dword ptr [rax+rax+00h]
0x140010ded  mov     eax, [rdi]
0x140010def  test    eax, eax
0x140010df1  jz      loc_140010EE9
0x140010df7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140010dfe  jnz     loc_140010EE9
0x140010e04  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140010e0b  test    rax, rax
0x140010e0e  jz      short loc_140010E1D
0x140010e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e15  test    al, al
0x140010e17  jnz     loc_140010EE9
0x140010e1d  mov     [rsp+48h+Source], ebp
0x140010e21  xor     eax, eax
0x140010e23  mov     [rsp+48h+var_24], eax
0x140010e27  mov     [rsp+48h+var_20], rbx
0x140010e2c  lea     ebp, [rax+10h]
0x140010e2f  mov     edx, ebp; unsigned __int64
0x140010e31  lea     rcx, [rdi+30h]; this
0x140010e35  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140010e3a  test    al, al
0x140010e3c  jz      short loc_140010E64
0x140010e3e  mov     rcx, [rdi+38h]; Destination
0x140010e42  mov     rax, [rdi+40h]
0x140010e46  sub     rax, rcx
0x140010e49  cmp     rcx, [rdi+40h]
0x140010e4d  sbb     rdx, rdx
0x140010e50  and     rdx, rax; DestinationSize
0x140010e53  mov     r9d, ebp; SourceSize
0x140010e56  lea     r8, [rsp+48h+Source]; Source
0x140010e5b  call    memcpy_s
0x140010e60  add     [rdi+38h], rbp
0x140010e64  cmp     byte ptr [rdi+18h], 0
0x140010e68  jnz     short loc_140010EE9
0x140010e6a  lea     r14, [rdi+10h]
0x140010e6e  cmp     qword ptr [r14], 0
0x140010e72  jnz     short loc_140010EB4
0x140010e74  call    cs:__imp_GetLastError
0x140010e7b  nop     dword ptr [rax+rax+00h]
0x140010e80  mov     ebx, eax
0x140010e82  xor     r8d, r8d; pcbe
0x140010e85  mov     rdx, rdi; pv
0x140010e88  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140010e8f  call    cs:__imp_CreateThreadpoolTimer
0x140010e96  nop     dword ptr [rax+rax+00h]
0x140010e9b  mov     rdx, rax
0x140010e9e  mov     rcx, r14
0x140010ea1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140010ea6  mov     ecx, ebx; dwErrCode
0x140010ea8  call    cs:__imp_SetLastError
0x140010eaf  nop     dword ptr [rax+rax+00h]
0x140010eb4  mov     rcx, [r14]; pti
0x140010eb7  test    rcx, rcx
0x140010eba  jz      short loc_140010EE9
0x140010ebc  mov     rax, 0FFFFFFFF4D2FA200h
0x140010ec6  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x140010ecb  mov     r9d, 124F8h; msWindowLength
0x140010ed1  xor     r8d, r8d; msPeriod
0x140010ed4  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x140010ed9  call    cs:__imp_SetThreadpoolTimer
0x140010ee0  nop     dword ptr [rax+rax+00h]
0x140010ee5  mov     byte ptr [rdi+18h], 1
0x140010ee9  test    rsi, rsi
0x140010eec  jz      short loc_140010EFE
0x140010eee  mov     rcx, rsi; SRWLock
0x140010ef1  call    cs:__imp_ReleaseSRWLockExclusive
0x140010ef8  nop     dword ptr [rax+rax+00h]
0x140010efd  nop
0x140010efe  mov     rbx, [rsp+48h+arg_8]
0x140010f03  mov     rbp, [rsp+48h+arg_10]
0x140010f08  add     rsp, 30h
0x140010f0c  pop     r14
0x140010f0e  pop     rdi
0x140010f0f  pop     rsi
0x140010f10  retn
```
