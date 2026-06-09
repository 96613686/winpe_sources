# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140009940`
- end: `0x140009a9c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c920`

## callees

- `0x140009940`
- `0x14000d0ac`
- `0x14000d1a4`
- `0x14000ded8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009a7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009a7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009995`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009a38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009a38`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009a63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009a63`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009a1f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009a1f`

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
  int Source; // [rsp+20h] [rbp-28h] BYREF
  __int16 v13; // [rsp+24h] [rbp-24h]
  __int16 v14; // [rsp+26h] [rbp-22h]
  int v15; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( *pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v14 = 0;
    Source = a2;
    v13 = a3;
    v15 = a4;
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
0x140009940  mov     [rsp+arg_8], rbx
0x140009945  mov     [rsp+arg_10], rbp
0x14000994a  push    rsi
0x14000994b  push    rdi
0x14000994c  push    r14
0x14000994e  sub     rsp, 30h
0x140009952  mov     ebx, r9d
0x140009955  movzx   esi, r8w
0x140009959  mov     r14d, edx
0x14000995c  mov     rdi, rcx
0x14000995f  cmp     byte ptr [rcx], 0
0x140009962  jz      loc_140009A88
0x140009968  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000996f  jnz     loc_140009A88
0x140009975  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000997c  test    rax, rax
0x14000997f  jz      short loc_14000998E
0x140009981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009986  test    al, al
0x140009988  jnz     loc_140009A88
0x14000998e  lea     rbp, [rdi+28h]
0x140009992  mov     rcx, rbp; SRWLock
0x140009995  call    cs:__imp_AcquireSRWLockExclusive
0x14000999c  nop     dword ptr [rax+rax+00h]
0x1400099a1  xor     eax, eax
0x1400099a3  mov     [rsp+48h+var_22], ax
0x1400099a8  mov     [rsp+48h+Source], r14d
0x1400099ad  mov     [rsp+48h+var_24], si
0x1400099b2  mov     [rsp+48h+var_20], ebx
0x1400099b6  lea     rbx, [rdi+0E8h]
0x1400099bd  lea     esi, [rax+0Ch]
0x1400099c0  mov     edx, esi; unsigned __int64
0x1400099c2  mov     rcx, rbx; this
0x1400099c5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400099ca  test    al, al
0x1400099cc  jz      short loc_1400099F4
0x1400099ce  mov     rcx, [rbx+8]; Destination
0x1400099d2  mov     rax, [rbx+10h]
0x1400099d6  sub     rax, rcx
0x1400099d9  cmp     rcx, [rbx+10h]
0x1400099dd  sbb     rdx, rdx
0x1400099e0  and     rdx, rax; DestinationSize
0x1400099e3  mov     r9d, esi; SourceSize
0x1400099e6  lea     r8, [rsp+48h+Source]; Source
0x1400099eb  call    memcpy_s
0x1400099f0  add     [rbx+8], rsi
0x1400099f4  cmp     byte ptr [rdi+40h], 0
0x1400099f8  jnz     short loc_140009A73
0x1400099fa  lea     rsi, [rdi+38h]
0x1400099fe  cmp     qword ptr [rsi], 0
0x140009a02  jnz     short loc_140009A44
0x140009a04  call    cs:__imp_GetLastError
0x140009a0b  nop     dword ptr [rax+rax+00h]
0x140009a10  mov     ebx, eax
0x140009a12  xor     r8d, r8d; pcbe
0x140009a15  mov     rdx, rdi; pv
0x140009a18  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140009a1f  call    cs:__imp_CreateThreadpoolTimer
0x140009a26  nop     dword ptr [rax+rax+00h]
0x140009a2b  mov     rdx, rax
0x140009a2e  mov     rcx, rsi
0x140009a31  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140009a36  mov     ecx, ebx; dwErrCode
0x140009a38  call    cs:__imp_SetLastError
0x140009a3f  nop     dword ptr [rax+rax+00h]
0x140009a44  mov     rcx, [rsi]; pti
0x140009a47  test    rcx, rcx
0x140009a4a  jz      short loc_140009A73
0x140009a4c  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140009a55  mov     r9d, 4E2h; msWindowLength
0x140009a5b  xor     r8d, r8d; msPeriod
0x140009a5e  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x140009a63  call    cs:__imp_SetThreadpoolTimer
0x140009a6a  nop     dword ptr [rax+rax+00h]
0x140009a6f  mov     byte ptr [rdi+40h], 1
0x140009a73  test    rbp, rbp
0x140009a76  jz      short loc_140009A88
0x140009a78  mov     rcx, rbp; SRWLock
0x140009a7b  call    cs:__imp_ReleaseSRWLockExclusive
0x140009a82  nop     dword ptr [rax+rax+00h]
0x140009a87  nop
0x140009a88  mov     rbx, [rsp+48h+arg_8]
0x140009a8d  mov     rbp, [rsp+48h+arg_10]
0x140009a92  add     rsp, 30h
0x140009a96  pop     r14
0x140009a98  pop     rdi
0x140009a99  pop     rsi
0x140009a9a  retn
```
