# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001d708`
- end: `0x18001d864`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180020ce0`

## callees

- `0x18001108c`
- `0x18001d708`
- `0x1800217b8`
- `0x180021d08`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d75d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d75d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d843`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d843`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d800`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d82b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d82b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d7e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d7e7`

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
0x18001d708  mov     [rsp+arg_8], rbx
0x18001d70d  mov     [rsp+arg_10], rbp
0x18001d712  push    rsi
0x18001d713  push    rdi
0x18001d714  push    r14
0x18001d716  sub     rsp, 30h
0x18001d71a  mov     ebx, r9d
0x18001d71d  movzx   esi, r8w
0x18001d721  mov     r14d, edx
0x18001d724  mov     rdi, rcx
0x18001d727  cmp     byte ptr [rcx], 0
0x18001d72a  jz      loc_18001D850
0x18001d730  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d737  jnz     loc_18001D850
0x18001d73d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d744  test    rax, rax
0x18001d747  jz      short loc_18001D756
0x18001d749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d74e  test    al, al
0x18001d750  jnz     loc_18001D850
0x18001d756  lea     rbp, [rdi+28h]
0x18001d75a  mov     rcx, rbp; SRWLock
0x18001d75d  call    cs:__imp_AcquireSRWLockExclusive
0x18001d764  nop     dword ptr [rax+rax+00h]
0x18001d769  xor     eax, eax
0x18001d76b  mov     [rsp+48h+var_22], ax
0x18001d770  mov     [rsp+48h+Source], r14d
0x18001d775  mov     [rsp+48h+var_24], si
0x18001d77a  mov     [rsp+48h+var_20], ebx
0x18001d77e  lea     rbx, [rdi+0E8h]
0x18001d785  lea     esi, [rax+0Ch]
0x18001d788  mov     edx, esi; unsigned __int64
0x18001d78a  mov     rcx, rbx; this
0x18001d78d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001d792  test    al, al
0x18001d794  jz      short loc_18001D7BC
0x18001d796  mov     rcx, [rbx+8]; Destination
0x18001d79a  mov     rax, [rbx+10h]
0x18001d79e  sub     rax, rcx
0x18001d7a1  cmp     rcx, [rbx+10h]
0x18001d7a5  sbb     rdx, rdx
0x18001d7a8  and     rdx, rax; DestinationSize
0x18001d7ab  mov     r9d, esi; SourceSize
0x18001d7ae  lea     r8, [rsp+48h+Source]; Source
0x18001d7b3  call    memcpy_s
0x18001d7b8  add     [rbx+8], rsi
0x18001d7bc  cmp     byte ptr [rdi+40h], 0
0x18001d7c0  jnz     short loc_18001D83B
0x18001d7c2  lea     rsi, [rdi+38h]
0x18001d7c6  cmp     qword ptr [rsi], 0
0x18001d7ca  jnz     short loc_18001D80C
0x18001d7cc  call    cs:__imp_GetLastError
0x18001d7d3  nop     dword ptr [rax+rax+00h]
0x18001d7d8  mov     ebx, eax
0x18001d7da  xor     r8d, r8d; pcbe
0x18001d7dd  mov     rdx, rdi; pv
0x18001d7e0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d7e7  call    cs:__imp_CreateThreadpoolTimer
0x18001d7ee  nop     dword ptr [rax+rax+00h]
0x18001d7f3  mov     rdx, rax
0x18001d7f6  mov     rcx, rsi
0x18001d7f9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001d7fe  mov     ecx, ebx; dwErrCode
0x18001d800  call    cs:__imp_SetLastError
0x18001d807  nop     dword ptr [rax+rax+00h]
0x18001d80c  mov     rcx, [rsi]; pti
0x18001d80f  test    rcx, rcx
0x18001d812  jz      short loc_18001D83B
0x18001d814  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18001d81d  mov     r9d, 4E2h; msWindowLength
0x18001d823  xor     r8d, r8d; msPeriod
0x18001d826  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001d82b  call    cs:__imp_SetThreadpoolTimer
0x18001d832  nop     dword ptr [rax+rax+00h]
0x18001d837  mov     byte ptr [rdi+40h], 1
0x18001d83b  test    rbp, rbp
0x18001d83e  jz      short loc_18001D850
0x18001d840  mov     rcx, rbp; SRWLock
0x18001d843  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d84a  nop     dword ptr [rax+rax+00h]
0x18001d84f  nop
0x18001d850  mov     rbx, [rsp+48h+arg_8]
0x18001d855  mov     rbp, [rsp+48h+arg_10]
0x18001d85a  add     rsp, 30h
0x18001d85e  pop     r14
0x18001d860  pop     rdi
0x18001d861  pop     rsi
0x18001d862  retn
```
