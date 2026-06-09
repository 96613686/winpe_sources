# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1400069e4`
- end: `0x140006ab8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008884`

## callees

- `0x1400069e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006a63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006a6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006a63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006a6f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006a1f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006a1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006a5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006a5b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006a44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006a9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006a44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006a9b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006a52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006a52`

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
0x1400069e4  mov     [rsp+arg_8], rbx
0x1400069e9  mov     [rsp+arg_10], rbp
0x1400069ee  push    rsi
0x1400069ef  push    rdi
0x1400069f0  push    r14
0x1400069f2  sub     rsp, 20h
0x1400069f6  cmp     byte ptr [rcx+41h], 0
0x1400069fa  mov     rdi, rcx
0x1400069fd  jnz     loc_140006AA5
0x140006a03  cmp     qword ptr [rcx+30h], 0
0x140006a08  jnz     short loc_140006A75
0x140006a0a  call    cs:__imp_GetLastError
0x140006a10  xor     r8d, r8d; pcbe
0x140006a13  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140006a1a  mov     rdx, rdi; pv
0x140006a1d  mov     ebp, eax
0x140006a1f  call    cs:__imp_CreateThreadpoolTimer
0x140006a25  mov     rsi, [rdi+30h]
0x140006a29  mov     r14, rax
0x140006a2c  test    rsi, rsi
0x140006a2f  jz      short loc_140006A69
0x140006a31  call    cs:__imp_GetLastError
0x140006a37  xor     r9d, r9d; msWindowLength
0x140006a3a  xor     r8d, r8d; msPeriod
0x140006a3d  xor     edx, edx; pftDueTime
0x140006a3f  mov     rcx, rsi; pti
0x140006a42  mov     ebx, eax
0x140006a44  call    cs:__imp_SetThreadpoolTimer
0x140006a4a  mov     edx, 1; fCancelPendingCallbacks
0x140006a4f  mov     rcx, rsi; pti
0x140006a52  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006a58  mov     rcx, rsi; pti
0x140006a5b  call    cs:__imp_CloseThreadpoolTimer
0x140006a61  mov     ecx, ebx; dwErrCode
0x140006a63  call    cs:__imp_SetLastError
0x140006a69  mov     ecx, ebp; dwErrCode
0x140006a6b  mov     [rdi+30h], r14
0x140006a6f  call    cs:__imp_SetLastError
0x140006a75  mov     rcx, [rdi+30h]; pti
0x140006a79  test    rcx, rcx
0x140006a7c  jz      short loc_140006AA5
0x140006a7e  mov     rax, 0FFFFFFFF4D2FA200h
0x140006a88  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140006a8d  mov     r9d, 124F8h; msWindowLength
0x140006a93  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140006a98  xor     r8d, r8d; msPeriod
0x140006a9b  call    cs:__imp_SetThreadpoolTimer
0x140006aa1  mov     byte ptr [rdi+41h], 1
0x140006aa5  mov     rbx, [rsp+38h+arg_8]
0x140006aaa  mov     rbp, [rsp+38h+arg_10]
0x140006aaf  add     rsp, 20h
0x140006ab3  pop     r14
0x140006ab5  pop     rdi
0x140006ab6  pop     rsi
0x140006ab7  retn
```
