# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800b0a54`
- end: `0x1800b0b28`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b5b24`

## callees

- `0x1800b0a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0ad3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0adf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0ad3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0aa1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b0ac2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b0ac2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b0acb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b0acb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b0a8f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b0a8f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b0ab4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b0b0b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b0ab4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b0b0b`

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
0x1800b0a54  mov     [rsp+arg_8], rbx
0x1800b0a59  mov     [rsp+arg_10], rbp
0x1800b0a5e  push    rsi
0x1800b0a5f  push    rdi
0x1800b0a60  push    r14
0x1800b0a62  sub     rsp, 20h
0x1800b0a66  cmp     byte ptr [rcx+41h], 0
0x1800b0a6a  mov     rdi, rcx
0x1800b0a6d  jnz     loc_1800B0B15
0x1800b0a73  cmp     qword ptr [rcx+30h], 0
0x1800b0a78  jnz     short loc_1800B0AE5
0x1800b0a7a  call    cs:__imp_GetLastError
0x1800b0a80  xor     r8d, r8d; pcbe
0x1800b0a83  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800b0a8a  mov     rdx, rdi; pv
0x1800b0a8d  mov     ebp, eax
0x1800b0a8f  call    cs:__imp_CreateThreadpoolTimer
0x1800b0a95  mov     rsi, [rdi+30h]
0x1800b0a99  mov     r14, rax
0x1800b0a9c  test    rsi, rsi
0x1800b0a9f  jz      short loc_1800B0AD9
0x1800b0aa1  call    cs:__imp_GetLastError
0x1800b0aa7  xor     r9d, r9d; msWindowLength
0x1800b0aaa  xor     r8d, r8d; msPeriod
0x1800b0aad  xor     edx, edx; pftDueTime
0x1800b0aaf  mov     rcx, rsi; pti
0x1800b0ab2  mov     ebx, eax
0x1800b0ab4  call    cs:__imp_SetThreadpoolTimer
0x1800b0aba  mov     edx, 1; fCancelPendingCallbacks
0x1800b0abf  mov     rcx, rsi; pti
0x1800b0ac2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b0ac8  mov     rcx, rsi; pti
0x1800b0acb  call    cs:__imp_CloseThreadpoolTimer
0x1800b0ad1  mov     ecx, ebx; dwErrCode
0x1800b0ad3  call    cs:__imp_SetLastError
0x1800b0ad9  mov     ecx, ebp; dwErrCode
0x1800b0adb  mov     [rdi+30h], r14
0x1800b0adf  call    cs:__imp_SetLastError
0x1800b0ae5  mov     rcx, [rdi+30h]; pti
0x1800b0ae9  test    rcx, rcx
0x1800b0aec  jz      short loc_1800B0B15
0x1800b0aee  mov     rax, 0FFFFFFFF4D2FA200h
0x1800b0af8  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800b0afd  mov     r9d, 124F8h; msWindowLength
0x1800b0b03  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800b0b08  xor     r8d, r8d; msPeriod
0x1800b0b0b  call    cs:__imp_SetThreadpoolTimer
0x1800b0b11  mov     byte ptr [rdi+41h], 1
0x1800b0b15  mov     rbx, [rsp+38h+arg_8]
0x1800b0b1a  mov     rbp, [rsp+38h+arg_10]
0x1800b0b1f  add     rsp, 20h
0x1800b0b23  pop     r14
0x1800b0b25  pop     rdi
0x1800b0b26  pop     rsi
0x1800b0b27  retn
```
