# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001cb50`
- end: `0x18001cc92`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `322`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001fe60`

## callees

- `0x18001cb50`
- `0x1800212d4`
- `0x180021468`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cbae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cbae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cc6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cc6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbf4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cc28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cc28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001cc53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001cc53`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001cc0f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001cc0f`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  int Source; // [rsp+20h] [rbp-28h] BYREF
  __int16 v13; // [rsp+24h] [rbp-24h]
  __int16 v14; // [rsp+26h] [rbp-22h]
  int v15; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v14 = 0;
    Source = a2;
    v13 = a3;
    v15 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[29], &Source, 0xCu);
    v8 = (struct _TP_TIMER **)&pv[7];
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !*v8 )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)&pv[7],
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x18001cb50  mov     [rsp+arg_8], rbx
0x18001cb55  mov     [rsp+arg_10], rbp
0x18001cb5a  mov     [rsp+arg_18], rsi
0x18001cb5f  push    rdi
0x18001cb60  push    r14
0x18001cb62  push    r15
0x18001cb64  sub     rsp, 30h
0x18001cb68  mov     ebx, r9d
0x18001cb6b  movzx   ebp, r8w
0x18001cb6f  mov     r14d, edx
0x18001cb72  mov     rdi, rcx
0x18001cb75  xor     r15d, r15d
0x18001cb78  cmp     [rcx], r15b
0x18001cb7b  jz      loc_18001CC78
0x18001cb81  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x18001cb88  jnz     loc_18001CC78
0x18001cb8e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001cb95  test    rax, rax
0x18001cb98  jz      short loc_18001CBA7
0x18001cb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb9f  test    al, al
0x18001cba1  jnz     loc_18001CC78
0x18001cba7  lea     rsi, [rdi+28h]
0x18001cbab  mov     rcx, rsi; SRWLock
0x18001cbae  call    cs:__imp_AcquireSRWLockExclusive
0x18001cbb5  nop     dword ptr [rax+rax+00h]
0x18001cbba  mov     [rsp+48h+var_22], r15w
0x18001cbc0  mov     [rsp+48h+Source], r14d
0x18001cbc5  mov     [rsp+48h+var_24], bp
0x18001cbca  mov     [rsp+48h+var_20], ebx
0x18001cbce  lea     rcx, [rdi+0E8h]; this
0x18001cbd5  mov     r8d, 0Ch; SourceSize
0x18001cbdb  lea     rdx, [rsp+48h+Source]; Source
0x18001cbe0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001cbe5  lea     r14, [rdi+38h]
0x18001cbe9  cmp     [rdi+40h], r15b
0x18001cbed  jnz     short loc_18001CC63
0x18001cbef  cmp     [r14], r15
0x18001cbf2  jnz     short loc_18001CC34
0x18001cbf4  call    cs:__imp_GetLastError
0x18001cbfb  nop     dword ptr [rax+rax+00h]
0x18001cc00  mov     ebx, eax
0x18001cc02  xor     r8d, r8d; pcbe
0x18001cc05  mov     rdx, rdi; pv
0x18001cc08  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001cc0f  call    cs:__imp_CreateThreadpoolTimer
0x18001cc16  nop     dword ptr [rax+rax+00h]
0x18001cc1b  mov     rdx, rax
0x18001cc1e  mov     rcx, r14
0x18001cc21  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001cc26  mov     ecx, ebx; dwErrCode
0x18001cc28  call    cs:__imp_SetLastError
0x18001cc2f  nop     dword ptr [rax+rax+00h]
0x18001cc34  mov     rcx, [r14]; pti
0x18001cc37  test    rcx, rcx
0x18001cc3a  jz      short loc_18001CC63
0x18001cc3c  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18001cc45  mov     r9d, 4E2h; msWindowLength
0x18001cc4b  xor     r8d, r8d; msPeriod
0x18001cc4e  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001cc53  call    cs:__imp_SetThreadpoolTimer
0x18001cc5a  nop     dword ptr [rax+rax+00h]
0x18001cc5f  mov     byte ptr [rdi+40h], 1
0x18001cc63  test    rsi, rsi
0x18001cc66  jz      short loc_18001CC78
0x18001cc68  mov     rcx, rsi; SRWLock
0x18001cc6b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cc72  nop     dword ptr [rax+rax+00h]
0x18001cc77  nop
0x18001cc78  mov     rbx, [rsp+48h+arg_8]
0x18001cc7d  mov     rbp, [rsp+48h+arg_10]
0x18001cc82  mov     rsi, [rsp+48h+arg_18]
0x18001cc87  add     rsp, 30h
0x18001cc8b  pop     r15
0x18001cc8d  pop     r14
0x18001cc8f  pop     rdi
0x18001cc90  retn
```
