# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180004298`
- end: `0x18000436c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c44`

## callees

- `0x180004298`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004317`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004323`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004317`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004323`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004306`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004306`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800042f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000434f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800042f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000434f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800042d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800042d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000430f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000430f`

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
0x180004298  mov     [rsp+arg_8], rbx
0x18000429d  mov     [rsp+arg_10], rbp
0x1800042a2  push    rsi
0x1800042a3  push    rdi
0x1800042a4  push    r14
0x1800042a6  sub     rsp, 20h
0x1800042aa  cmp     byte ptr [rcx+41h], 0
0x1800042ae  mov     rdi, rcx
0x1800042b1  jnz     loc_180004359
0x1800042b7  cmp     qword ptr [rcx+30h], 0
0x1800042bc  jnz     short loc_180004329
0x1800042be  call    cs:__imp_GetLastError
0x1800042c4  xor     r8d, r8d; pcbe
0x1800042c7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800042ce  mov     rdx, rdi; pv
0x1800042d1  mov     ebp, eax
0x1800042d3  call    cs:__imp_CreateThreadpoolTimer
0x1800042d9  mov     rsi, [rdi+30h]
0x1800042dd  mov     r14, rax
0x1800042e0  test    rsi, rsi
0x1800042e3  jz      short loc_18000431D
0x1800042e5  call    cs:__imp_GetLastError
0x1800042eb  xor     r9d, r9d; msWindowLength
0x1800042ee  xor     r8d, r8d; msPeriod
0x1800042f1  xor     edx, edx; pftDueTime
0x1800042f3  mov     rcx, rsi; pti
0x1800042f6  mov     ebx, eax
0x1800042f8  call    cs:__imp_SetThreadpoolTimer
0x1800042fe  mov     edx, 1; fCancelPendingCallbacks
0x180004303  mov     rcx, rsi; pti
0x180004306  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000430c  mov     rcx, rsi; pti
0x18000430f  call    cs:__imp_CloseThreadpoolTimer
0x180004315  mov     ecx, ebx; dwErrCode
0x180004317  call    cs:__imp_SetLastError
0x18000431d  mov     ecx, ebp; dwErrCode
0x18000431f  mov     [rdi+30h], r14
0x180004323  call    cs:__imp_SetLastError
0x180004329  mov     rcx, [rdi+30h]; pti
0x18000432d  test    rcx, rcx
0x180004330  jz      short loc_180004359
0x180004332  mov     rax, 0FFFFFFFF4D2FA200h
0x18000433c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004341  mov     r9d, 124F8h; msWindowLength
0x180004347  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000434c  xor     r8d, r8d; msPeriod
0x18000434f  call    cs:__imp_SetThreadpoolTimer
0x180004355  mov     byte ptr [rdi+41h], 1
0x180004359  mov     rbx, [rsp+38h+arg_8]
0x18000435e  mov     rbp, [rsp+38h+arg_10]
0x180004363  add     rsp, 20h
0x180004367  pop     r14
0x180004369  pop     rdi
0x18000436a  pop     rsi
0x18000436b  retn
```
