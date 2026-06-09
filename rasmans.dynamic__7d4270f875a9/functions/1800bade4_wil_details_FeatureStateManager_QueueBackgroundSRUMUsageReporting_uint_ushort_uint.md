# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800bade4`
- end: `0x1800baf52`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `366`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800bd700`

## callees

- `0x1800bade4`
- `0x1800bdd68`
- `0x1800be088`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800bae96`
- `msvcrt!memcpy_s` at `0x1800bae96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800baeb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800baeb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800baeea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800baeea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800baf2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800baf2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bae40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bae40`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800baf15`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800baf15`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800baed1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800baed1`

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
    Source = a2;
    v14 = a3;
    v15 = 0;
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
0x1800bade4  push    rbx
0x1800bade6  push    rbp
0x1800bade7  push    rsi
0x1800bade8  push    rdi
0x1800bade9  push    r14
0x1800badeb  sub     rsp, 40h
0x1800badef  mov     rax, cs:__security_cookie
0x1800badf6  xor     rax, rsp
0x1800badf9  mov     [rsp+68h+var_30], rax
0x1800badfe  cmp     byte ptr [rcx], 0
0x1800bae01  mov     r14d, r9d
0x1800bae04  movzx   esi, r8w
0x1800bae08  mov     ebx, edx
0x1800bae0a  mov     rdi, rcx
0x1800bae0d  jz      loc_1800BAF39
0x1800bae13  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800bae1a  jnz     loc_1800BAF39
0x1800bae20  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800bae27  test    rax, rax
0x1800bae2a  jz      short loc_1800BAE39
0x1800bae2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae31  test    al, al
0x1800bae33  jnz     loc_1800BAF39
0x1800bae39  lea     rbp, [rdi+28h]
0x1800bae3d  mov     rcx, rbp; SRWLock
0x1800bae40  call    cs:__imp_AcquireSRWLockExclusive
0x1800bae47  nop     dword ptr [rax+rax+00h]
0x1800bae4c  xor     eax, eax
0x1800bae4e  mov     [rsp+68h+Source], ebx
0x1800bae52  mov     [rsp+68h+var_3C], si
0x1800bae57  lea     rbx, [rdi+0E8h]
0x1800bae5e  mov     rcx, rbx; this
0x1800bae61  mov     [rsp+68h+var_3A], ax
0x1800bae66  mov     [rsp+68h+var_38], r14d
0x1800bae6b  lea     esi, [rax+0Ch]
0x1800bae6e  mov     edx, esi; unsigned __int64
0x1800bae70  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800bae75  test    al, al
0x1800bae77  jz      short loc_1800BAEA6
0x1800bae79  mov     rcx, [rbx+8]; Destination
0x1800bae7d  lea     r8, [rsp+68h+Source]; Source
0x1800bae82  mov     rax, [rbx+10h]
0x1800bae86  mov     r9d, esi; SourceSize
0x1800bae89  sub     rax, rcx
0x1800bae8c  cmp     rcx, [rbx+10h]
0x1800bae90  sbb     rdx, rdx
0x1800bae93  and     rdx, rax; DestinationSize
0x1800bae96  call    cs:__imp_memcpy_s
0x1800bae9d  nop     dword ptr [rax+rax+00h]
0x1800baea2  add     [rbx+8], rsi
0x1800baea6  cmp     byte ptr [rdi+40h], 0
0x1800baeaa  jnz     short loc_1800BAF25
0x1800baeac  lea     rsi, [rdi+38h]
0x1800baeb0  cmp     qword ptr [rsi], 0
0x1800baeb4  jnz     short loc_1800BAEF6
0x1800baeb6  call    cs:__imp_GetLastError
0x1800baebd  nop     dword ptr [rax+rax+00h]
0x1800baec2  xor     r8d, r8d; pcbe
0x1800baec5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800baecc  mov     rdx, rdi; pv
0x1800baecf  mov     ebx, eax
0x1800baed1  call    cs:__imp_CreateThreadpoolTimer
0x1800baed8  nop     dword ptr [rax+rax+00h]
0x1800baedd  mov     rdx, rax
0x1800baee0  mov     rcx, rsi
0x1800baee3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800baee8  mov     ecx, ebx; dwErrCode
0x1800baeea  call    cs:__imp_SetLastError
0x1800baef1  nop     dword ptr [rax+rax+00h]
0x1800baef6  mov     rcx, [rsi]; pti
0x1800baef9  test    rcx, rcx
0x1800baefc  jz      short loc_1800BAF25
0x1800baefe  mov     r9d, 4E2h; msWindowLength
0x1800baf04  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800baf0d  xor     r8d, r8d; msPeriod
0x1800baf10  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800baf15  call    cs:__imp_SetThreadpoolTimer
0x1800baf1c  nop     dword ptr [rax+rax+00h]
0x1800baf21  mov     byte ptr [rdi+40h], 1
0x1800baf25  test    rbp, rbp
0x1800baf28  jz      short loc_1800BAF39
0x1800baf2a  mov     rcx, rbp; SRWLock
0x1800baf2d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800baf34  nop     dword ptr [rax+rax+00h]
0x1800baf39  mov     rcx, [rsp+68h+var_30]
0x1800baf3e  xor     rcx, rsp; StackCookie
0x1800baf41  call    __security_check_cookie
0x1800baf46  add     rsp, 40h
0x1800baf4a  pop     r14
0x1800baf4c  pop     rdi
0x1800baf4d  pop     rsi
0x1800baf4e  pop     rbp
0x1800baf4f  pop     rbx
0x1800baf50  retn
```
