# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140006c2c`
- end: `0x140006d00`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400095d4`

## callees

- `0x140006c2c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140006cab`
- `KERNEL32!SetLastError` at `0x140006cb7`
- `KERNEL32!SetLastError` at `0x140006cab`
- `KERNEL32!SetLastError` at `0x140006cb7`
- `KERNEL32!SetThreadpoolTimer` at `0x140006c8c`
- `KERNEL32!SetThreadpoolTimer` at `0x140006ce3`
- `KERNEL32!SetThreadpoolTimer` at `0x140006c8c`
- `KERNEL32!SetThreadpoolTimer` at `0x140006ce3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140006c9a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140006c9a`
- `KERNEL32!CloseThreadpoolTimer` at `0x140006ca3`
- `KERNEL32!CloseThreadpoolTimer` at `0x140006ca3`
- `KERNEL32!CreateThreadpoolTimer` at `0x140006c67`
- `KERNEL32!CreateThreadpoolTimer` at `0x140006c67`
- `KERNEL32!GetLastError` at `0x140006c52`
- `KERNEL32!GetLastError` at `0x140006c79`
- `KERNEL32!GetLastError` at `0x140006c52`
- `KERNEL32!GetLastError` at `0x140006c79`

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
0x140006c2c  mov     [rsp+arg_8], rbx
0x140006c31  mov     [rsp+arg_10], rbp
0x140006c36  push    rsi
0x140006c37  push    rdi
0x140006c38  push    r14
0x140006c3a  sub     rsp, 20h
0x140006c3e  cmp     byte ptr [rcx+41h], 0
0x140006c42  mov     rdi, rcx
0x140006c45  jnz     loc_140006CED
0x140006c4b  cmp     qword ptr [rcx+30h], 0
0x140006c50  jnz     short loc_140006CBD
0x140006c52  call    cs:__imp_GetLastError
0x140006c58  xor     r8d, r8d; pcbe
0x140006c5b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140006c62  mov     rdx, rdi; pv
0x140006c65  mov     ebp, eax
0x140006c67  call    cs:__imp_CreateThreadpoolTimer
0x140006c6d  mov     rsi, [rdi+30h]
0x140006c71  mov     r14, rax
0x140006c74  test    rsi, rsi
0x140006c77  jz      short loc_140006CB1
0x140006c79  call    cs:__imp_GetLastError
0x140006c7f  xor     r9d, r9d; msWindowLength
0x140006c82  xor     r8d, r8d; msPeriod
0x140006c85  xor     edx, edx; pftDueTime
0x140006c87  mov     rcx, rsi; pti
0x140006c8a  mov     ebx, eax
0x140006c8c  call    cs:__imp_SetThreadpoolTimer
0x140006c92  mov     edx, 1; fCancelPendingCallbacks
0x140006c97  mov     rcx, rsi; pti
0x140006c9a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006ca0  mov     rcx, rsi; pti
0x140006ca3  call    cs:__imp_CloseThreadpoolTimer
0x140006ca9  mov     ecx, ebx; dwErrCode
0x140006cab  call    cs:__imp_SetLastError
0x140006cb1  mov     ecx, ebp; dwErrCode
0x140006cb3  mov     [rdi+30h], r14
0x140006cb7  call    cs:__imp_SetLastError
0x140006cbd  mov     rcx, [rdi+30h]; pti
0x140006cc1  test    rcx, rcx
0x140006cc4  jz      short loc_140006CED
0x140006cc6  mov     rax, 0FFFFFFFF4D2FA200h
0x140006cd0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140006cd5  mov     r9d, 124F8h; msWindowLength
0x140006cdb  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140006ce0  xor     r8d, r8d; msPeriod
0x140006ce3  call    cs:__imp_SetThreadpoolTimer
0x140006ce9  mov     byte ptr [rdi+41h], 1
0x140006ced  mov     rbx, [rsp+38h+arg_8]
0x140006cf2  mov     rbp, [rsp+38h+arg_10]
0x140006cf7  add     rsp, 20h
0x140006cfb  pop     r14
0x140006cfd  pop     rdi
0x140006cfe  pop     rsi
0x140006cff  retn
```
