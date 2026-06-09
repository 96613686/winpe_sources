# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180022a2c`
- end: `0x180022bbf`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180023d68`

## callees

- `0x180022a2c`
- `0x180024b74`
- `0x18003f010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180022aeb`
- `msvcrt!memcpy_s` at `0x180022aeb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022a76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022a76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022bab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022bab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022b60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022b6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022b60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022b6d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180022b1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180022b1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022b41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022b99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022b41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022b99`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022b4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022b4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022b58`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022b58`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v8; // ebx
  struct _TP_TIMER *v9; // rcx
  _QWORD Source[9]; // [rsp+20h] [rbp-48h] BYREF
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = 27656178;
      Source[1] = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
      {
        memcpy_s(pv[5].Ptr, ((char *)pv[6].Ptr - (char *)pv[5].Ptr) & -(__int64)(pv[5].Ptr < pv[6].Ptr), Source, 0x10u);
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
      }
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v8 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v8);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v9 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v9 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v9, &pftDueTime, 0, 0x124F8u);
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
0x180022a2c  push    rbx
0x180022a2e  push    rbp
0x180022a2f  push    rsi
0x180022a30  push    rdi
0x180022a31  push    r14
0x180022a33  push    r15
0x180022a35  sub     rsp, 38h
0x180022a39  mov     rbx, r8
0x180022a3c  mov     rdi, rcx
0x180022a3f  mov     eax, [rcx]
0x180022a41  test    eax, eax
0x180022a43  jz      loc_180022BB2
0x180022a49  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180022a50  jnz     loc_180022BB2
0x180022a56  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180022a5d  test    rax, rax
0x180022a60  jz      short loc_180022A6F
0x180022a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a67  test    al, al
0x180022a69  jnz     loc_180022BB2
0x180022a6f  lea     rsi, [rdi+8]
0x180022a73  mov     rcx, rsi; SRWLock
0x180022a76  call    cs:__imp_AcquireSRWLockExclusive
0x180022a7c  mov     eax, [rdi]
0x180022a7e  test    eax, eax
0x180022a80  jz      loc_180022BA3
0x180022a86  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180022a8d  jnz     loc_180022BA3
0x180022a93  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180022a9a  test    rax, rax
0x180022a9d  jz      short loc_180022AAC
0x180022a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022aa4  test    al, al
0x180022aa6  jnz     loc_180022BA3
0x180022aac  mov     [rsp+68h+Source], 1A5FFF2h
0x180022ab5  mov     [rsp+68h+var_40], rbx
0x180022aba  mov     ebp, 10h
0x180022abf  mov     edx, ebp; unsigned __int64
0x180022ac1  lea     rcx, [rdi+20h]; this
0x180022ac5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180022aca  test    al, al
0x180022acc  jz      short loc_180022AF5
0x180022ace  mov     rcx, [rdi+28h]; Destination
0x180022ad2  mov     rax, [rdi+30h]
0x180022ad6  sub     rax, rcx
0x180022ad9  cmp     rcx, [rdi+30h]
0x180022add  sbb     rdx, rdx
0x180022ae0  and     rdx, rax; DestinationSize
0x180022ae3  mov     r9d, ebp; SourceSize
0x180022ae6  lea     r8, [rsp+68h+Source]; Source
0x180022aeb  call    cs:__imp_memcpy_s
0x180022af1  add     [rdi+28h], rbp
0x180022af5  cmp     byte ptr [rdi+18h], 0
0x180022af9  jnz     loc_180022BA3
0x180022aff  cmp     qword ptr [rdi+10h], 0
0x180022b04  jnz     short loc_180022B73
0x180022b06  call    cs:__imp_GetLastError
0x180022b0c  mov     r14d, eax
0x180022b0f  xor     r8d, r8d; pcbe
0x180022b12  mov     rdx, rdi; pv
0x180022b15  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180022b1c  call    cs:__imp_CreateThreadpoolTimer
0x180022b22  mov     r15, rax
0x180022b25  mov     rbp, [rdi+10h]
0x180022b29  test    rbp, rbp
0x180022b2c  jz      short loc_180022B66
0x180022b2e  call    cs:__imp_GetLastError
0x180022b34  mov     ebx, eax
0x180022b36  xor     r9d, r9d; msWindowLength
0x180022b39  xor     r8d, r8d; msPeriod
0x180022b3c  xor     edx, edx; pftDueTime
0x180022b3e  mov     rcx, rbp; pti
0x180022b41  call    cs:__imp_SetThreadpoolTimer
0x180022b47  mov     edx, 1; fCancelPendingCallbacks
0x180022b4c  mov     rcx, rbp; pti
0x180022b4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180022b55  mov     rcx, rbp; pti
0x180022b58  call    cs:__imp_CloseThreadpoolTimer
0x180022b5e  mov     ecx, ebx; dwErrCode
0x180022b60  call    cs:__imp_SetLastError
0x180022b66  mov     [rdi+10h], r15
0x180022b6a  mov     ecx, r14d; dwErrCode
0x180022b6d  call    cs:__imp_SetLastError
0x180022b73  mov     rcx, [rdi+10h]; pti
0x180022b77  test    rcx, rcx
0x180022b7a  jz      short loc_180022BA3
0x180022b7c  mov     rax, 0FFFFFFFF4D2FA200h
0x180022b86  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180022b8b  mov     r9d, 124F8h; msWindowLength
0x180022b91  xor     r8d, r8d; msPeriod
0x180022b94  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180022b99  call    cs:__imp_SetThreadpoolTimer
0x180022b9f  mov     byte ptr [rdi+18h], 1
0x180022ba3  test    rsi, rsi
0x180022ba6  jz      short loc_180022BB2
0x180022ba8  mov     rcx, rsi; SRWLock
0x180022bab  call    cs:__imp_ReleaseSRWLockExclusive
0x180022bb1  nop
0x180022bb2  add     rsp, 38h
0x180022bb6  pop     r15
0x180022bb8  pop     r14
0x180022bba  pop     rdi
0x180022bbb  pop     rsi
0x180022bbc  pop     rbp
0x180022bbd  pop     rbx
0x180022bbe  retn
```
