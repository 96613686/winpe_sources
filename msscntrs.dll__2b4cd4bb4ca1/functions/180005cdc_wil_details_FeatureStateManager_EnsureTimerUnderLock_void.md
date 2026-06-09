# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005cdc`
- end: `0x180005db0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007af4`

## callees

- `0x180005cdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005d53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005d53`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005d4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005d4a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005d17`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005d17`

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
0x180005cdc  mov     [rsp+arg_8], rbx
0x180005ce1  mov     [rsp+arg_10], rbp
0x180005ce6  push    rsi
0x180005ce7  push    rdi
0x180005ce8  push    r14
0x180005cea  sub     rsp, 20h
0x180005cee  cmp     byte ptr [rcx+41h], 0
0x180005cf2  mov     rdi, rcx
0x180005cf5  jnz     loc_180005D9D
0x180005cfb  cmp     qword ptr [rcx+30h], 0
0x180005d00  jnz     short loc_180005D6D
0x180005d02  call    cs:__imp_GetLastError
0x180005d08  xor     r8d, r8d; pcbe
0x180005d0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005d12  mov     rdx, rdi; pv
0x180005d15  mov     ebp, eax
0x180005d17  call    cs:__imp_CreateThreadpoolTimer
0x180005d1d  mov     rsi, [rdi+30h]
0x180005d21  mov     r14, rax
0x180005d24  test    rsi, rsi
0x180005d27  jz      short loc_180005D61
0x180005d29  call    cs:__imp_GetLastError
0x180005d2f  xor     r9d, r9d; msWindowLength
0x180005d32  xor     r8d, r8d; msPeriod
0x180005d35  xor     edx, edx; pftDueTime
0x180005d37  mov     rcx, rsi; pti
0x180005d3a  mov     ebx, eax
0x180005d3c  call    cs:__imp_SetThreadpoolTimer
0x180005d42  mov     edx, 1; fCancelPendingCallbacks
0x180005d47  mov     rcx, rsi; pti
0x180005d4a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005d50  mov     rcx, rsi; pti
0x180005d53  call    cs:__imp_CloseThreadpoolTimer
0x180005d59  mov     ecx, ebx; dwErrCode
0x180005d5b  call    cs:__imp_SetLastError
0x180005d61  mov     ecx, ebp; dwErrCode
0x180005d63  mov     [rdi+30h], r14
0x180005d67  call    cs:__imp_SetLastError
0x180005d6d  mov     rcx, [rdi+30h]; pti
0x180005d71  test    rcx, rcx
0x180005d74  jz      short loc_180005D9D
0x180005d76  mov     rax, 0FFFFFFFF4D2FA200h
0x180005d80  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005d85  mov     r9d, 124F8h; msWindowLength
0x180005d8b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005d90  xor     r8d, r8d; msPeriod
0x180005d93  call    cs:__imp_SetThreadpoolTimer
0x180005d99  mov     byte ptr [rdi+41h], 1
0x180005d9d  mov     rbx, [rsp+38h+arg_8]
0x180005da2  mov     rbp, [rsp+38h+arg_10]
0x180005da7  add     rsp, 20h
0x180005dab  pop     r14
0x180005dad  pop     rdi
0x180005dae  pop     rsi
0x180005daf  retn
```
