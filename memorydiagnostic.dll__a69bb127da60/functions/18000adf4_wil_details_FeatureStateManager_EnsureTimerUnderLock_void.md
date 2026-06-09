# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000adf4`
- end: `0x18000aec8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f294`

## callees

- `0x18000adf4`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18000ae2f`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000ae2f`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ae54`
- `KERNEL32!SetThreadpoolTimer` at `0x18000aeab`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ae54`
- `KERNEL32!SetThreadpoolTimer` at `0x18000aeab`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000ae6b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000ae6b`
- `KERNEL32!GetLastError` at `0x18000ae1a`
- `KERNEL32!GetLastError` at `0x18000ae41`
- `KERNEL32!GetLastError` at `0x18000ae1a`
- `KERNEL32!GetLastError` at `0x18000ae41`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000ae62`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000ae62`
- `KERNEL32!SetLastError` at `0x18000ae73`
- `KERNEL32!SetLastError` at `0x18000ae7f`
- `KERNEL32!SetLastError` at `0x18000ae73`
- `KERNEL32!SetLastError` at `0x18000ae7f`

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
0x18000adf4  mov     [rsp+arg_8], rbx
0x18000adf9  mov     [rsp+arg_10], rbp
0x18000adfe  push    rsi
0x18000adff  push    rdi
0x18000ae00  push    r14
0x18000ae02  sub     rsp, 20h
0x18000ae06  cmp     byte ptr [rcx+41h], 0
0x18000ae0a  mov     rdi, rcx
0x18000ae0d  jnz     loc_18000AEB5
0x18000ae13  cmp     qword ptr [rcx+30h], 0
0x18000ae18  jnz     short loc_18000AE85
0x18000ae1a  call    cs:__imp_GetLastError
0x18000ae20  xor     r8d, r8d; pcbe
0x18000ae23  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ae2a  mov     rdx, rdi; pv
0x18000ae2d  mov     ebp, eax
0x18000ae2f  call    cs:__imp_CreateThreadpoolTimer
0x18000ae35  mov     rsi, [rdi+30h]
0x18000ae39  mov     r14, rax
0x18000ae3c  test    rsi, rsi
0x18000ae3f  jz      short loc_18000AE79
0x18000ae41  call    cs:__imp_GetLastError
0x18000ae47  xor     r9d, r9d; msWindowLength
0x18000ae4a  xor     r8d, r8d; msPeriod
0x18000ae4d  xor     edx, edx; pftDueTime
0x18000ae4f  mov     rcx, rsi; pti
0x18000ae52  mov     ebx, eax
0x18000ae54  call    cs:__imp_SetThreadpoolTimer
0x18000ae5a  mov     edx, 1; fCancelPendingCallbacks
0x18000ae5f  mov     rcx, rsi; pti
0x18000ae62  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ae68  mov     rcx, rsi; pti
0x18000ae6b  call    cs:__imp_CloseThreadpoolTimer
0x18000ae71  mov     ecx, ebx; dwErrCode
0x18000ae73  call    cs:__imp_SetLastError
0x18000ae79  mov     ecx, ebp; dwErrCode
0x18000ae7b  mov     [rdi+30h], r14
0x18000ae7f  call    cs:__imp_SetLastError
0x18000ae85  mov     rcx, [rdi+30h]; pti
0x18000ae89  test    rcx, rcx
0x18000ae8c  jz      short loc_18000AEB5
0x18000ae8e  mov     rax, 0FFFFFFFF4D2FA200h
0x18000ae98  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000ae9d  mov     r9d, 124F8h; msWindowLength
0x18000aea3  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000aea8  xor     r8d, r8d; msPeriod
0x18000aeab  call    cs:__imp_SetThreadpoolTimer
0x18000aeb1  mov     byte ptr [rdi+41h], 1
0x18000aeb5  mov     rbx, [rsp+38h+arg_8]
0x18000aeba  mov     rbp, [rsp+38h+arg_10]
0x18000aebf  add     rsp, 20h
0x18000aec3  pop     r14
0x18000aec5  pop     rdi
0x18000aec6  pop     rsi
0x18000aec7  retn
```
