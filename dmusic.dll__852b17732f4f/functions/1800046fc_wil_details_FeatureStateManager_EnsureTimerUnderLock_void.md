# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800046fc`
- end: `0x1800047d0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800067a4`

## callees

- `0x1800046fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004749`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000477b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004787`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000477b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004787`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000475c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800047b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000475c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800047b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004773`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004773`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000476a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000476a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004737`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004737`

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
0x1800046fc  mov     [rsp+arg_8], rbx
0x180004701  mov     [rsp+arg_10], rbp
0x180004706  push    rsi
0x180004707  push    rdi
0x180004708  push    r14
0x18000470a  sub     rsp, 20h
0x18000470e  cmp     byte ptr [rcx+41h], 0
0x180004712  mov     rdi, rcx
0x180004715  jnz     loc_1800047BD
0x18000471b  cmp     qword ptr [rcx+30h], 0
0x180004720  jnz     short loc_18000478D
0x180004722  call    cs:__imp_GetLastError
0x180004728  xor     r8d, r8d; pcbe
0x18000472b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004732  mov     rdx, rdi; pv
0x180004735  mov     ebp, eax
0x180004737  call    cs:__imp_CreateThreadpoolTimer
0x18000473d  mov     rsi, [rdi+30h]
0x180004741  mov     r14, rax
0x180004744  test    rsi, rsi
0x180004747  jz      short loc_180004781
0x180004749  call    cs:__imp_GetLastError
0x18000474f  xor     r9d, r9d; msWindowLength
0x180004752  xor     r8d, r8d; msPeriod
0x180004755  xor     edx, edx; pftDueTime
0x180004757  mov     rcx, rsi; pti
0x18000475a  mov     ebx, eax
0x18000475c  call    cs:__imp_SetThreadpoolTimer
0x180004762  mov     edx, 1; fCancelPendingCallbacks
0x180004767  mov     rcx, rsi; pti
0x18000476a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004770  mov     rcx, rsi; pti
0x180004773  call    cs:__imp_CloseThreadpoolTimer
0x180004779  mov     ecx, ebx; dwErrCode
0x18000477b  call    cs:__imp_SetLastError
0x180004781  mov     ecx, ebp; dwErrCode
0x180004783  mov     [rdi+30h], r14
0x180004787  call    cs:__imp_SetLastError
0x18000478d  mov     rcx, [rdi+30h]; pti
0x180004791  test    rcx, rcx
0x180004794  jz      short loc_1800047BD
0x180004796  mov     rax, 0FFFFFFFF4D2FA200h
0x1800047a0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800047a5  mov     r9d, 124F8h; msWindowLength
0x1800047ab  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800047b0  xor     r8d, r8d; msPeriod
0x1800047b3  call    cs:__imp_SetThreadpoolTimer
0x1800047b9  mov     byte ptr [rdi+41h], 1
0x1800047bd  mov     rbx, [rsp+38h+arg_8]
0x1800047c2  mov     rbp, [rsp+38h+arg_10]
0x1800047c7  add     rsp, 20h
0x1800047cb  pop     r14
0x1800047cd  pop     rdi
0x1800047ce  pop     rsi
0x1800047cf  retn
```
