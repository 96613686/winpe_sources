# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000e3e4`
- end: `0x18000e4b8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800109c4`

## callees

- `0x18000e3e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e463`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e46f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e463`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e431`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e444`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e49b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e444`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e49b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e45b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e45b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e41f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e41f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e452`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e452`

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
0x18000e3e4  mov     [rsp+arg_8], rbx
0x18000e3e9  mov     [rsp+arg_10], rbp
0x18000e3ee  push    rsi
0x18000e3ef  push    rdi
0x18000e3f0  push    r14
0x18000e3f2  sub     rsp, 20h
0x18000e3f6  cmp     byte ptr [rcx+41h], 0
0x18000e3fa  mov     rdi, rcx
0x18000e3fd  jnz     loc_18000E4A5
0x18000e403  cmp     qword ptr [rcx+30h], 0
0x18000e408  jnz     short loc_18000E475
0x18000e40a  call    cs:__imp_GetLastError
0x18000e410  xor     r8d, r8d; pcbe
0x18000e413  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000e41a  mov     rdx, rdi; pv
0x18000e41d  mov     ebp, eax
0x18000e41f  call    cs:__imp_CreateThreadpoolTimer
0x18000e425  mov     rsi, [rdi+30h]
0x18000e429  mov     r14, rax
0x18000e42c  test    rsi, rsi
0x18000e42f  jz      short loc_18000E469
0x18000e431  call    cs:__imp_GetLastError
0x18000e437  xor     r9d, r9d; msWindowLength
0x18000e43a  xor     r8d, r8d; msPeriod
0x18000e43d  xor     edx, edx; pftDueTime
0x18000e43f  mov     rcx, rsi; pti
0x18000e442  mov     ebx, eax
0x18000e444  call    cs:__imp_SetThreadpoolTimer
0x18000e44a  mov     edx, 1; fCancelPendingCallbacks
0x18000e44f  mov     rcx, rsi; pti
0x18000e452  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e458  mov     rcx, rsi; pti
0x18000e45b  call    cs:__imp_CloseThreadpoolTimer
0x18000e461  mov     ecx, ebx; dwErrCode
0x18000e463  call    cs:__imp_SetLastError
0x18000e469  mov     ecx, ebp; dwErrCode
0x18000e46b  mov     [rdi+30h], r14
0x18000e46f  call    cs:__imp_SetLastError
0x18000e475  mov     rcx, [rdi+30h]; pti
0x18000e479  test    rcx, rcx
0x18000e47c  jz      short loc_18000E4A5
0x18000e47e  mov     rax, 0FFFFFFFF4D2FA200h
0x18000e488  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000e48d  mov     r9d, 124F8h; msWindowLength
0x18000e493  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000e498  xor     r8d, r8d; msPeriod
0x18000e49b  call    cs:__imp_SetThreadpoolTimer
0x18000e4a1  mov     byte ptr [rdi+41h], 1
0x18000e4a5  mov     rbx, [rsp+38h+arg_8]
0x18000e4aa  mov     rbp, [rsp+38h+arg_10]
0x18000e4af  add     rsp, 20h
0x18000e4b3  pop     r14
0x18000e4b5  pop     rdi
0x18000e4b6  pop     rsi
0x18000e4b7  retn
```
