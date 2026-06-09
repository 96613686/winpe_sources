# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180012570`
- end: `0x180012644`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800151f4`

## callees

- `0x180012570`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800125ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800125fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800125ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800125fb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800125ab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800125ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800125d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012627`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800125d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012627`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800125e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800125e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800125de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800125de`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
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
0x180012570  mov     [rsp+arg_8], rbx
0x180012575  mov     [rsp+arg_10], rbp
0x18001257a  push    rsi
0x18001257b  push    rdi
0x18001257c  push    r14
0x18001257e  sub     rsp, 20h
0x180012582  cmp     byte ptr [rcx+41h], 0
0x180012586  mov     rdi, rcx
0x180012589  jnz     loc_180012631
0x18001258f  cmp     qword ptr [rcx+30h], 0
0x180012594  jnz     short loc_180012601
0x180012596  call    cs:__imp_GetLastError
0x18001259c  xor     r8d, r8d; pcbe
0x18001259f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800125a6  mov     rdx, rdi; pv
0x1800125a9  mov     ebp, eax
0x1800125ab  call    cs:__imp_CreateThreadpoolTimer
0x1800125b1  mov     rsi, [rdi+30h]
0x1800125b5  mov     r14, rax
0x1800125b8  test    rsi, rsi
0x1800125bb  jz      short loc_1800125F5
0x1800125bd  call    cs:__imp_GetLastError
0x1800125c3  xor     r9d, r9d; msWindowLength
0x1800125c6  xor     r8d, r8d; msPeriod
0x1800125c9  xor     edx, edx; pftDueTime
0x1800125cb  mov     rcx, rsi; pti
0x1800125ce  mov     ebx, eax
0x1800125d0  call    cs:__imp_SetThreadpoolTimer
0x1800125d6  mov     edx, 1; fCancelPendingCallbacks
0x1800125db  mov     rcx, rsi; pti
0x1800125de  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800125e4  mov     rcx, rsi; pti
0x1800125e7  call    cs:__imp_CloseThreadpoolTimer
0x1800125ed  mov     ecx, ebx; dwErrCode
0x1800125ef  call    cs:__imp_SetLastError
0x1800125f5  mov     ecx, ebp; dwErrCode
0x1800125f7  mov     [rdi+30h], r14
0x1800125fb  call    cs:__imp_SetLastError
0x180012601  mov     rcx, [rdi+30h]; pti
0x180012605  test    rcx, rcx
0x180012608  jz      short loc_180012631
0x18001260a  mov     rax, 0FFFFFFFF4D2FA200h
0x180012614  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180012619  mov     r9d, 124F8h; msWindowLength
0x18001261f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180012624  xor     r8d, r8d; msPeriod
0x180012627  call    cs:__imp_SetThreadpoolTimer
0x18001262d  mov     byte ptr [rdi+41h], 1
0x180012631  mov     rbx, [rsp+38h+arg_8]
0x180012636  mov     rbp, [rsp+38h+arg_10]
0x18001263b  add     rsp, 20h
0x18001263f  pop     r14
0x180012641  pop     rdi
0x180012642  pop     rsi
0x180012643  retn
```
