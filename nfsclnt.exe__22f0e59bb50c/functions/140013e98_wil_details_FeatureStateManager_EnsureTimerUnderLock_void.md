# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140013e98`
- end: `0x140013f6c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400158f4`

## callees

- `0x140013e98`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140013f06`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140013f06`
- `KERNEL32!CloseThreadpoolTimer` at `0x140013f0f`
- `KERNEL32!CloseThreadpoolTimer` at `0x140013f0f`
- `KERNEL32!GetLastError` at `0x140013ebe`
- `KERNEL32!GetLastError` at `0x140013ee5`
- `KERNEL32!GetLastError` at `0x140013ebe`
- `KERNEL32!GetLastError` at `0x140013ee5`
- `KERNEL32!SetThreadpoolTimer` at `0x140013ef8`
- `KERNEL32!SetThreadpoolTimer` at `0x140013f4f`
- `KERNEL32!SetThreadpoolTimer` at `0x140013ef8`
- `KERNEL32!SetThreadpoolTimer` at `0x140013f4f`
- `KERNEL32!CreateThreadpoolTimer` at `0x140013ed3`
- `KERNEL32!CreateThreadpoolTimer` at `0x140013ed3`
- `KERNEL32!SetLastError` at `0x140013f17`
- `KERNEL32!SetLastError` at `0x140013f23`
- `KERNEL32!SetLastError` at `0x140013f17`
- `KERNEL32!SetLastError` at `0x140013f23`

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
0x140013e98  mov     [rsp+arg_8], rbx
0x140013e9d  mov     [rsp+arg_10], rbp
0x140013ea2  push    rsi
0x140013ea3  push    rdi
0x140013ea4  push    r14
0x140013ea6  sub     rsp, 20h
0x140013eaa  cmp     byte ptr [rcx+41h], 0
0x140013eae  mov     rdi, rcx
0x140013eb1  jnz     loc_140013F59
0x140013eb7  cmp     qword ptr [rcx+30h], 0
0x140013ebc  jnz     short loc_140013F29
0x140013ebe  call    cs:__imp_GetLastError
0x140013ec4  xor     r8d, r8d; pcbe
0x140013ec7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140013ece  mov     rdx, rdi; pv
0x140013ed1  mov     ebp, eax
0x140013ed3  call    cs:__imp_CreateThreadpoolTimer
0x140013ed9  mov     rsi, [rdi+30h]
0x140013edd  mov     r14, rax
0x140013ee0  test    rsi, rsi
0x140013ee3  jz      short loc_140013F1D
0x140013ee5  call    cs:__imp_GetLastError
0x140013eeb  xor     r9d, r9d; msWindowLength
0x140013eee  xor     r8d, r8d; msPeriod
0x140013ef1  xor     edx, edx; pftDueTime
0x140013ef3  mov     rcx, rsi; pti
0x140013ef6  mov     ebx, eax
0x140013ef8  call    cs:__imp_SetThreadpoolTimer
0x140013efe  mov     edx, 1; fCancelPendingCallbacks
0x140013f03  mov     rcx, rsi; pti
0x140013f06  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013f0c  mov     rcx, rsi; pti
0x140013f0f  call    cs:__imp_CloseThreadpoolTimer
0x140013f15  mov     ecx, ebx; dwErrCode
0x140013f17  call    cs:__imp_SetLastError
0x140013f1d  mov     ecx, ebp; dwErrCode
0x140013f1f  mov     [rdi+30h], r14
0x140013f23  call    cs:__imp_SetLastError
0x140013f29  mov     rcx, [rdi+30h]; pti
0x140013f2d  test    rcx, rcx
0x140013f30  jz      short loc_140013F59
0x140013f32  mov     rax, 0FFFFFFFF4D2FA200h
0x140013f3c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140013f41  mov     r9d, 124F8h; msWindowLength
0x140013f47  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140013f4c  xor     r8d, r8d; msPeriod
0x140013f4f  call    cs:__imp_SetThreadpoolTimer
0x140013f55  mov     byte ptr [rdi+41h], 1
0x140013f59  mov     rbx, [rsp+38h+arg_8]
0x140013f5e  mov     rbp, [rsp+38h+arg_10]
0x140013f63  add     rsp, 20h
0x140013f67  pop     r14
0x140013f69  pop     rdi
0x140013f6a  pop     rsi
0x140013f6b  retn
```
