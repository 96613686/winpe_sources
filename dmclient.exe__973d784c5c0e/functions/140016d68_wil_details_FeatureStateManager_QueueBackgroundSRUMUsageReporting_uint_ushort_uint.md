# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140016d68`
- end: `0x140016ed7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `367`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140018430`

## callees

- `0x140016d68`
- `0x14001898c`
- `0x140018a8c`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140016e1a`
- `msvcrt!memcpy_s` at `0x140016e1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016dc4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016dc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016eb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016e3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016e6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016e6e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140016e99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140016e99`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140016e55`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140016e55`

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
0x140016d68  push    rbx
0x140016d6a  push    rbp
0x140016d6b  push    rsi
0x140016d6c  push    rdi
0x140016d6d  push    r14
0x140016d6f  sub     rsp, 40h
0x140016d73  mov     rax, cs:__security_cookie
0x140016d7a  xor     rax, rsp
0x140016d7d  mov     [rsp+68h+var_30], rax
0x140016d82  mov     r14d, r9d
0x140016d85  movzx   esi, r8w
0x140016d89  mov     ebx, edx
0x140016d8b  mov     rdi, rcx
0x140016d8e  cmp     byte ptr [rcx], 0
0x140016d91  jz      loc_140016EBE
0x140016d97  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140016d9e  jnz     loc_140016EBE
0x140016da4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140016dab  test    rax, rax
0x140016dae  jz      short loc_140016DBD
0x140016db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016db5  test    al, al
0x140016db7  jnz     loc_140016EBE
0x140016dbd  lea     rbp, [rdi+28h]
0x140016dc1  mov     rcx, rbp; SRWLock
0x140016dc4  call    cs:__imp_AcquireSRWLockExclusive
0x140016dcb  nop     dword ptr [rax+rax+00h]
0x140016dd0  xor     eax, eax
0x140016dd2  mov     [rsp+68h+var_3A], ax
0x140016dd7  mov     [rsp+68h+Source], ebx
0x140016ddb  mov     [rsp+68h+var_3C], si
0x140016de0  mov     [rsp+68h+var_38], r14d
0x140016de5  lea     rbx, [rdi+0E8h]
0x140016dec  lea     esi, [rax+0Ch]
0x140016def  mov     edx, esi; unsigned __int64
0x140016df1  mov     rcx, rbx; this
0x140016df4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140016df9  test    al, al
0x140016dfb  jz      short loc_140016E2A
0x140016dfd  mov     rcx, [rbx+8]; Destination
0x140016e01  mov     rax, [rbx+10h]
0x140016e05  sub     rax, rcx
0x140016e08  cmp     rcx, [rbx+10h]
0x140016e0c  sbb     rdx, rdx
0x140016e0f  and     rdx, rax; DestinationSize
0x140016e12  mov     r9d, esi; SourceSize
0x140016e15  lea     r8, [rsp+68h+Source]; Source
0x140016e1a  call    cs:__imp_memcpy_s
0x140016e21  nop     dword ptr [rax+rax+00h]
0x140016e26  add     [rbx+8], rsi
0x140016e2a  cmp     byte ptr [rdi+40h], 0
0x140016e2e  jnz     short loc_140016EA9
0x140016e30  lea     rsi, [rdi+38h]
0x140016e34  cmp     qword ptr [rsi], 0
0x140016e38  jnz     short loc_140016E7A
0x140016e3a  call    cs:__imp_GetLastError
0x140016e41  nop     dword ptr [rax+rax+00h]
0x140016e46  mov     ebx, eax
0x140016e48  xor     r8d, r8d; pcbe
0x140016e4b  mov     rdx, rdi; pv
0x140016e4e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140016e55  call    cs:__imp_CreateThreadpoolTimer
0x140016e5c  nop     dword ptr [rax+rax+00h]
0x140016e61  mov     rdx, rax
0x140016e64  mov     rcx, rsi
0x140016e67  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140016e6c  mov     ecx, ebx; dwErrCode
0x140016e6e  call    cs:__imp_SetLastError
0x140016e75  nop     dword ptr [rax+rax+00h]
0x140016e7a  mov     rcx, [rsi]; pti
0x140016e7d  test    rcx, rcx
0x140016e80  jz      short loc_140016EA9
0x140016e82  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140016e8b  mov     r9d, 4E2h; msWindowLength
0x140016e91  xor     r8d, r8d; msPeriod
0x140016e94  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140016e99  call    cs:__imp_SetThreadpoolTimer
0x140016ea0  nop     dword ptr [rax+rax+00h]
0x140016ea5  mov     byte ptr [rdi+40h], 1
0x140016ea9  test    rbp, rbp
0x140016eac  jz      short loc_140016EBE
0x140016eae  mov     rcx, rbp; SRWLock
0x140016eb1  call    cs:__imp_ReleaseSRWLockExclusive
0x140016eb8  nop     dword ptr [rax+rax+00h]
0x140016ebd  nop
0x140016ebe  mov     rcx, [rsp+68h+var_30]
0x140016ec3  xor     rcx, rsp; StackCookie
0x140016ec6  call    __security_check_cookie
0x140016ecb  add     rsp, 40h
0x140016ecf  pop     r14
0x140016ed1  pop     rdi
0x140016ed2  pop     rsi
0x140016ed3  pop     rbp
0x140016ed4  pop     rbx
0x140016ed5  retn
```
