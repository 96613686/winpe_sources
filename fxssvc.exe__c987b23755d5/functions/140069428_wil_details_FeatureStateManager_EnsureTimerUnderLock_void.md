# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140069428`
- end: `0x1400694fc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14006b0a4`

## callees

- `0x140069428`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x140069463`
- `KERNEL32!CreateThreadpoolTimer` at `0x140069463`
- `KERNEL32!SetThreadpoolTimer` at `0x140069488`
- `KERNEL32!SetThreadpoolTimer` at `0x1400694df`
- `KERNEL32!SetThreadpoolTimer` at `0x140069488`
- `KERNEL32!SetThreadpoolTimer` at `0x1400694df`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006949f`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006949f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140069496`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140069496`
- `KERNEL32!GetLastError` at `0x14006944e`
- `KERNEL32!GetLastError` at `0x140069475`
- `KERNEL32!GetLastError` at `0x14006944e`
- `KERNEL32!GetLastError` at `0x140069475`
- `KERNEL32!SetLastError` at `0x1400694a7`
- `KERNEL32!SetLastError` at `0x1400694b3`
- `KERNEL32!SetLastError` at `0x1400694a7`
- `KERNEL32!SetLastError` at `0x1400694b3`

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
0x140069428  mov     [rsp+arg_8], rbx
0x14006942d  mov     [rsp+arg_10], rbp
0x140069432  push    rsi
0x140069433  push    rdi
0x140069434  push    r14
0x140069436  sub     rsp, 20h
0x14006943a  cmp     byte ptr [rcx+41h], 0
0x14006943e  mov     rdi, rcx
0x140069441  jnz     loc_1400694E9
0x140069447  cmp     qword ptr [rcx+30h], 0
0x14006944c  jnz     short loc_1400694B9
0x14006944e  call    cs:__imp_GetLastError
0x140069454  xor     r8d, r8d; pcbe
0x140069457  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14006945e  mov     rdx, rdi; pv
0x140069461  mov     ebp, eax
0x140069463  call    cs:__imp_CreateThreadpoolTimer
0x140069469  mov     rsi, [rdi+30h]
0x14006946d  mov     r14, rax
0x140069470  test    rsi, rsi
0x140069473  jz      short loc_1400694AD
0x140069475  call    cs:__imp_GetLastError
0x14006947b  xor     r9d, r9d; msWindowLength
0x14006947e  xor     r8d, r8d; msPeriod
0x140069481  xor     edx, edx; pftDueTime
0x140069483  mov     rcx, rsi; pti
0x140069486  mov     ebx, eax
0x140069488  call    cs:__imp_SetThreadpoolTimer
0x14006948e  mov     edx, 1; fCancelPendingCallbacks
0x140069493  mov     rcx, rsi; pti
0x140069496  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14006949c  mov     rcx, rsi; pti
0x14006949f  call    cs:__imp_CloseThreadpoolTimer
0x1400694a5  mov     ecx, ebx; dwErrCode
0x1400694a7  call    cs:__imp_SetLastError
0x1400694ad  mov     ecx, ebp; dwErrCode
0x1400694af  mov     [rdi+30h], r14
0x1400694b3  call    cs:__imp_SetLastError
0x1400694b9  mov     rcx, [rdi+30h]; pti
0x1400694bd  test    rcx, rcx
0x1400694c0  jz      short loc_1400694E9
0x1400694c2  mov     rax, 0FFFFFFFF4D2FA200h
0x1400694cc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1400694d1  mov     r9d, 124F8h; msWindowLength
0x1400694d7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1400694dc  xor     r8d, r8d; msPeriod
0x1400694df  call    cs:__imp_SetThreadpoolTimer
0x1400694e5  mov     byte ptr [rdi+41h], 1
0x1400694e9  mov     rbx, [rsp+38h+arg_8]
0x1400694ee  mov     rbp, [rsp+38h+arg_10]
0x1400694f3  add     rsp, 20h
0x1400694f7  pop     r14
0x1400694f9  pop     rdi
0x1400694fa  pop     rsi
0x1400694fb  retn
```
