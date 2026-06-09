# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001715c`
- end: `0x1800172ce`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `370`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180018030`

## callees

- `0x18000b7a8`
- `0x18000b8a0`
- `0x18000bd1c`
- `0x18001715c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800171a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800171a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800172b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800172b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001726d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001726d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017239`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017254`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017254`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001729e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001729e`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v5; // r14
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v8; // rcx
  _QWORD Source[7]; // [rsp+20h] [rbp-38h] BYREF
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = 53100131;
      Source[1] = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
      {
        memcpy_s(pv[5].Ptr, ((char *)pv[6].Ptr - (char *)pv[5].Ptr) & -(__int64)(pv[5].Ptr < pv[6].Ptr), Source, 0x10u);
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
      }
      if ( !LOBYTE(pv[3].Ptr) )
      {
        v5 = (struct _TP_TIMER **)&pv[2];
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            &pv[2],
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v8 = *v5;
        if ( *v5 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v8, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x18001715c  push    rbx
0x18001715e  push    rsi
0x18001715f  push    rdi
0x180017160  push    r14
0x180017162  sub     rsp, 38h
0x180017166  mov     rbx, r8
0x180017169  mov     rdi, rcx
0x18001716c  mov     eax, [rcx]
0x18001716e  test    eax, eax
0x180017170  jz      loc_1800172C3
0x180017176  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001717d  jnz     loc_1800172C3
0x180017183  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001718a  test    rax, rax
0x18001718d  jz      short loc_18001719C
0x18001718f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017194  test    al, al
0x180017196  jnz     loc_1800172C3
0x18001719c  lea     rsi, [rdi+8]
0x1800171a0  mov     rcx, rsi; SRWLock
0x1800171a3  call    cs:__imp_AcquireSRWLockExclusive
0x1800171aa  nop     dword ptr [rax+rax+00h]
0x1800171af  mov     eax, [rdi]
0x1800171b1  test    eax, eax
0x1800171b3  jz      loc_1800172AE
0x1800171b9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800171c0  jnz     loc_1800172AE
0x1800171c6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800171cd  test    rax, rax
0x1800171d0  jz      short loc_1800171DF
0x1800171d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171d7  test    al, al
0x1800171d9  jnz     loc_1800172AE
0x1800171df  mov     [rsp+58h+Source], 32A3E63h
0x1800171e8  mov     [rsp+58h+var_30], rbx
0x1800171ed  mov     r14d, 10h
0x1800171f3  mov     edx, r14d; unsigned __int64
0x1800171f6  lea     rcx, [rdi+20h]; this
0x1800171fa  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800171ff  test    al, al
0x180017201  jz      short loc_180017229
0x180017203  mov     rcx, [rdi+28h]; Destination
0x180017207  mov     rax, [rdi+30h]
0x18001720b  sub     rax, rcx
0x18001720e  cmp     rcx, [rdi+30h]
0x180017212  sbb     rdx, rdx
0x180017215  and     rdx, rax; DestinationSize
0x180017218  mov     r9d, r14d; SourceSize
0x18001721b  lea     r8, [rsp+58h+Source]; Source
0x180017220  call    memcpy_s
0x180017225  add     [rdi+28h], r14
0x180017229  cmp     byte ptr [rdi+18h], 0
0x18001722d  jnz     short loc_1800172AE
0x18001722f  lea     r14, [rdi+10h]
0x180017233  cmp     qword ptr [r14], 0
0x180017237  jnz     short loc_180017279
0x180017239  call    cs:__imp_GetLastError
0x180017240  nop     dword ptr [rax+rax+00h]
0x180017245  mov     ebx, eax
0x180017247  xor     r8d, r8d; pcbe
0x18001724a  mov     rdx, rdi; pv
0x18001724d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017254  call    cs:__imp_CreateThreadpoolTimer
0x18001725b  nop     dword ptr [rax+rax+00h]
0x180017260  mov     rdx, rax
0x180017263  mov     rcx, r14
0x180017266  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001726b  mov     ecx, ebx; dwErrCode
0x18001726d  call    cs:__imp_SetLastError
0x180017274  nop     dword ptr [rax+rax+00h]
0x180017279  mov     rcx, [r14]; pti
0x18001727c  test    rcx, rcx
0x18001727f  jz      short loc_1800172AE
0x180017281  mov     rax, 0FFFFFFFF4D2FA200h
0x18001728b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180017290  mov     r9d, 124F8h; msWindowLength
0x180017296  xor     r8d, r8d; msPeriod
0x180017299  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001729e  call    cs:__imp_SetThreadpoolTimer
0x1800172a5  nop     dword ptr [rax+rax+00h]
0x1800172aa  mov     byte ptr [rdi+18h], 1
0x1800172ae  test    rsi, rsi
0x1800172b1  jz      short loc_1800172C3
0x1800172b3  mov     rcx, rsi; SRWLock
0x1800172b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800172bd  nop     dword ptr [rax+rax+00h]
0x1800172c2  nop
0x1800172c3  add     rsp, 38h
0x1800172c7  pop     r14
0x1800172c9  pop     rdi
0x1800172ca  pop     rsi
0x1800172cb  pop     rbx
0x1800172cc  retn
```
