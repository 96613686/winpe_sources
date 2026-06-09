# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800093c8`
- end: `0x18000949c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ad74`

## callees

- `0x1800093c8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180009447`
- `KERNEL32!SetLastError` at `0x180009453`
- `KERNEL32!SetLastError` at `0x180009447`
- `KERNEL32!SetLastError` at `0x180009453`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009436`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009436`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000943f`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000943f`
- `KERNEL32!SetThreadpoolTimer` at `0x180009428`
- `KERNEL32!SetThreadpoolTimer` at `0x18000947f`
- `KERNEL32!SetThreadpoolTimer` at `0x180009428`
- `KERNEL32!SetThreadpoolTimer` at `0x18000947f`
- `KERNEL32!CreateThreadpoolTimer` at `0x180009403`
- `KERNEL32!CreateThreadpoolTimer` at `0x180009403`
- `KERNEL32!GetLastError` at `0x1800093ee`
- `KERNEL32!GetLastError` at `0x180009415`
- `KERNEL32!GetLastError` at `0x1800093ee`
- `KERNEL32!GetLastError` at `0x180009415`

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
0x1800093c8  mov     [rsp+arg_8], rbx
0x1800093cd  mov     [rsp+arg_10], rbp
0x1800093d2  push    rsi
0x1800093d3  push    rdi
0x1800093d4  push    r14
0x1800093d6  sub     rsp, 20h
0x1800093da  cmp     byte ptr [rcx+41h], 0
0x1800093de  mov     rdi, rcx
0x1800093e1  jnz     loc_180009489
0x1800093e7  cmp     qword ptr [rcx+30h], 0
0x1800093ec  jnz     short loc_180009459
0x1800093ee  call    cs:__imp_GetLastError
0x1800093f4  xor     r8d, r8d; pcbe
0x1800093f7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800093fe  mov     rdx, rdi; pv
0x180009401  mov     ebp, eax
0x180009403  call    cs:__imp_CreateThreadpoolTimer
0x180009409  mov     rsi, [rdi+30h]
0x18000940d  mov     r14, rax
0x180009410  test    rsi, rsi
0x180009413  jz      short loc_18000944D
0x180009415  call    cs:__imp_GetLastError
0x18000941b  xor     r9d, r9d; msWindowLength
0x18000941e  xor     r8d, r8d; msPeriod
0x180009421  xor     edx, edx; pftDueTime
0x180009423  mov     rcx, rsi; pti
0x180009426  mov     ebx, eax
0x180009428  call    cs:__imp_SetThreadpoolTimer
0x18000942e  mov     edx, 1; fCancelPendingCallbacks
0x180009433  mov     rcx, rsi; pti
0x180009436  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000943c  mov     rcx, rsi; pti
0x18000943f  call    cs:__imp_CloseThreadpoolTimer
0x180009445  mov     ecx, ebx; dwErrCode
0x180009447  call    cs:__imp_SetLastError
0x18000944d  mov     ecx, ebp; dwErrCode
0x18000944f  mov     [rdi+30h], r14
0x180009453  call    cs:__imp_SetLastError
0x180009459  mov     rcx, [rdi+30h]; pti
0x18000945d  test    rcx, rcx
0x180009460  jz      short loc_180009489
0x180009462  mov     rax, 0FFFFFFFF4D2FA200h
0x18000946c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180009471  mov     r9d, 124F8h; msWindowLength
0x180009477  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000947c  xor     r8d, r8d; msPeriod
0x18000947f  call    cs:__imp_SetThreadpoolTimer
0x180009485  mov     byte ptr [rdi+41h], 1
0x180009489  mov     rbx, [rsp+38h+arg_8]
0x18000948e  mov     rbp, [rsp+38h+arg_10]
0x180009493  add     rsp, 20h
0x180009497  pop     r14
0x180009499  pop     rdi
0x18000949a  pop     rsi
0x18000949b  retn
```
