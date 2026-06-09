# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14000521c`
- end: `0x1400052f0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007734`

## callees

- `0x14000521c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000529b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400052a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000529b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400052a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005269`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000528a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000528a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140005257`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140005257`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005293`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005293`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000527c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400052d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000527c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400052d3`

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
0x14000521c  mov     [rsp+arg_8], rbx
0x140005221  mov     [rsp+arg_10], rbp
0x140005226  push    rsi
0x140005227  push    rdi
0x140005228  push    r14
0x14000522a  sub     rsp, 20h
0x14000522e  cmp     byte ptr [rcx+41h], 0
0x140005232  mov     rdi, rcx
0x140005235  jnz     loc_1400052DD
0x14000523b  cmp     qword ptr [rcx+30h], 0
0x140005240  jnz     short loc_1400052AD
0x140005242  call    cs:__imp_GetLastError
0x140005248  xor     r8d, r8d; pcbe
0x14000524b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140005252  mov     rdx, rdi; pv
0x140005255  mov     ebp, eax
0x140005257  call    cs:__imp_CreateThreadpoolTimer
0x14000525d  mov     rsi, [rdi+30h]
0x140005261  mov     r14, rax
0x140005264  test    rsi, rsi
0x140005267  jz      short loc_1400052A1
0x140005269  call    cs:__imp_GetLastError
0x14000526f  xor     r9d, r9d; msWindowLength
0x140005272  xor     r8d, r8d; msPeriod
0x140005275  xor     edx, edx; pftDueTime
0x140005277  mov     rcx, rsi; pti
0x14000527a  mov     ebx, eax
0x14000527c  call    cs:__imp_SetThreadpoolTimer
0x140005282  mov     edx, 1; fCancelPendingCallbacks
0x140005287  mov     rcx, rsi; pti
0x14000528a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005290  mov     rcx, rsi; pti
0x140005293  call    cs:__imp_CloseThreadpoolTimer
0x140005299  mov     ecx, ebx; dwErrCode
0x14000529b  call    cs:__imp_SetLastError
0x1400052a1  mov     ecx, ebp; dwErrCode
0x1400052a3  mov     [rdi+30h], r14
0x1400052a7  call    cs:__imp_SetLastError
0x1400052ad  mov     rcx, [rdi+30h]; pti
0x1400052b1  test    rcx, rcx
0x1400052b4  jz      short loc_1400052DD
0x1400052b6  mov     rax, 0FFFFFFFF4D2FA200h
0x1400052c0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1400052c5  mov     r9d, 124F8h; msWindowLength
0x1400052cb  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1400052d0  xor     r8d, r8d; msPeriod
0x1400052d3  call    cs:__imp_SetThreadpoolTimer
0x1400052d9  mov     byte ptr [rdi+41h], 1
0x1400052dd  mov     rbx, [rsp+38h+arg_8]
0x1400052e2  mov     rbp, [rsp+38h+arg_10]
0x1400052e7  add     rsp, 20h
0x1400052eb  pop     r14
0x1400052ed  pop     rdi
0x1400052ee  pop     rsi
0x1400052ef  retn
```
