# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800baf58`
- end: `0x1800bb0e0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800bc6dc`

## callees

- `0x1800baf58`
- `0x1800bdd68`
- `0x1800be088`
- `0x1800eb010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800bb023`
- `msvcrt!memcpy_s` at `0x1800bb023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb043`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bb077`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bb077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb0c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb0c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bafa9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bafa9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800bb0a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800bb0a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bb05e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bb05e`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v6; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v9; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v11; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( *(_DWORD *)pv
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v11 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 48), 0x10u) )
      {
        memcpy_s(
          *((void *const *)pv + 7),
          (*((_QWORD *)pv + 8) - *((_QWORD *)pv + 7)) & -(__int64)(*((_QWORD *)pv + 7) < *((_QWORD *)pv + 8)),
          Source,
          0x10u);
        *((_QWORD *)pv + 7) += 16LL;
      }
      if ( !pv[24] )
      {
        v6 = (struct _TP_TIMER **)(pv + 16);
        if ( !*((_QWORD *)pv + 2) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)pv + 2,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v9 = *v6;
        if ( *v6 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v9, &pftDueTime, 0, 0x124F8u);
          pv[24] = 1;
        }
      }
    }
    if ( pv != (char *)-8LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
  }
}

```

## disassembly

```asm
0x1800baf58  mov     [rsp+arg_8], rbx
0x1800baf5d  mov     [rsp+arg_10], rbp
0x1800baf62  push    rsi
0x1800baf63  push    rdi
0x1800baf64  push    r14
0x1800baf66  sub     rsp, 30h
0x1800baf6a  mov     eax, [rcx]
0x1800baf6c  mov     rbx, r8
0x1800baf6f  mov     ebp, edx
0x1800baf71  mov     rdi, rcx
0x1800baf74  test    eax, eax
0x1800baf76  jz      loc_1800BB0CC
0x1800baf7c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800baf83  jnz     loc_1800BB0CC
0x1800baf89  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800baf90  test    rax, rax
0x1800baf93  jz      short loc_1800BAFA2
0x1800baf95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baf9a  test    al, al
0x1800baf9c  jnz     loc_1800BB0CC
0x1800bafa2  lea     rsi, [rdi+8]
0x1800bafa6  mov     rcx, rsi; SRWLock
0x1800bafa9  call    cs:__imp_AcquireSRWLockExclusive
0x1800bafb0  nop     dword ptr [rax+rax+00h]
0x1800bafb5  mov     eax, [rdi]
0x1800bafb7  test    eax, eax
0x1800bafb9  jz      loc_1800BB0B8
0x1800bafbf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800bafc6  jnz     loc_1800BB0B8
0x1800bafcc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800bafd3  test    rax, rax
0x1800bafd6  jz      short loc_1800BAFE5
0x1800bafd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bafdd  test    al, al
0x1800bafdf  jnz     loc_1800BB0B8
0x1800bafe5  xor     eax, eax
0x1800bafe7  mov     [rsp+48h+Source], ebp
0x1800bafeb  lea     rcx, [rdi+30h]; this
0x1800bafef  mov     [rsp+48h+var_24], eax
0x1800baff3  mov     [rsp+48h+var_20], rbx
0x1800baff8  lea     ebp, [rax+10h]
0x1800baffb  mov     edx, ebp; unsigned __int64
0x1800baffd  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800bb002  test    al, al
0x1800bb004  jz      short loc_1800BB033
0x1800bb006  mov     rcx, [rdi+38h]; Destination
0x1800bb00a  lea     r8, [rsp+48h+Source]; Source
0x1800bb00f  mov     rax, [rdi+40h]
0x1800bb013  mov     r9d, ebp; SourceSize
0x1800bb016  sub     rax, rcx
0x1800bb019  cmp     rcx, [rdi+40h]
0x1800bb01d  sbb     rdx, rdx
0x1800bb020  and     rdx, rax; DestinationSize
0x1800bb023  call    cs:__imp_memcpy_s
0x1800bb02a  nop     dword ptr [rax+rax+00h]
0x1800bb02f  add     [rdi+38h], rbp
0x1800bb033  cmp     byte ptr [rdi+18h], 0
0x1800bb037  jnz     short loc_1800BB0B8
0x1800bb039  lea     r14, [rdi+10h]
0x1800bb03d  cmp     qword ptr [r14], 0
0x1800bb041  jnz     short loc_1800BB083
0x1800bb043  call    cs:__imp_GetLastError
0x1800bb04a  nop     dword ptr [rax+rax+00h]
0x1800bb04f  xor     r8d, r8d; pcbe
0x1800bb052  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800bb059  mov     rdx, rdi; pv
0x1800bb05c  mov     ebx, eax
0x1800bb05e  call    cs:__imp_CreateThreadpoolTimer
0x1800bb065  nop     dword ptr [rax+rax+00h]
0x1800bb06a  mov     rdx, rax
0x1800bb06d  mov     rcx, r14
0x1800bb070  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800bb075  mov     ecx, ebx; dwErrCode
0x1800bb077  call    cs:__imp_SetLastError
0x1800bb07e  nop     dword ptr [rax+rax+00h]
0x1800bb083  mov     rcx, [r14]; pti
0x1800bb086  test    rcx, rcx
0x1800bb089  jz      short loc_1800BB0B8
0x1800bb08b  mov     rax, 0FFFFFFFF4D2FA200h
0x1800bb095  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800bb09a  mov     r9d, 124F8h; msWindowLength
0x1800bb0a0  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800bb0a5  xor     r8d, r8d; msPeriod
0x1800bb0a8  call    cs:__imp_SetThreadpoolTimer
0x1800bb0af  nop     dword ptr [rax+rax+00h]
0x1800bb0b4  mov     byte ptr [rdi+18h], 1
0x1800bb0b8  test    rsi, rsi
0x1800bb0bb  jz      short loc_1800BB0CC
0x1800bb0bd  mov     rcx, rsi; SRWLock
0x1800bb0c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bb0c7  nop     dword ptr [rax+rax+00h]
0x1800bb0cc  mov     rbx, [rsp+48h+arg_8]
0x1800bb0d1  mov     rbp, [rsp+48h+arg_10]
0x1800bb0d6  add     rsp, 30h
0x1800bb0da  pop     r14
0x1800bb0dc  pop     rdi
0x1800bb0dd  pop     rsi
0x1800bb0de  retn
```
