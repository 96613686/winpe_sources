# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800050ac`
- end: `0x180005180`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007d14`

## callees

- `0x1800050ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000512b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005137`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000512b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005137`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005123`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005123`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000510c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005163`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000510c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005163`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800050e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800050e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000511a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000511a`

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
0x1800050ac  mov     [rsp+arg_8], rbx
0x1800050b1  mov     [rsp+arg_10], rbp
0x1800050b6  push    rsi
0x1800050b7  push    rdi
0x1800050b8  push    r14
0x1800050ba  sub     rsp, 20h
0x1800050be  cmp     byte ptr [rcx+41h], 0
0x1800050c2  mov     rdi, rcx
0x1800050c5  jnz     loc_18000516D
0x1800050cb  cmp     qword ptr [rcx+30h], 0
0x1800050d0  jnz     short loc_18000513D
0x1800050d2  call    cs:__imp_GetLastError
0x1800050d8  xor     r8d, r8d; pcbe
0x1800050db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800050e2  mov     rdx, rdi; pv
0x1800050e5  mov     ebp, eax
0x1800050e7  call    cs:__imp_CreateThreadpoolTimer
0x1800050ed  mov     rsi, [rdi+30h]
0x1800050f1  mov     r14, rax
0x1800050f4  test    rsi, rsi
0x1800050f7  jz      short loc_180005131
0x1800050f9  call    cs:__imp_GetLastError
0x1800050ff  xor     r9d, r9d; msWindowLength
0x180005102  xor     r8d, r8d; msPeriod
0x180005105  xor     edx, edx; pftDueTime
0x180005107  mov     rcx, rsi; pti
0x18000510a  mov     ebx, eax
0x18000510c  call    cs:__imp_SetThreadpoolTimer
0x180005112  mov     edx, 1; fCancelPendingCallbacks
0x180005117  mov     rcx, rsi; pti
0x18000511a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005120  mov     rcx, rsi; pti
0x180005123  call    cs:__imp_CloseThreadpoolTimer
0x180005129  mov     ecx, ebx; dwErrCode
0x18000512b  call    cs:__imp_SetLastError
0x180005131  mov     ecx, ebp; dwErrCode
0x180005133  mov     [rdi+30h], r14
0x180005137  call    cs:__imp_SetLastError
0x18000513d  mov     rcx, [rdi+30h]; pti
0x180005141  test    rcx, rcx
0x180005144  jz      short loc_18000516D
0x180005146  mov     rax, 0FFFFFFFF4D2FA200h
0x180005150  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005155  mov     r9d, 124F8h; msWindowLength
0x18000515b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005160  xor     r8d, r8d; msPeriod
0x180005163  call    cs:__imp_SetThreadpoolTimer
0x180005169  mov     byte ptr [rdi+41h], 1
0x18000516d  mov     rbx, [rsp+38h+arg_8]
0x180005172  mov     rbp, [rsp+38h+arg_10]
0x180005177  add     rsp, 20h
0x18000517b  pop     r14
0x18000517d  pop     rdi
0x18000517e  pop     rsi
0x18000517f  retn
```
