# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180010220`
- end: `0x18001037c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800138d0`

## callees

- `0x18000649c`
- `0x180010220`
- `0x180013f2c`
- `0x1800142b8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010318`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001035b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001035b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010275`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010275`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800102ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800102ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010343`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010343`

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
0x180010220  mov     [rsp+arg_8], rbx
0x180010225  mov     [rsp+arg_10], rbp
0x18001022a  push    rsi
0x18001022b  push    rdi
0x18001022c  push    r14
0x18001022e  sub     rsp, 30h
0x180010232  mov     ebx, r9d
0x180010235  movzx   esi, r8w
0x180010239  mov     r14d, edx
0x18001023c  mov     rdi, rcx
0x18001023f  cmp     byte ptr [rcx], 0
0x180010242  jz      loc_180010368
0x180010248  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001024f  jnz     loc_180010368
0x180010255  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001025c  test    rax, rax
0x18001025f  jz      short loc_18001026E
0x180010261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010266  test    al, al
0x180010268  jnz     loc_180010368
0x18001026e  lea     rbp, [rdi+28h]
0x180010272  mov     rcx, rbp; SRWLock
0x180010275  call    cs:__imp_AcquireSRWLockExclusive
0x18001027c  nop     dword ptr [rax+rax+00h]
0x180010281  xor     eax, eax
0x180010283  mov     [rsp+48h+var_22], ax
0x180010288  mov     [rsp+48h+Source], r14d
0x18001028d  mov     [rsp+48h+var_24], si
0x180010292  mov     [rsp+48h+var_20], ebx
0x180010296  lea     rbx, [rdi+0E8h]
0x18001029d  lea     esi, [rax+0Ch]
0x1800102a0  mov     edx, esi; unsigned __int64
0x1800102a2  mov     rcx, rbx; this
0x1800102a5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800102aa  test    al, al
0x1800102ac  jz      short loc_1800102D4
0x1800102ae  mov     rcx, [rbx+8]; Destination
0x1800102b2  mov     rax, [rbx+10h]
0x1800102b6  sub     rax, rcx
0x1800102b9  cmp     rcx, [rbx+10h]
0x1800102bd  sbb     rdx, rdx
0x1800102c0  and     rdx, rax; DestinationSize
0x1800102c3  mov     r9d, esi; SourceSize
0x1800102c6  lea     r8, [rsp+48h+Source]; Source
0x1800102cb  call    memcpy_s
0x1800102d0  add     [rbx+8], rsi
0x1800102d4  cmp     byte ptr [rdi+40h], 0
0x1800102d8  jnz     short loc_180010353
0x1800102da  lea     rsi, [rdi+38h]
0x1800102de  cmp     qword ptr [rsi], 0
0x1800102e2  jnz     short loc_180010324
0x1800102e4  call    cs:__imp_GetLastError
0x1800102eb  nop     dword ptr [rax+rax+00h]
0x1800102f0  mov     ebx, eax
0x1800102f2  xor     r8d, r8d; pcbe
0x1800102f5  mov     rdx, rdi; pv
0x1800102f8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800102ff  call    cs:__imp_CreateThreadpoolTimer
0x180010306  nop     dword ptr [rax+rax+00h]
0x18001030b  mov     rdx, rax
0x18001030e  mov     rcx, rsi
0x180010311  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180010316  mov     ecx, ebx; dwErrCode
0x180010318  call    cs:__imp_SetLastError
0x18001031f  nop     dword ptr [rax+rax+00h]
0x180010324  mov     rcx, [rsi]; pti
0x180010327  test    rcx, rcx
0x18001032a  jz      short loc_180010353
0x18001032c  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180010335  mov     r9d, 4E2h; msWindowLength
0x18001033b  xor     r8d, r8d; msPeriod
0x18001033e  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180010343  call    cs:__imp_SetThreadpoolTimer
0x18001034a  nop     dword ptr [rax+rax+00h]
0x18001034f  mov     byte ptr [rdi+40h], 1
0x180010353  test    rbp, rbp
0x180010356  jz      short loc_180010368
0x180010358  mov     rcx, rbp; SRWLock
0x18001035b  call    cs:__imp_ReleaseSRWLockExclusive
0x180010362  nop     dword ptr [rax+rax+00h]
0x180010367  nop
0x180010368  mov     rbx, [rsp+48h+arg_8]
0x18001036d  mov     rbp, [rsp+48h+arg_10]
0x180010372  add     rsp, 30h
0x180010376  pop     r14
0x180010378  pop     rdi
0x180010379  pop     rsi
0x18001037a  retn
```
