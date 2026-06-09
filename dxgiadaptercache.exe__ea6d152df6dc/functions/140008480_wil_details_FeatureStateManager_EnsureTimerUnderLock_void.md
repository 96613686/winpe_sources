# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140008480`
- end: `0x140008554`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b304`

## callees

- `0x140008480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400084a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400084cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400084a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400084cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400084ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000850b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400084ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000850b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400084bb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400084bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400084ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400084ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400084f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400084f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400084e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008537`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400084e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008537`

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
0x140008480  mov     [rsp+arg_8], rbx
0x140008485  mov     [rsp+arg_10], rbp
0x14000848a  push    rsi
0x14000848b  push    rdi
0x14000848c  push    r14
0x14000848e  sub     rsp, 20h
0x140008492  cmp     byte ptr [rcx+41h], 0
0x140008496  mov     rdi, rcx
0x140008499  jnz     loc_140008541
0x14000849f  cmp     qword ptr [rcx+30h], 0
0x1400084a4  jnz     short loc_140008511
0x1400084a6  call    cs:__imp_GetLastError
0x1400084ac  xor     r8d, r8d; pcbe
0x1400084af  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400084b6  mov     rdx, rdi; pv
0x1400084b9  mov     ebp, eax
0x1400084bb  call    cs:__imp_CreateThreadpoolTimer
0x1400084c1  mov     rsi, [rdi+30h]
0x1400084c5  mov     r14, rax
0x1400084c8  test    rsi, rsi
0x1400084cb  jz      short loc_140008505
0x1400084cd  call    cs:__imp_GetLastError
0x1400084d3  xor     r9d, r9d; msWindowLength
0x1400084d6  xor     r8d, r8d; msPeriod
0x1400084d9  xor     edx, edx; pftDueTime
0x1400084db  mov     rcx, rsi; pti
0x1400084de  mov     ebx, eax
0x1400084e0  call    cs:__imp_SetThreadpoolTimer
0x1400084e6  mov     edx, 1; fCancelPendingCallbacks
0x1400084eb  mov     rcx, rsi; pti
0x1400084ee  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400084f4  mov     rcx, rsi; pti
0x1400084f7  call    cs:__imp_CloseThreadpoolTimer
0x1400084fd  mov     ecx, ebx; dwErrCode
0x1400084ff  call    cs:__imp_SetLastError
0x140008505  mov     ecx, ebp; dwErrCode
0x140008507  mov     [rdi+30h], r14
0x14000850b  call    cs:__imp_SetLastError
0x140008511  mov     rcx, [rdi+30h]; pti
0x140008515  test    rcx, rcx
0x140008518  jz      short loc_140008541
0x14000851a  mov     rax, 0FFFFFFFF4D2FA200h
0x140008524  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140008529  mov     r9d, 124F8h; msWindowLength
0x14000852f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140008534  xor     r8d, r8d; msPeriod
0x140008537  call    cs:__imp_SetThreadpoolTimer
0x14000853d  mov     byte ptr [rdi+41h], 1
0x140008541  mov     rbx, [rsp+38h+arg_8]
0x140008546  mov     rbp, [rsp+38h+arg_10]
0x14000854b  add     rsp, 20h
0x14000854f  pop     r14
0x140008551  pop     rdi
0x140008552  pop     rsi
0x140008553  retn
```
