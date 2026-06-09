# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180004c08`
- end: `0x180004cdc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006664`

## callees

- `0x180004c08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c68`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004cbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c68`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004cbf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c7f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004c43`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004c43`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c76`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c93`

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
0x180004c08  mov     [rsp+arg_8], rbx
0x180004c0d  mov     [rsp+arg_10], rbp
0x180004c12  push    rsi
0x180004c13  push    rdi
0x180004c14  push    r14
0x180004c16  sub     rsp, 20h
0x180004c1a  cmp     byte ptr [rcx+41h], 0
0x180004c1e  mov     rdi, rcx
0x180004c21  jnz     loc_180004CC9
0x180004c27  cmp     qword ptr [rcx+30h], 0
0x180004c2c  jnz     short loc_180004C99
0x180004c2e  call    cs:__imp_GetLastError
0x180004c34  xor     r8d, r8d; pcbe
0x180004c37  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004c3e  mov     rdx, rdi; pv
0x180004c41  mov     ebp, eax
0x180004c43  call    cs:__imp_CreateThreadpoolTimer
0x180004c49  mov     rsi, [rdi+30h]
0x180004c4d  mov     r14, rax
0x180004c50  test    rsi, rsi
0x180004c53  jz      short loc_180004C8D
0x180004c55  call    cs:__imp_GetLastError
0x180004c5b  xor     r9d, r9d; msWindowLength
0x180004c5e  xor     r8d, r8d; msPeriod
0x180004c61  xor     edx, edx; pftDueTime
0x180004c63  mov     rcx, rsi; pti
0x180004c66  mov     ebx, eax
0x180004c68  call    cs:__imp_SetThreadpoolTimer
0x180004c6e  mov     edx, 1; fCancelPendingCallbacks
0x180004c73  mov     rcx, rsi; pti
0x180004c76  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004c7c  mov     rcx, rsi; pti
0x180004c7f  call    cs:__imp_CloseThreadpoolTimer
0x180004c85  mov     ecx, ebx; dwErrCode
0x180004c87  call    cs:__imp_SetLastError
0x180004c8d  mov     ecx, ebp; dwErrCode
0x180004c8f  mov     [rdi+30h], r14
0x180004c93  call    cs:__imp_SetLastError
0x180004c99  mov     rcx, [rdi+30h]; pti
0x180004c9d  test    rcx, rcx
0x180004ca0  jz      short loc_180004CC9
0x180004ca2  mov     rax, 0FFFFFFFF4D2FA200h
0x180004cac  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004cb1  mov     r9d, 124F8h; msWindowLength
0x180004cb7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180004cbc  xor     r8d, r8d; msPeriod
0x180004cbf  call    cs:__imp_SetThreadpoolTimer
0x180004cc5  mov     byte ptr [rdi+41h], 1
0x180004cc9  mov     rbx, [rsp+38h+arg_8]
0x180004cce  mov     rbp, [rsp+38h+arg_10]
0x180004cd3  add     rsp, 20h
0x180004cd7  pop     r14
0x180004cd9  pop     rdi
0x180004cda  pop     rsi
0x180004cdb  retn
```
