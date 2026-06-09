# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000505c`
- end: `0x180005130`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006fa4`

## callees

- `0x18000505c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800050bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005113`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800050bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005113`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800050ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800050ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005097`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005097`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800050d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800050d3`

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
0x18000505c  mov     [rsp+arg_8], rbx
0x180005061  mov     [rsp+arg_10], rbp
0x180005066  push    rsi
0x180005067  push    rdi
0x180005068  push    r14
0x18000506a  sub     rsp, 20h
0x18000506e  cmp     byte ptr [rcx+41h], 0
0x180005072  mov     rdi, rcx
0x180005075  jnz     loc_18000511D
0x18000507b  cmp     qword ptr [rcx+30h], 0
0x180005080  jnz     short loc_1800050ED
0x180005082  call    cs:__imp_GetLastError
0x180005088  xor     r8d, r8d; pcbe
0x18000508b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005092  mov     rdx, rdi; pv
0x180005095  mov     ebp, eax
0x180005097  call    cs:__imp_CreateThreadpoolTimer
0x18000509d  mov     rsi, [rdi+30h]
0x1800050a1  mov     r14, rax
0x1800050a4  test    rsi, rsi
0x1800050a7  jz      short loc_1800050E1
0x1800050a9  call    cs:__imp_GetLastError
0x1800050af  xor     r9d, r9d; msWindowLength
0x1800050b2  xor     r8d, r8d; msPeriod
0x1800050b5  xor     edx, edx; pftDueTime
0x1800050b7  mov     rcx, rsi; pti
0x1800050ba  mov     ebx, eax
0x1800050bc  call    cs:__imp_SetThreadpoolTimer
0x1800050c2  mov     edx, 1; fCancelPendingCallbacks
0x1800050c7  mov     rcx, rsi; pti
0x1800050ca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800050d0  mov     rcx, rsi; pti
0x1800050d3  call    cs:__imp_CloseThreadpoolTimer
0x1800050d9  mov     ecx, ebx; dwErrCode
0x1800050db  call    cs:__imp_SetLastError
0x1800050e1  mov     ecx, ebp; dwErrCode
0x1800050e3  mov     [rdi+30h], r14
0x1800050e7  call    cs:__imp_SetLastError
0x1800050ed  mov     rcx, [rdi+30h]; pti
0x1800050f1  test    rcx, rcx
0x1800050f4  jz      short loc_18000511D
0x1800050f6  mov     rax, 0FFFFFFFF4D2FA200h
0x180005100  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005105  mov     r9d, 124F8h; msWindowLength
0x18000510b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005110  xor     r8d, r8d; msPeriod
0x180005113  call    cs:__imp_SetThreadpoolTimer
0x180005119  mov     byte ptr [rdi+41h], 1
0x18000511d  mov     rbx, [rsp+38h+arg_8]
0x180005122  mov     rbp, [rsp+38h+arg_10]
0x180005127  add     rsp, 20h
0x18000512b  pop     r14
0x18000512d  pop     rdi
0x18000512e  pop     rsi
0x18000512f  retn
```
