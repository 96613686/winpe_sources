# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800099e0`
- end: `0x180009b3c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c760`

## callees

- `0x1800099e0`
- `0x18000ce0c`
- `0x18000cfb4`
- `0x180013bfc`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009a35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009a35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009b1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aa4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ad8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ad8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009b03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009b03`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009abf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009abf`

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
0x1800099e0  mov     [rsp+arg_8], rbx
0x1800099e5  mov     [rsp+arg_10], rbp
0x1800099ea  push    rsi
0x1800099eb  push    rdi
0x1800099ec  push    r14
0x1800099ee  sub     rsp, 30h
0x1800099f2  mov     ebx, r9d
0x1800099f5  movzx   esi, r8w
0x1800099f9  mov     r14d, edx
0x1800099fc  mov     rdi, rcx
0x1800099ff  cmp     byte ptr [rcx], 0
0x180009a02  jz      loc_180009B28
0x180009a08  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009a0f  jnz     loc_180009B28
0x180009a15  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009a1c  test    rax, rax
0x180009a1f  jz      short loc_180009A2E
0x180009a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a26  test    al, al
0x180009a28  jnz     loc_180009B28
0x180009a2e  lea     rbp, [rdi+28h]
0x180009a32  mov     rcx, rbp; SRWLock
0x180009a35  call    cs:__imp_AcquireSRWLockExclusive
0x180009a3c  nop     dword ptr [rax+rax+00h]
0x180009a41  xor     eax, eax
0x180009a43  mov     [rsp+48h+var_22], ax
0x180009a48  mov     [rsp+48h+Source], r14d
0x180009a4d  mov     [rsp+48h+var_24], si
0x180009a52  mov     [rsp+48h+var_20], ebx
0x180009a56  lea     rbx, [rdi+0E8h]
0x180009a5d  lea     esi, [rax+0Ch]
0x180009a60  mov     edx, esi; unsigned __int64
0x180009a62  mov     rcx, rbx; this
0x180009a65  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009a6a  test    al, al
0x180009a6c  jz      short loc_180009A94
0x180009a6e  mov     rcx, [rbx+8]; Destination
0x180009a72  mov     rax, [rbx+10h]
0x180009a76  sub     rax, rcx
0x180009a79  cmp     rcx, [rbx+10h]
0x180009a7d  sbb     rdx, rdx
0x180009a80  and     rdx, rax; DestinationSize
0x180009a83  mov     r9d, esi; SourceSize
0x180009a86  lea     r8, [rsp+48h+Source]; Source
0x180009a8b  call    memcpy_s
0x180009a90  add     [rbx+8], rsi
0x180009a94  cmp     byte ptr [rdi+40h], 0
0x180009a98  jnz     short loc_180009B13
0x180009a9a  lea     rsi, [rdi+38h]
0x180009a9e  cmp     qword ptr [rsi], 0
0x180009aa2  jnz     short loc_180009AE4
0x180009aa4  call    cs:__imp_GetLastError
0x180009aab  nop     dword ptr [rax+rax+00h]
0x180009ab0  mov     ebx, eax
0x180009ab2  xor     r8d, r8d; pcbe
0x180009ab5  mov     rdx, rdi; pv
0x180009ab8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009abf  call    cs:__imp_CreateThreadpoolTimer
0x180009ac6  nop     dword ptr [rax+rax+00h]
0x180009acb  mov     rdx, rax
0x180009ace  mov     rcx, rsi
0x180009ad1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009ad6  mov     ecx, ebx; dwErrCode
0x180009ad8  call    cs:__imp_SetLastError
0x180009adf  nop     dword ptr [rax+rax+00h]
0x180009ae4  mov     rcx, [rsi]; pti
0x180009ae7  test    rcx, rcx
0x180009aea  jz      short loc_180009B13
0x180009aec  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180009af5  mov     r9d, 4E2h; msWindowLength
0x180009afb  xor     r8d, r8d; msPeriod
0x180009afe  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180009b03  call    cs:__imp_SetThreadpoolTimer
0x180009b0a  nop     dword ptr [rax+rax+00h]
0x180009b0f  mov     byte ptr [rdi+40h], 1
0x180009b13  test    rbp, rbp
0x180009b16  jz      short loc_180009B28
0x180009b18  mov     rcx, rbp; SRWLock
0x180009b1b  call    cs:__imp_ReleaseSRWLockExclusive
0x180009b22  nop     dword ptr [rax+rax+00h]
0x180009b27  nop
0x180009b28  mov     rbx, [rsp+48h+arg_8]
0x180009b2d  mov     rbp, [rsp+48h+arg_10]
0x180009b32  add     rsp, 30h
0x180009b36  pop     r14
0x180009b38  pop     rdi
0x180009b39  pop     rsi
0x180009b3a  retn
```
