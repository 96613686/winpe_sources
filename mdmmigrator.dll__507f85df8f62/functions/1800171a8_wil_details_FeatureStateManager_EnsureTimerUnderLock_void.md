# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800171a8`
- end: `0x18001727c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017f40`

## callees

- `0x1800171a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017233`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017233`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017216`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017216`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001721f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001721f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800171e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800171e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017208`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001725f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017208`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001725f`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // r14
  struct _TP_TIMER *v4; // rsi
  DWORD v5; // ebx
  struct _TP_TIMER *v6; // rcx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[6];
      if ( v4 )
      {
        v5 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v5);
      }
      pv[6] = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v6 = pv[6];
    if ( v6 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v6, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x1800171a8  mov     [rsp+arg_8], rbx
0x1800171ad  mov     [rsp+arg_10], rbp
0x1800171b2  push    rsi
0x1800171b3  push    rdi
0x1800171b4  push    r14
0x1800171b6  sub     rsp, 20h
0x1800171ba  mov     rdi, rcx
0x1800171bd  cmp     byte ptr [rcx+41h], 0
0x1800171c1  jnz     loc_180017269
0x1800171c7  cmp     qword ptr [rcx+30h], 0
0x1800171cc  jnz     short loc_180017239
0x1800171ce  call    cs:__imp_GetLastError
0x1800171d4  mov     ebp, eax
0x1800171d6  xor     r8d, r8d; pcbe
0x1800171d9  mov     rdx, rdi; pv
0x1800171dc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800171e3  call    cs:__imp_CreateThreadpoolTimer
0x1800171e9  mov     r14, rax
0x1800171ec  mov     rsi, [rdi+30h]
0x1800171f0  test    rsi, rsi
0x1800171f3  jz      short loc_18001722D
0x1800171f5  call    cs:__imp_GetLastError
0x1800171fb  mov     ebx, eax
0x1800171fd  xor     r9d, r9d; msWindowLength
0x180017200  xor     r8d, r8d; msPeriod
0x180017203  xor     edx, edx; pftDueTime
0x180017205  mov     rcx, rsi; pti
0x180017208  call    cs:__imp_SetThreadpoolTimer
0x18001720e  mov     edx, 1; fCancelPendingCallbacks
0x180017213  mov     rcx, rsi; pti
0x180017216  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001721c  mov     rcx, rsi; pti
0x18001721f  call    cs:__imp_CloseThreadpoolTimer
0x180017225  mov     ecx, ebx; dwErrCode
0x180017227  call    cs:__imp_SetLastError
0x18001722d  mov     [rdi+30h], r14
0x180017231  mov     ecx, ebp; dwErrCode
0x180017233  call    cs:__imp_SetLastError
0x180017239  mov     rcx, [rdi+30h]; pti
0x18001723d  test    rcx, rcx
0x180017240  jz      short loc_180017269
0x180017242  mov     rax, 0FFFFFFFF4D2FA200h
0x18001724c  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180017251  mov     r9d, 124F8h; msWindowLength
0x180017257  xor     r8d, r8d; msPeriod
0x18001725a  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18001725f  call    cs:__imp_SetThreadpoolTimer
0x180017265  mov     byte ptr [rdi+41h], 1
0x180017269  mov     rbx, [rsp+38h+arg_8]
0x18001726e  mov     rbp, [rsp+38h+arg_10]
0x180017273  add     rsp, 20h
0x180017277  pop     r14
0x180017279  pop     rdi
0x18001727a  pop     rsi
0x18001727b  retn
```
