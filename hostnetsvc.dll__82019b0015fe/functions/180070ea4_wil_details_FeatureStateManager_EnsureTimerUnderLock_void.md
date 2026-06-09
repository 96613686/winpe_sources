# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180070ea4`
- end: `0x180070f78`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180073774`

## callees

- `0x180070ea4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070f23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070f2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070f23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070f2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ef1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180070f1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180070f1b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070f12`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070f12`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070f04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070f5b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070f04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070f5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180070edf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180070edf`

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
0x180070ea4  mov     [rsp+arg_8], rbx
0x180070ea9  mov     [rsp+arg_10], rbp
0x180070eae  push    rsi
0x180070eaf  push    rdi
0x180070eb0  push    r14
0x180070eb2  sub     rsp, 20h
0x180070eb6  cmp     byte ptr [rcx+41h], 0
0x180070eba  mov     rdi, rcx
0x180070ebd  jnz     loc_180070F65
0x180070ec3  cmp     qword ptr [rcx+30h], 0
0x180070ec8  jnz     short loc_180070F35
0x180070eca  call    cs:__imp_GetLastError
0x180070ed0  xor     r8d, r8d; pcbe
0x180070ed3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180070eda  mov     rdx, rdi; pv
0x180070edd  mov     ebp, eax
0x180070edf  call    cs:__imp_CreateThreadpoolTimer
0x180070ee5  mov     rsi, [rdi+30h]
0x180070ee9  mov     r14, rax
0x180070eec  test    rsi, rsi
0x180070eef  jz      short loc_180070F29
0x180070ef1  call    cs:__imp_GetLastError
0x180070ef7  xor     r9d, r9d; msWindowLength
0x180070efa  xor     r8d, r8d; msPeriod
0x180070efd  xor     edx, edx; pftDueTime
0x180070eff  mov     rcx, rsi; pti
0x180070f02  mov     ebx, eax
0x180070f04  call    cs:__imp_SetThreadpoolTimer
0x180070f0a  mov     edx, 1; fCancelPendingCallbacks
0x180070f0f  mov     rcx, rsi; pti
0x180070f12  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180070f18  mov     rcx, rsi; pti
0x180070f1b  call    cs:__imp_CloseThreadpoolTimer
0x180070f21  mov     ecx, ebx; dwErrCode
0x180070f23  call    cs:__imp_SetLastError
0x180070f29  mov     ecx, ebp; dwErrCode
0x180070f2b  mov     [rdi+30h], r14
0x180070f2f  call    cs:__imp_SetLastError
0x180070f35  mov     rcx, [rdi+30h]; pti
0x180070f39  test    rcx, rcx
0x180070f3c  jz      short loc_180070F65
0x180070f3e  mov     rax, 0FFFFFFFF4D2FA200h
0x180070f48  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180070f4d  mov     r9d, 124F8h; msWindowLength
0x180070f53  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180070f58  xor     r8d, r8d; msPeriod
0x180070f5b  call    cs:__imp_SetThreadpoolTimer
0x180070f61  mov     byte ptr [rdi+41h], 1
0x180070f65  mov     rbx, [rsp+38h+arg_8]
0x180070f6a  mov     rbp, [rsp+38h+arg_10]
0x180070f6f  add     rsp, 20h
0x180070f73  pop     r14
0x180070f75  pop     rdi
0x180070f76  pop     rsi
0x180070f77  retn
```
