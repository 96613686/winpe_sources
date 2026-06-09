# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180020c50`
- end: `0x180020dbf`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `367`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180022630`

## callees

- `0x180020c50`
- `0x180022984`
- `0x180022a84`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180020d02`
- `msvcrt!memcpy_s` at `0x180020d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020d56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020d56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020cac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020cac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020d99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020d99`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020d3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020d3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020d81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020d81`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-48h] BYREF
  int Source; // [rsp+28h] [rbp-40h] BYREF
  __int16 v14; // [rsp+2Ch] [rbp-3Ch]
  __int16 v15; // [rsp+2Eh] [rbp-3Ah]
  int v16; // [rsp+30h] [rbp-38h]

  if ( *pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v15 = 0;
    Source = a2;
    v14 = a3;
    v16 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 232), 0xCu) )
    {
      memcpy_s(
        *((void *const *)pv + 30),
        (*((_QWORD *)pv + 31) - *((_QWORD *)pv + 30)) & -(__int64)(*((_QWORD *)pv + 30) < *((_QWORD *)pv + 31)),
        &Source,
        0xCu);
      *((_QWORD *)pv + 30) += 12LL;
    }
    if ( !pv[64] )
    {
      v8 = (struct _TP_TIMER **)(pv + 56);
      if ( !*((_QWORD *)pv + 7) )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)pv + 7,
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        pv[64] = 1;
      }
    }
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x180020c50  push    rbx
0x180020c52  push    rbp
0x180020c53  push    rsi
0x180020c54  push    rdi
0x180020c55  push    r14
0x180020c57  sub     rsp, 40h
0x180020c5b  mov     rax, cs:__security_cookie
0x180020c62  xor     rax, rsp
0x180020c65  mov     [rsp+68h+var_30], rax
0x180020c6a  mov     r14d, r9d
0x180020c6d  movzx   esi, r8w
0x180020c71  mov     ebx, edx
0x180020c73  mov     rdi, rcx
0x180020c76  cmp     byte ptr [rcx], 0
0x180020c79  jz      loc_180020DA6
0x180020c7f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180020c86  jnz     loc_180020DA6
0x180020c8c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180020c93  test    rax, rax
0x180020c96  jz      short loc_180020CA5
0x180020c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c9d  test    al, al
0x180020c9f  jnz     loc_180020DA6
0x180020ca5  lea     rbp, [rdi+28h]
0x180020ca9  mov     rcx, rbp; SRWLock
0x180020cac  call    cs:__imp_AcquireSRWLockExclusive
0x180020cb3  nop     dword ptr [rax+rax+00h]
0x180020cb8  xor     eax, eax
0x180020cba  mov     [rsp+68h+var_3A], ax
0x180020cbf  mov     [rsp+68h+Source], ebx
0x180020cc3  mov     [rsp+68h+var_3C], si
0x180020cc8  mov     [rsp+68h+var_38], r14d
0x180020ccd  lea     rbx, [rdi+0E8h]
0x180020cd4  lea     esi, [rax+0Ch]
0x180020cd7  mov     edx, esi; unsigned __int64
0x180020cd9  mov     rcx, rbx; this
0x180020cdc  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180020ce1  test    al, al
0x180020ce3  jz      short loc_180020D12
0x180020ce5  mov     rcx, [rbx+8]; Destination
0x180020ce9  mov     rax, [rbx+10h]
0x180020ced  sub     rax, rcx
0x180020cf0  cmp     rcx, [rbx+10h]
0x180020cf4  sbb     rdx, rdx
0x180020cf7  and     rdx, rax; DestinationSize
0x180020cfa  mov     r9d, esi; SourceSize
0x180020cfd  lea     r8, [rsp+68h+Source]; Source
0x180020d02  call    cs:__imp_memcpy_s
0x180020d09  nop     dword ptr [rax+rax+00h]
0x180020d0e  add     [rbx+8], rsi
0x180020d12  cmp     byte ptr [rdi+40h], 0
0x180020d16  jnz     short loc_180020D91
0x180020d18  lea     rsi, [rdi+38h]
0x180020d1c  cmp     qword ptr [rsi], 0
0x180020d20  jnz     short loc_180020D62
0x180020d22  call    cs:__imp_GetLastError
0x180020d29  nop     dword ptr [rax+rax+00h]
0x180020d2e  mov     ebx, eax
0x180020d30  xor     r8d, r8d; pcbe
0x180020d33  mov     rdx, rdi; pv
0x180020d36  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180020d3d  call    cs:__imp_CreateThreadpoolTimer
0x180020d44  nop     dword ptr [rax+rax+00h]
0x180020d49  mov     rdx, rax
0x180020d4c  mov     rcx, rsi
0x180020d4f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180020d54  mov     ecx, ebx; dwErrCode
0x180020d56  call    cs:__imp_SetLastError
0x180020d5d  nop     dword ptr [rax+rax+00h]
0x180020d62  mov     rcx, [rsi]; pti
0x180020d65  test    rcx, rcx
0x180020d68  jz      short loc_180020D91
0x180020d6a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180020d73  mov     r9d, 4E2h; msWindowLength
0x180020d79  xor     r8d, r8d; msPeriod
0x180020d7c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180020d81  call    cs:__imp_SetThreadpoolTimer
0x180020d88  nop     dword ptr [rax+rax+00h]
0x180020d8d  mov     byte ptr [rdi+40h], 1
0x180020d91  test    rbp, rbp
0x180020d94  jz      short loc_180020DA6
0x180020d96  mov     rcx, rbp; SRWLock
0x180020d99  call    cs:__imp_ReleaseSRWLockExclusive
0x180020da0  nop     dword ptr [rax+rax+00h]
0x180020da5  nop
0x180020da6  mov     rcx, [rsp+68h+var_30]
0x180020dab  xor     rcx, rsp; StackCookie
0x180020dae  call    __security_check_cookie
0x180020db3  add     rsp, 40h
0x180020db7  pop     r14
0x180020db9  pop     rdi
0x180020dba  pop     rsi
0x180020dbb  pop     rbp
0x180020dbc  pop     rbx
0x180020dbd  retn
```
