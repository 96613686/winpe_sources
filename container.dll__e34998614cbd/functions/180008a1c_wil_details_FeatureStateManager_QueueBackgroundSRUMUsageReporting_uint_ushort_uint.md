# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008a1c`
- end: `0x180008b78`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b8c0`

## callees

- `0x180008a1c`
- `0x18000c008`
- `0x18000c100`
- `0x18000c498`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008a71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008a71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ae0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008b3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008b3f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008afb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008afb`

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
0x180008a1c  mov     [rsp+arg_8], rbx
0x180008a21  mov     [rsp+arg_10], rbp
0x180008a26  push    rsi
0x180008a27  push    rdi
0x180008a28  push    r14
0x180008a2a  sub     rsp, 30h
0x180008a2e  mov     ebx, r9d
0x180008a31  movzx   esi, r8w
0x180008a35  mov     r14d, edx
0x180008a38  mov     rdi, rcx
0x180008a3b  cmp     byte ptr [rcx], 0
0x180008a3e  jz      loc_180008B64
0x180008a44  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008a4b  jnz     loc_180008B64
0x180008a51  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008a58  test    rax, rax
0x180008a5b  jz      short loc_180008A6A
0x180008a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a62  test    al, al
0x180008a64  jnz     loc_180008B64
0x180008a6a  lea     rbp, [rdi+28h]
0x180008a6e  mov     rcx, rbp; SRWLock
0x180008a71  call    cs:__imp_AcquireSRWLockExclusive
0x180008a78  nop     dword ptr [rax+rax+00h]
0x180008a7d  xor     eax, eax
0x180008a7f  mov     [rsp+48h+var_22], ax
0x180008a84  mov     [rsp+48h+Source], r14d
0x180008a89  mov     [rsp+48h+var_24], si
0x180008a8e  mov     [rsp+48h+var_20], ebx
0x180008a92  lea     rbx, [rdi+0E8h]
0x180008a99  lea     esi, [rax+0Ch]
0x180008a9c  mov     edx, esi; unsigned __int64
0x180008a9e  mov     rcx, rbx; this
0x180008aa1  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008aa6  test    al, al
0x180008aa8  jz      short loc_180008AD0
0x180008aaa  mov     rcx, [rbx+8]; Destination
0x180008aae  mov     rax, [rbx+10h]
0x180008ab2  sub     rax, rcx
0x180008ab5  cmp     rcx, [rbx+10h]
0x180008ab9  sbb     rdx, rdx
0x180008abc  and     rdx, rax; DestinationSize
0x180008abf  mov     r9d, esi; SourceSize
0x180008ac2  lea     r8, [rsp+48h+Source]; Source
0x180008ac7  call    memcpy_s
0x180008acc  add     [rbx+8], rsi
0x180008ad0  cmp     byte ptr [rdi+40h], 0
0x180008ad4  jnz     short loc_180008B4F
0x180008ad6  lea     rsi, [rdi+38h]
0x180008ada  cmp     qword ptr [rsi], 0
0x180008ade  jnz     short loc_180008B20
0x180008ae0  call    cs:__imp_GetLastError
0x180008ae7  nop     dword ptr [rax+rax+00h]
0x180008aec  mov     ebx, eax
0x180008aee  xor     r8d, r8d; pcbe
0x180008af1  mov     rdx, rdi; pv
0x180008af4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008afb  call    cs:__imp_CreateThreadpoolTimer
0x180008b02  nop     dword ptr [rax+rax+00h]
0x180008b07  mov     rdx, rax
0x180008b0a  mov     rcx, rsi
0x180008b0d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008b12  mov     ecx, ebx; dwErrCode
0x180008b14  call    cs:__imp_SetLastError
0x180008b1b  nop     dword ptr [rax+rax+00h]
0x180008b20  mov     rcx, [rsi]; pti
0x180008b23  test    rcx, rcx
0x180008b26  jz      short loc_180008B4F
0x180008b28  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180008b31  mov     r9d, 4E2h; msWindowLength
0x180008b37  xor     r8d, r8d; msPeriod
0x180008b3a  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180008b3f  call    cs:__imp_SetThreadpoolTimer
0x180008b46  nop     dword ptr [rax+rax+00h]
0x180008b4b  mov     byte ptr [rdi+40h], 1
0x180008b4f  test    rbp, rbp
0x180008b52  jz      short loc_180008B64
0x180008b54  mov     rcx, rbp; SRWLock
0x180008b57  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b5e  nop     dword ptr [rax+rax+00h]
0x180008b63  nop
0x180008b64  mov     rbx, [rsp+48h+arg_8]
0x180008b69  mov     rbp, [rsp+48h+arg_10]
0x180008b6e  add     rsp, 30h
0x180008b72  pop     r14
0x180008b74  pop     rdi
0x180008b75  pop     rsi
0x180008b76  retn
```
