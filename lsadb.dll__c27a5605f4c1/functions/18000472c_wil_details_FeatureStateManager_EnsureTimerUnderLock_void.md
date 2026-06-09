# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000472c`
- end: `0x180004800`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006c14`

## callees

- `0x18000472c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004779`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004767`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004767`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800047a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800047a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000478c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800047e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000478c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800047e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000479a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000479a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[6];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[6] = v5;
      SetLastError(LastError);
    }
    v7 = pv[6];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x18000472c  mov     [rsp+arg_8], rbx
0x180004731  mov     [rsp+arg_10], rbp
0x180004736  push    rsi
0x180004737  push    rdi
0x180004738  push    r14
0x18000473a  sub     rsp, 20h
0x18000473e  cmp     byte ptr [rcx+41h], 0
0x180004742  mov     rdi, rcx
0x180004745  jnz     loc_1800047ED
0x18000474b  cmp     qword ptr [rcx+30h], 0
0x180004750  jnz     short loc_1800047BD
0x180004752  call    cs:__imp_GetLastError
0x180004758  xor     r8d, r8d; pcbe
0x18000475b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004762  mov     rdx, rdi; pv
0x180004765  mov     ebp, eax
0x180004767  call    cs:__imp_CreateThreadpoolTimer
0x18000476d  mov     rsi, [rdi+30h]
0x180004771  mov     r14, rax
0x180004774  test    rsi, rsi
0x180004777  jz      short loc_1800047B1
0x180004779  call    cs:__imp_GetLastError
0x18000477f  xor     r9d, r9d; msWindowLength
0x180004782  xor     r8d, r8d; msPeriod
0x180004785  xor     edx, edx; pftDueTime
0x180004787  mov     rcx, rsi; pti
0x18000478a  mov     ebx, eax
0x18000478c  call    cs:__imp_SetThreadpoolTimer
0x180004792  mov     edx, 1; fCancelPendingCallbacks
0x180004797  mov     rcx, rsi; pti
0x18000479a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800047a0  mov     rcx, rsi; pti
0x1800047a3  call    cs:__imp_CloseThreadpoolTimer
0x1800047a9  mov     ecx, ebx; dwErrCode
0x1800047ab  call    cs:__imp_SetLastError
0x1800047b1  mov     ecx, ebp; dwErrCode
0x1800047b3  mov     [rdi+30h], r14
0x1800047b7  call    cs:__imp_SetLastError
0x1800047bd  mov     rcx, [rdi+30h]; pti
0x1800047c1  test    rcx, rcx
0x1800047c4  jz      short loc_1800047ED
0x1800047c6  mov     rax, 0FFFFFFFF4D2FA200h
0x1800047d0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800047d5  mov     r9d, 124F8h; msWindowLength
0x1800047db  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800047e0  xor     r8d, r8d; msPeriod
0x1800047e3  call    cs:__imp_SetThreadpoolTimer
0x1800047e9  mov     byte ptr [rdi+41h], 1
0x1800047ed  mov     rbx, [rsp+38h+arg_8]
0x1800047f2  mov     rbp, [rsp+38h+arg_10]
0x1800047f7  add     rsp, 20h
0x1800047fb  pop     r14
0x1800047fd  pop     rdi
0x1800047fe  pop     rsi
0x1800047ff  retn
```
