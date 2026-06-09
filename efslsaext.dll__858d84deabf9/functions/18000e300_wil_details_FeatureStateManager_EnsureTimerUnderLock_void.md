# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000e300`
- end: `0x18000e3d4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010090`

## callees

- `0x18000e300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e34d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e34d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e37f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e38b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e37f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e38b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e377`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e377`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e360`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e3b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e360`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e3b7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e36e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e36e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e33b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e33b`

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
0x18000e300  mov     [rsp+arg_8], rbx
0x18000e305  mov     [rsp+arg_10], rbp
0x18000e30a  push    rsi
0x18000e30b  push    rdi
0x18000e30c  push    r14
0x18000e30e  sub     rsp, 20h
0x18000e312  cmp     byte ptr [rcx+41h], 0
0x18000e316  mov     rdi, rcx
0x18000e319  jnz     loc_18000E3C1
0x18000e31f  cmp     qword ptr [rcx+30h], 0
0x18000e324  jnz     short loc_18000E391
0x18000e326  call    cs:__imp_GetLastError
0x18000e32c  xor     r8d, r8d; pcbe
0x18000e32f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000e336  mov     rdx, rdi; pv
0x18000e339  mov     ebp, eax
0x18000e33b  call    cs:__imp_CreateThreadpoolTimer
0x18000e341  mov     rsi, [rdi+30h]
0x18000e345  mov     r14, rax
0x18000e348  test    rsi, rsi
0x18000e34b  jz      short loc_18000E385
0x18000e34d  call    cs:__imp_GetLastError
0x18000e353  xor     r9d, r9d; msWindowLength
0x18000e356  xor     r8d, r8d; msPeriod
0x18000e359  xor     edx, edx; pftDueTime
0x18000e35b  mov     rcx, rsi; pti
0x18000e35e  mov     ebx, eax
0x18000e360  call    cs:__imp_SetThreadpoolTimer
0x18000e366  mov     edx, 1; fCancelPendingCallbacks
0x18000e36b  mov     rcx, rsi; pti
0x18000e36e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e374  mov     rcx, rsi; pti
0x18000e377  call    cs:__imp_CloseThreadpoolTimer
0x18000e37d  mov     ecx, ebx; dwErrCode
0x18000e37f  call    cs:__imp_SetLastError
0x18000e385  mov     ecx, ebp; dwErrCode
0x18000e387  mov     [rdi+30h], r14
0x18000e38b  call    cs:__imp_SetLastError
0x18000e391  mov     rcx, [rdi+30h]; pti
0x18000e395  test    rcx, rcx
0x18000e398  jz      short loc_18000E3C1
0x18000e39a  mov     rax, 0FFFFFFFF4D2FA200h
0x18000e3a4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000e3a9  mov     r9d, 124F8h; msWindowLength
0x18000e3af  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000e3b4  xor     r8d, r8d; msPeriod
0x18000e3b7  call    cs:__imp_SetThreadpoolTimer
0x18000e3bd  mov     byte ptr [rdi+41h], 1
0x18000e3c1  mov     rbx, [rsp+38h+arg_8]
0x18000e3c6  mov     rbp, [rsp+38h+arg_10]
0x18000e3cb  add     rsp, 20h
0x18000e3cf  pop     r14
0x18000e3d1  pop     rdi
0x18000e3d2  pop     rsi
0x18000e3d3  retn
```
