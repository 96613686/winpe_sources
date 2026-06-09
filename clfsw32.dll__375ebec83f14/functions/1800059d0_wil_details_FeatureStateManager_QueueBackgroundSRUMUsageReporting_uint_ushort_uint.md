# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800059d0`
- end: `0x180005b3e`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `366`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800079d0`

## callees

- `0x1800059d0`
- `0x180007f3c`
- `0x18000803c`
- `0x180014e00`
- `0x180016010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005a82`
- `msvcrt!memcpy_s` at `0x180005a82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ad6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aa2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005a2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005a2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005b01`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005b01`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005abd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005abd`

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
0x1800059d0  push    rbx
0x1800059d2  push    rbp
0x1800059d3  push    rsi
0x1800059d4  push    rdi
0x1800059d5  push    r14
0x1800059d7  sub     rsp, 40h
0x1800059db  mov     rax, cs:__security_cookie
0x1800059e2  xor     rax, rsp
0x1800059e5  mov     [rsp+68h+var_30], rax
0x1800059ea  cmp     byte ptr [rcx], 0
0x1800059ed  mov     r14d, r9d
0x1800059f0  movzx   esi, r8w
0x1800059f4  mov     ebx, edx
0x1800059f6  mov     rdi, rcx
0x1800059f9  jz      loc_180005B25
0x1800059ff  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005a06  jnz     loc_180005B25
0x180005a0c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005a13  test    rax, rax
0x180005a16  jz      short loc_180005A25
0x180005a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a1d  test    al, al
0x180005a1f  jnz     loc_180005B25
0x180005a25  lea     rbp, [rdi+28h]
0x180005a29  mov     rcx, rbp; SRWLock
0x180005a2c  call    cs:__imp_AcquireSRWLockExclusive
0x180005a33  nop     dword ptr [rax+rax+00h]
0x180005a38  xor     eax, eax
0x180005a3a  mov     [rsp+68h+Source], ebx
0x180005a3e  mov     [rsp+68h+var_3C], si
0x180005a43  lea     rbx, [rdi+0E8h]
0x180005a4a  mov     rcx, rbx; this
0x180005a4d  mov     [rsp+68h+var_3A], ax
0x180005a52  mov     [rsp+68h+var_38], r14d
0x180005a57  lea     esi, [rax+0Ch]
0x180005a5a  mov     edx, esi; unsigned __int64
0x180005a5c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005a61  test    al, al
0x180005a63  jz      short loc_180005A92
0x180005a65  mov     rcx, [rbx+8]; Destination
0x180005a69  lea     r8, [rsp+68h+Source]; Source
0x180005a6e  mov     rax, [rbx+10h]
0x180005a72  mov     r9d, esi; SourceSize
0x180005a75  sub     rax, rcx
0x180005a78  cmp     rcx, [rbx+10h]
0x180005a7c  sbb     rdx, rdx
0x180005a7f  and     rdx, rax; DestinationSize
0x180005a82  call    cs:__imp_memcpy_s
0x180005a89  nop     dword ptr [rax+rax+00h]
0x180005a8e  add     [rbx+8], rsi
0x180005a92  cmp     byte ptr [rdi+40h], 0
0x180005a96  jnz     short loc_180005B11
0x180005a98  lea     rsi, [rdi+38h]
0x180005a9c  cmp     qword ptr [rsi], 0
0x180005aa0  jnz     short loc_180005AE2
0x180005aa2  call    cs:__imp_GetLastError
0x180005aa9  nop     dword ptr [rax+rax+00h]
0x180005aae  xor     r8d, r8d; pcbe
0x180005ab1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005ab8  mov     rdx, rdi; pv
0x180005abb  mov     ebx, eax
0x180005abd  call    cs:__imp_CreateThreadpoolTimer
0x180005ac4  nop     dword ptr [rax+rax+00h]
0x180005ac9  mov     rdx, rax
0x180005acc  mov     rcx, rsi
0x180005acf  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005ad4  mov     ecx, ebx; dwErrCode
0x180005ad6  call    cs:__imp_SetLastError
0x180005add  nop     dword ptr [rax+rax+00h]
0x180005ae2  mov     rcx, [rsi]; pti
0x180005ae5  test    rcx, rcx
0x180005ae8  jz      short loc_180005B11
0x180005aea  mov     r9d, 4E2h; msWindowLength
0x180005af0  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180005af9  xor     r8d, r8d; msPeriod
0x180005afc  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180005b01  call    cs:__imp_SetThreadpoolTimer
0x180005b08  nop     dword ptr [rax+rax+00h]
0x180005b0d  mov     byte ptr [rdi+40h], 1
0x180005b11  test    rbp, rbp
0x180005b14  jz      short loc_180005B25
0x180005b16  mov     rcx, rbp; SRWLock
0x180005b19  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b20  nop     dword ptr [rax+rax+00h]
0x180005b25  mov     rcx, [rsp+68h+var_30]
0x180005b2a  xor     rcx, rsp; StackCookie
0x180005b2d  call    __security_check_cookie
0x180005b32  add     rsp, 40h
0x180005b36  pop     r14
0x180005b38  pop     rdi
0x180005b39  pop     rsi
0x180005b3a  pop     rbp
0x180005b3b  pop     rbx
0x180005b3c  retn
```
