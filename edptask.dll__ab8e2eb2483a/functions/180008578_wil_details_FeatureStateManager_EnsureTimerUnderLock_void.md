# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180008578`
- end: `0x18000864c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f624`

## callees

- `0x180008578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008603`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000859e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000859e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800085ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800085ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800085b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800085b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800085e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800085e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800085d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000862f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800085d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000862f`

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
0x180008578  mov     [rsp+arg_8], rbx
0x18000857d  mov     [rsp+arg_10], rbp
0x180008582  push    rsi
0x180008583  push    rdi
0x180008584  push    r14
0x180008586  sub     rsp, 20h
0x18000858a  cmp     byte ptr [rcx+41h], 0
0x18000858e  mov     rdi, rcx
0x180008591  jnz     loc_180008639
0x180008597  cmp     qword ptr [rcx+30h], 0
0x18000859c  jnz     short loc_180008609
0x18000859e  call    cs:__imp_GetLastError
0x1800085a4  xor     r8d, r8d; pcbe
0x1800085a7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800085ae  mov     rdx, rdi; pv
0x1800085b1  mov     ebp, eax
0x1800085b3  call    cs:__imp_CreateThreadpoolTimer
0x1800085b9  mov     rsi, [rdi+30h]
0x1800085bd  mov     r14, rax
0x1800085c0  test    rsi, rsi
0x1800085c3  jz      short loc_1800085FD
0x1800085c5  call    cs:__imp_GetLastError
0x1800085cb  xor     r9d, r9d; msWindowLength
0x1800085ce  xor     r8d, r8d; msPeriod
0x1800085d1  xor     edx, edx; pftDueTime
0x1800085d3  mov     rcx, rsi; pti
0x1800085d6  mov     ebx, eax
0x1800085d8  call    cs:__imp_SetThreadpoolTimer
0x1800085de  mov     edx, 1; fCancelPendingCallbacks
0x1800085e3  mov     rcx, rsi; pti
0x1800085e6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800085ec  mov     rcx, rsi; pti
0x1800085ef  call    cs:__imp_CloseThreadpoolTimer
0x1800085f5  mov     ecx, ebx; dwErrCode
0x1800085f7  call    cs:__imp_SetLastError
0x1800085fd  mov     ecx, ebp; dwErrCode
0x1800085ff  mov     [rdi+30h], r14
0x180008603  call    cs:__imp_SetLastError
0x180008609  mov     rcx, [rdi+30h]; pti
0x18000860d  test    rcx, rcx
0x180008610  jz      short loc_180008639
0x180008612  mov     rax, 0FFFFFFFF4D2FA200h
0x18000861c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180008621  mov     r9d, 124F8h; msWindowLength
0x180008627  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000862c  xor     r8d, r8d; msPeriod
0x18000862f  call    cs:__imp_SetThreadpoolTimer
0x180008635  mov     byte ptr [rdi+41h], 1
0x180008639  mov     rbx, [rsp+38h+arg_8]
0x18000863e  mov     rbp, [rsp+38h+arg_10]
0x180008643  add     rsp, 20h
0x180008647  pop     r14
0x180008649  pop     rdi
0x18000864a  pop     rsi
0x18000864b  retn
```
