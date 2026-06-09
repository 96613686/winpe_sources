# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140006b24`
- end: `0x140006c93`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `367`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140009880`

## callees

- `0x140006b24`
- `0x14000a33c`
- `0x14000a6e0`
- `0x140015690`
- `0x140017010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140006bd6`
- `msvcrt!memcpy_s` at `0x140006bd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006bf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006b80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006b80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006c6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006c6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006c55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006c55`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006c11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006c11`

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
0x140006b24  push    rbx
0x140006b26  push    rbp
0x140006b27  push    rsi
0x140006b28  push    rdi
0x140006b29  push    r14
0x140006b2b  sub     rsp, 40h
0x140006b2f  mov     rax, cs:__security_cookie
0x140006b36  xor     rax, rsp
0x140006b39  mov     [rsp+68h+var_30], rax
0x140006b3e  mov     r14d, r9d
0x140006b41  movzx   esi, r8w
0x140006b45  mov     ebx, edx
0x140006b47  mov     rdi, rcx
0x140006b4a  cmp     byte ptr [rcx], 0
0x140006b4d  jz      loc_140006C7A
0x140006b53  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140006b5a  jnz     loc_140006C7A
0x140006b60  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140006b67  test    rax, rax
0x140006b6a  jz      short loc_140006B79
0x140006b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b71  test    al, al
0x140006b73  jnz     loc_140006C7A
0x140006b79  lea     rbp, [rdi+28h]
0x140006b7d  mov     rcx, rbp; SRWLock
0x140006b80  call    cs:__imp_AcquireSRWLockExclusive
0x140006b87  nop     dword ptr [rax+rax+00h]
0x140006b8c  xor     eax, eax
0x140006b8e  mov     [rsp+68h+var_3A], ax
0x140006b93  mov     [rsp+68h+Source], ebx
0x140006b97  mov     [rsp+68h+var_3C], si
0x140006b9c  mov     [rsp+68h+var_38], r14d
0x140006ba1  lea     rbx, [rdi+0E8h]
0x140006ba8  lea     esi, [rax+0Ch]
0x140006bab  mov     edx, esi; unsigned __int64
0x140006bad  mov     rcx, rbx; this
0x140006bb0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140006bb5  test    al, al
0x140006bb7  jz      short loc_140006BE6
0x140006bb9  mov     rcx, [rbx+8]; Destination
0x140006bbd  mov     rax, [rbx+10h]
0x140006bc1  sub     rax, rcx
0x140006bc4  cmp     rcx, [rbx+10h]
0x140006bc8  sbb     rdx, rdx
0x140006bcb  and     rdx, rax; DestinationSize
0x140006bce  mov     r9d, esi; SourceSize
0x140006bd1  lea     r8, [rsp+68h+Source]; Source
0x140006bd6  call    cs:__imp_memcpy_s
0x140006bdd  nop     dword ptr [rax+rax+00h]
0x140006be2  add     [rbx+8], rsi
0x140006be6  cmp     byte ptr [rdi+40h], 0
0x140006bea  jnz     short loc_140006C65
0x140006bec  lea     rsi, [rdi+38h]
0x140006bf0  cmp     qword ptr [rsi], 0
0x140006bf4  jnz     short loc_140006C36
0x140006bf6  call    cs:__imp_GetLastError
0x140006bfd  nop     dword ptr [rax+rax+00h]
0x140006c02  mov     ebx, eax
0x140006c04  xor     r8d, r8d; pcbe
0x140006c07  mov     rdx, rdi; pv
0x140006c0a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140006c11  call    cs:__imp_CreateThreadpoolTimer
0x140006c18  nop     dword ptr [rax+rax+00h]
0x140006c1d  mov     rdx, rax
0x140006c20  mov     rcx, rsi
0x140006c23  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140006c28  mov     ecx, ebx; dwErrCode
0x140006c2a  call    cs:__imp_SetLastError
0x140006c31  nop     dword ptr [rax+rax+00h]
0x140006c36  mov     rcx, [rsi]; pti
0x140006c39  test    rcx, rcx
0x140006c3c  jz      short loc_140006C65
0x140006c3e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140006c47  mov     r9d, 4E2h; msWindowLength
0x140006c4d  xor     r8d, r8d; msPeriod
0x140006c50  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140006c55  call    cs:__imp_SetThreadpoolTimer
0x140006c5c  nop     dword ptr [rax+rax+00h]
0x140006c61  mov     byte ptr [rdi+40h], 1
0x140006c65  test    rbp, rbp
0x140006c68  jz      short loc_140006C7A
0x140006c6a  mov     rcx, rbp; SRWLock
0x140006c6d  call    cs:__imp_ReleaseSRWLockExclusive
0x140006c74  nop     dword ptr [rax+rax+00h]
0x140006c79  nop
0x140006c7a  mov     rcx, [rsp+68h+var_30]
0x140006c7f  xor     rcx, rsp; StackCookie
0x140006c82  call    __security_check_cookie
0x140006c87  add     rsp, 40h
0x140006c8b  pop     r14
0x140006c8d  pop     rdi
0x140006c8e  pop     rsi
0x140006c8f  pop     rbp
0x140006c90  pop     rbx
0x140006c91  retn
```
