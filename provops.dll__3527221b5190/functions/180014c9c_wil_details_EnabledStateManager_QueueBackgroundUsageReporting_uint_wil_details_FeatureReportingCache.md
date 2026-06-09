# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180014c9c`
- end: `0x180014e30`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `404`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017700`

## callees

- `0x180014c9c`
- `0x180021370`
- `0x180037010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180014d5c`
- `msvcrt!memcpy_s` at `0x180014d5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ce8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ce8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014e1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014dd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014dde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014dd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014dde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014d8d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014d8d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014db2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014e0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014db2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014e0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014dc9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014dc9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014dc0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014dc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v9; // ebx
  struct _TP_TIMER *v10; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v12; // [rsp+28h] [rbp-40h]
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
      Source[0] = a2;
      Source[1] = 0;
      v12 = a3;
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
            v9 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v9);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v10 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v10 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v10, &pftDueTime, 0, 0x124F8u);
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
0x180014c9c  push    rbx
0x180014c9e  push    rbp
0x180014c9f  push    rsi
0x180014ca0  push    rdi
0x180014ca1  push    r14
0x180014ca3  push    r15
0x180014ca5  sub     rsp, 38h
0x180014ca9  mov     rbx, r8
0x180014cac  mov     ebp, edx
0x180014cae  mov     rdi, rcx
0x180014cb1  mov     eax, [rcx]
0x180014cb3  test    eax, eax
0x180014cb5  jz      loc_180014E23
0x180014cbb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014cc2  jnz     loc_180014E23
0x180014cc8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014ccf  test    rax, rax
0x180014cd2  jz      short loc_180014CE1
0x180014cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cd9  test    al, al
0x180014cdb  jnz     loc_180014E23
0x180014ce1  lea     rsi, [rdi+8]
0x180014ce5  mov     rcx, rsi; SRWLock
0x180014ce8  call    cs:__imp_AcquireSRWLockExclusive
0x180014cee  mov     eax, [rdi]
0x180014cf0  test    eax, eax
0x180014cf2  jz      loc_180014E14
0x180014cf8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014cff  jnz     loc_180014E14
0x180014d05  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014d0c  test    rax, rax
0x180014d0f  jz      short loc_180014D1E
0x180014d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d16  test    al, al
0x180014d18  jnz     loc_180014E14
0x180014d1e  mov     [rsp+68h+Source], ebp
0x180014d22  xor     eax, eax
0x180014d24  mov     [rsp+68h+var_44], eax
0x180014d28  mov     [rsp+68h+var_40], rbx
0x180014d2d  lea     ebp, [rax+10h]
0x180014d30  mov     edx, ebp; unsigned __int64
0x180014d32  lea     rcx, [rdi+20h]; this
0x180014d36  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180014d3b  test    al, al
0x180014d3d  jz      short loc_180014D66
0x180014d3f  mov     rcx, [rdi+28h]; Destination
0x180014d43  mov     rax, [rdi+30h]
0x180014d47  sub     rax, rcx
0x180014d4a  cmp     rcx, [rdi+30h]
0x180014d4e  sbb     rdx, rdx
0x180014d51  and     rdx, rax; DestinationSize
0x180014d54  mov     r9d, ebp; SourceSize
0x180014d57  lea     r8, [rsp+68h+Source]; Source
0x180014d5c  call    cs:__imp_memcpy_s
0x180014d62  add     [rdi+28h], rbp
0x180014d66  cmp     byte ptr [rdi+18h], 0
0x180014d6a  jnz     loc_180014E14
0x180014d70  cmp     qword ptr [rdi+10h], 0
0x180014d75  jnz     short loc_180014DE4
0x180014d77  call    cs:__imp_GetLastError
0x180014d7d  mov     r14d, eax
0x180014d80  xor     r8d, r8d; pcbe
0x180014d83  mov     rdx, rdi; pv
0x180014d86  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180014d8d  call    cs:__imp_CreateThreadpoolTimer
0x180014d93  mov     r15, rax
0x180014d96  mov     rbp, [rdi+10h]
0x180014d9a  test    rbp, rbp
0x180014d9d  jz      short loc_180014DD7
0x180014d9f  call    cs:__imp_GetLastError
0x180014da5  mov     ebx, eax
0x180014da7  xor     r9d, r9d; msWindowLength
0x180014daa  xor     r8d, r8d; msPeriod
0x180014dad  xor     edx, edx; pftDueTime
0x180014daf  mov     rcx, rbp; pti
0x180014db2  call    cs:__imp_SetThreadpoolTimer
0x180014db8  mov     edx, 1; fCancelPendingCallbacks
0x180014dbd  mov     rcx, rbp; pti
0x180014dc0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014dc6  mov     rcx, rbp; pti
0x180014dc9  call    cs:__imp_CloseThreadpoolTimer
0x180014dcf  mov     ecx, ebx; dwErrCode
0x180014dd1  call    cs:__imp_SetLastError
0x180014dd7  mov     [rdi+10h], r15
0x180014ddb  mov     ecx, r14d; dwErrCode
0x180014dde  call    cs:__imp_SetLastError
0x180014de4  mov     rcx, [rdi+10h]; pti
0x180014de8  test    rcx, rcx
0x180014deb  jz      short loc_180014E14
0x180014ded  mov     rax, 0FFFFFFFF4D2FA200h
0x180014df7  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180014dfc  mov     r9d, 124F8h; msWindowLength
0x180014e02  xor     r8d, r8d; msPeriod
0x180014e05  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180014e0a  call    cs:__imp_SetThreadpoolTimer
0x180014e10  mov     byte ptr [rdi+18h], 1
0x180014e14  test    rsi, rsi
0x180014e17  jz      short loc_180014E23
0x180014e19  mov     rcx, rsi; SRWLock
0x180014e1c  call    cs:__imp_ReleaseSRWLockExclusive
0x180014e22  nop
0x180014e23  add     rsp, 38h
0x180014e27  pop     r15
0x180014e29  pop     r14
0x180014e2b  pop     rdi
0x180014e2c  pop     rsi
0x180014e2d  pop     rbp
0x180014e2e  pop     rbx
0x180014e2f  retn
```
