# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180009208`
- end: `0x1800092dc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac64`

## callees

- `0x180009208`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009293`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000922e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000922e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009255`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000927f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000927f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009268`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800092bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009268`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800092bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009243`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009243`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009276`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009276`

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
0x180009208  mov     [rsp+arg_8], rbx
0x18000920d  mov     [rsp+arg_10], rbp
0x180009212  push    rsi
0x180009213  push    rdi
0x180009214  push    r14
0x180009216  sub     rsp, 20h
0x18000921a  cmp     byte ptr [rcx+41h], 0
0x18000921e  mov     rdi, rcx
0x180009221  jnz     loc_1800092C9
0x180009227  cmp     qword ptr [rcx+30h], 0
0x18000922c  jnz     short loc_180009299
0x18000922e  call    cs:__imp_GetLastError
0x180009234  xor     r8d, r8d; pcbe
0x180009237  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000923e  mov     rdx, rdi; pv
0x180009241  mov     ebp, eax
0x180009243  call    cs:__imp_CreateThreadpoolTimer
0x180009249  mov     rsi, [rdi+30h]
0x18000924d  mov     r14, rax
0x180009250  test    rsi, rsi
0x180009253  jz      short loc_18000928D
0x180009255  call    cs:__imp_GetLastError
0x18000925b  xor     r9d, r9d; msWindowLength
0x18000925e  xor     r8d, r8d; msPeriod
0x180009261  xor     edx, edx; pftDueTime
0x180009263  mov     rcx, rsi; pti
0x180009266  mov     ebx, eax
0x180009268  call    cs:__imp_SetThreadpoolTimer
0x18000926e  mov     edx, 1; fCancelPendingCallbacks
0x180009273  mov     rcx, rsi; pti
0x180009276  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000927c  mov     rcx, rsi; pti
0x18000927f  call    cs:__imp_CloseThreadpoolTimer
0x180009285  mov     ecx, ebx; dwErrCode
0x180009287  call    cs:__imp_SetLastError
0x18000928d  mov     ecx, ebp; dwErrCode
0x18000928f  mov     [rdi+30h], r14
0x180009293  call    cs:__imp_SetLastError
0x180009299  mov     rcx, [rdi+30h]; pti
0x18000929d  test    rcx, rcx
0x1800092a0  jz      short loc_1800092C9
0x1800092a2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800092ac  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800092b1  mov     r9d, 124F8h; msWindowLength
0x1800092b7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800092bc  xor     r8d, r8d; msPeriod
0x1800092bf  call    cs:__imp_SetThreadpoolTimer
0x1800092c5  mov     byte ptr [rdi+41h], 1
0x1800092c9  mov     rbx, [rsp+38h+arg_8]
0x1800092ce  mov     rbp, [rsp+38h+arg_10]
0x1800092d3  add     rsp, 20h
0x1800092d7  pop     r14
0x1800092d9  pop     rdi
0x1800092da  pop     rsi
0x1800092db  retn
```
