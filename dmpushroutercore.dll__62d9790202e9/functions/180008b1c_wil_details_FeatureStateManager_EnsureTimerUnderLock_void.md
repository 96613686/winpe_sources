# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180008b1c`
- end: `0x180008bf0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aa74`

## callees

- `0x180008b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b69`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008b93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008b93`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008b57`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008b57`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008b8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008b8a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008b7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bd3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008b7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180008b1c  mov     [rsp+arg_8], rbx
0x180008b21  mov     [rsp+arg_10], rbp
0x180008b26  push    rsi
0x180008b27  push    rdi
0x180008b28  push    r14
0x180008b2a  sub     rsp, 20h
0x180008b2e  cmp     byte ptr [rcx+41h], 0
0x180008b32  mov     rdi, rcx
0x180008b35  jnz     loc_180008BDD
0x180008b3b  cmp     qword ptr [rcx+30h], 0
0x180008b40  jnz     short loc_180008BAD
0x180008b42  call    cs:__imp_GetLastError
0x180008b48  xor     r8d, r8d; pcbe
0x180008b4b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008b52  mov     rdx, rdi; pv
0x180008b55  mov     ebp, eax
0x180008b57  call    cs:__imp_CreateThreadpoolTimer
0x180008b5d  mov     rsi, [rdi+30h]
0x180008b61  mov     r14, rax
0x180008b64  test    rsi, rsi
0x180008b67  jz      short loc_180008BA1
0x180008b69  call    cs:__imp_GetLastError
0x180008b6f  xor     r9d, r9d; msWindowLength
0x180008b72  xor     r8d, r8d; msPeriod
0x180008b75  xor     edx, edx; pftDueTime
0x180008b77  mov     rcx, rsi; pti
0x180008b7a  mov     ebx, eax
0x180008b7c  call    cs:__imp_SetThreadpoolTimer
0x180008b82  mov     edx, 1; fCancelPendingCallbacks
0x180008b87  mov     rcx, rsi; pti
0x180008b8a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008b90  mov     rcx, rsi; pti
0x180008b93  call    cs:__imp_CloseThreadpoolTimer
0x180008b99  mov     ecx, ebx; dwErrCode
0x180008b9b  call    cs:__imp_SetLastError
0x180008ba1  mov     ecx, ebp; dwErrCode
0x180008ba3  mov     [rdi+30h], r14
0x180008ba7  call    cs:__imp_SetLastError
0x180008bad  mov     rcx, [rdi+30h]; pti
0x180008bb1  test    rcx, rcx
0x180008bb4  jz      short loc_180008BDD
0x180008bb6  mov     rax, 0FFFFFFFF4D2FA200h
0x180008bc0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180008bc5  mov     r9d, 124F8h; msWindowLength
0x180008bcb  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180008bd0  xor     r8d, r8d; msPeriod
0x180008bd3  call    cs:__imp_SetThreadpoolTimer
0x180008bd9  mov     byte ptr [rdi+41h], 1
0x180008bdd  mov     rbx, [rsp+38h+arg_8]
0x180008be2  mov     rbp, [rsp+38h+arg_10]
0x180008be7  add     rsp, 20h
0x180008beb  pop     r14
0x180008bed  pop     rdi
0x180008bee  pop     rsi
0x180008bef  retn
```
