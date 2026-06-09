# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180003de8`
- end: `0x180003ebc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058e4`

## callees

- `0x180003de8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003e23`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003e23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e5f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003e56`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003e56`

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
0x180003de8  mov     [rsp+arg_8], rbx
0x180003ded  mov     [rsp+arg_10], rbp
0x180003df2  push    rsi
0x180003df3  push    rdi
0x180003df4  push    r14
0x180003df6  sub     rsp, 20h
0x180003dfa  cmp     byte ptr [rcx+41h], 0
0x180003dfe  mov     rdi, rcx
0x180003e01  jnz     loc_180003EA9
0x180003e07  cmp     qword ptr [rcx+30h], 0
0x180003e0c  jnz     short loc_180003E79
0x180003e0e  call    cs:__imp_GetLastError
0x180003e14  xor     r8d, r8d; pcbe
0x180003e17  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180003e1e  mov     rdx, rdi; pv
0x180003e21  mov     ebp, eax
0x180003e23  call    cs:__imp_CreateThreadpoolTimer
0x180003e29  mov     rsi, [rdi+30h]
0x180003e2d  mov     r14, rax
0x180003e30  test    rsi, rsi
0x180003e33  jz      short loc_180003E6D
0x180003e35  call    cs:__imp_GetLastError
0x180003e3b  xor     r9d, r9d; msWindowLength
0x180003e3e  xor     r8d, r8d; msPeriod
0x180003e41  xor     edx, edx; pftDueTime
0x180003e43  mov     rcx, rsi; pti
0x180003e46  mov     ebx, eax
0x180003e48  call    cs:__imp_SetThreadpoolTimer
0x180003e4e  mov     edx, 1; fCancelPendingCallbacks
0x180003e53  mov     rcx, rsi; pti
0x180003e56  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003e5c  mov     rcx, rsi; pti
0x180003e5f  call    cs:__imp_CloseThreadpoolTimer
0x180003e65  mov     ecx, ebx; dwErrCode
0x180003e67  call    cs:__imp_SetLastError
0x180003e6d  mov     ecx, ebp; dwErrCode
0x180003e6f  mov     [rdi+30h], r14
0x180003e73  call    cs:__imp_SetLastError
0x180003e79  mov     rcx, [rdi+30h]; pti
0x180003e7d  test    rcx, rcx
0x180003e80  jz      short loc_180003EA9
0x180003e82  mov     rax, 0FFFFFFFF4D2FA200h
0x180003e8c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180003e91  mov     r9d, 124F8h; msWindowLength
0x180003e97  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180003e9c  xor     r8d, r8d; msPeriod
0x180003e9f  call    cs:__imp_SetThreadpoolTimer
0x180003ea5  mov     byte ptr [rdi+41h], 1
0x180003ea9  mov     rbx, [rsp+38h+arg_8]
0x180003eae  mov     rbp, [rsp+38h+arg_10]
0x180003eb3  add     rsp, 20h
0x180003eb7  pop     r14
0x180003eb9  pop     rdi
0x180003eba  pop     rsi
0x180003ebb  retn
```
