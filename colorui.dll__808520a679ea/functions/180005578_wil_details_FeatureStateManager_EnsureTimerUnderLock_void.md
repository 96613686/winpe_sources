# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005578`
- end: `0x18000564c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007d94`

## callees

- `0x180005578`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800055e6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800055e6`
- `KERNEL32!GetLastError` at `0x18000559e`
- `KERNEL32!GetLastError` at `0x1800055c5`
- `KERNEL32!GetLastError` at `0x18000559e`
- `KERNEL32!GetLastError` at `0x1800055c5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800055ef`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800055ef`
- `KERNEL32!SetThreadpoolTimer` at `0x1800055d8`
- `KERNEL32!SetThreadpoolTimer` at `0x18000562f`
- `KERNEL32!SetThreadpoolTimer` at `0x1800055d8`
- `KERNEL32!SetThreadpoolTimer` at `0x18000562f`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800055b3`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800055b3`
- `KERNEL32!SetLastError` at `0x1800055f7`
- `KERNEL32!SetLastError` at `0x180005603`
- `KERNEL32!SetLastError` at `0x1800055f7`
- `KERNEL32!SetLastError` at `0x180005603`

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
0x180005578  mov     [rsp+arg_8], rbx
0x18000557d  mov     [rsp+arg_10], rbp
0x180005582  push    rsi
0x180005583  push    rdi
0x180005584  push    r14
0x180005586  sub     rsp, 20h
0x18000558a  cmp     byte ptr [rcx+41h], 0
0x18000558e  mov     rdi, rcx
0x180005591  jnz     loc_180005639
0x180005597  cmp     qword ptr [rcx+30h], 0
0x18000559c  jnz     short loc_180005609
0x18000559e  call    cs:__imp_GetLastError
0x1800055a4  xor     r8d, r8d; pcbe
0x1800055a7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800055ae  mov     rdx, rdi; pv
0x1800055b1  mov     ebp, eax
0x1800055b3  call    cs:__imp_CreateThreadpoolTimer
0x1800055b9  mov     rsi, [rdi+30h]
0x1800055bd  mov     r14, rax
0x1800055c0  test    rsi, rsi
0x1800055c3  jz      short loc_1800055FD
0x1800055c5  call    cs:__imp_GetLastError
0x1800055cb  xor     r9d, r9d; msWindowLength
0x1800055ce  xor     r8d, r8d; msPeriod
0x1800055d1  xor     edx, edx; pftDueTime
0x1800055d3  mov     rcx, rsi; pti
0x1800055d6  mov     ebx, eax
0x1800055d8  call    cs:__imp_SetThreadpoolTimer
0x1800055de  mov     edx, 1; fCancelPendingCallbacks
0x1800055e3  mov     rcx, rsi; pti
0x1800055e6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800055ec  mov     rcx, rsi; pti
0x1800055ef  call    cs:__imp_CloseThreadpoolTimer
0x1800055f5  mov     ecx, ebx; dwErrCode
0x1800055f7  call    cs:__imp_SetLastError
0x1800055fd  mov     ecx, ebp; dwErrCode
0x1800055ff  mov     [rdi+30h], r14
0x180005603  call    cs:__imp_SetLastError
0x180005609  mov     rcx, [rdi+30h]; pti
0x18000560d  test    rcx, rcx
0x180005610  jz      short loc_180005639
0x180005612  mov     rax, 0FFFFFFFF4D2FA200h
0x18000561c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005621  mov     r9d, 124F8h; msWindowLength
0x180005627  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000562c  xor     r8d, r8d; msPeriod
0x18000562f  call    cs:__imp_SetThreadpoolTimer
0x180005635  mov     byte ptr [rdi+41h], 1
0x180005639  mov     rbx, [rsp+38h+arg_8]
0x18000563e  mov     rbp, [rsp+38h+arg_10]
0x180005643  add     rsp, 20h
0x180005647  pop     r14
0x180005649  pop     rdi
0x18000564a  pop     rsi
0x18000564b  retn
```
