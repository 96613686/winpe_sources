# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180004fdc`
- end: `0x1800050b0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006f74`

## callees

- `0x180004fdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000505b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005067`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000505b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005029`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000503c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005093`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000503c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005093`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005053`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005053`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000504a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000504a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005017`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005017`

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
0x180004fdc  mov     [rsp+arg_8], rbx
0x180004fe1  mov     [rsp+arg_10], rbp
0x180004fe6  push    rsi
0x180004fe7  push    rdi
0x180004fe8  push    r14
0x180004fea  sub     rsp, 20h
0x180004fee  cmp     byte ptr [rcx+41h], 0
0x180004ff2  mov     rdi, rcx
0x180004ff5  jnz     loc_18000509D
0x180004ffb  cmp     qword ptr [rcx+30h], 0
0x180005000  jnz     short loc_18000506D
0x180005002  call    cs:__imp_GetLastError
0x180005008  xor     r8d, r8d; pcbe
0x18000500b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005012  mov     rdx, rdi; pv
0x180005015  mov     ebp, eax
0x180005017  call    cs:__imp_CreateThreadpoolTimer
0x18000501d  mov     rsi, [rdi+30h]
0x180005021  mov     r14, rax
0x180005024  test    rsi, rsi
0x180005027  jz      short loc_180005061
0x180005029  call    cs:__imp_GetLastError
0x18000502f  xor     r9d, r9d; msWindowLength
0x180005032  xor     r8d, r8d; msPeriod
0x180005035  xor     edx, edx; pftDueTime
0x180005037  mov     rcx, rsi; pti
0x18000503a  mov     ebx, eax
0x18000503c  call    cs:__imp_SetThreadpoolTimer
0x180005042  mov     edx, 1; fCancelPendingCallbacks
0x180005047  mov     rcx, rsi; pti
0x18000504a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005050  mov     rcx, rsi; pti
0x180005053  call    cs:__imp_CloseThreadpoolTimer
0x180005059  mov     ecx, ebx; dwErrCode
0x18000505b  call    cs:__imp_SetLastError
0x180005061  mov     ecx, ebp; dwErrCode
0x180005063  mov     [rdi+30h], r14
0x180005067  call    cs:__imp_SetLastError
0x18000506d  mov     rcx, [rdi+30h]; pti
0x180005071  test    rcx, rcx
0x180005074  jz      short loc_18000509D
0x180005076  mov     rax, 0FFFFFFFF4D2FA200h
0x180005080  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005085  mov     r9d, 124F8h; msWindowLength
0x18000508b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005090  xor     r8d, r8d; msPeriod
0x180005093  call    cs:__imp_SetThreadpoolTimer
0x180005099  mov     byte ptr [rdi+41h], 1
0x18000509d  mov     rbx, [rsp+38h+arg_8]
0x1800050a2  mov     rbp, [rsp+38h+arg_10]
0x1800050a7  add     rsp, 20h
0x1800050ab  pop     r14
0x1800050ad  pop     rdi
0x1800050ae  pop     rsi
0x1800050af  retn
```
