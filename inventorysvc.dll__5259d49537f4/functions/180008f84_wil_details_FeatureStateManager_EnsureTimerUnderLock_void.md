# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180008f84`
- end: `0x180009058`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000da24`

## callees

- `0x180008f84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009003`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000900f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009003`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000900f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008fe4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000903b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008fe4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000903b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008fbf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008fbf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ffb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ffb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008ff2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008ff2`

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
0x180008f84  mov     [rsp+arg_8], rbx
0x180008f89  mov     [rsp+arg_10], rbp
0x180008f8e  push    rsi
0x180008f8f  push    rdi
0x180008f90  push    r14
0x180008f92  sub     rsp, 20h
0x180008f96  cmp     byte ptr [rcx+41h], 0
0x180008f9a  mov     rdi, rcx
0x180008f9d  jnz     loc_180009045
0x180008fa3  cmp     qword ptr [rcx+30h], 0
0x180008fa8  jnz     short loc_180009015
0x180008faa  call    cs:__imp_GetLastError
0x180008fb0  xor     r8d, r8d; pcbe
0x180008fb3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008fba  mov     rdx, rdi; pv
0x180008fbd  mov     ebp, eax
0x180008fbf  call    cs:__imp_CreateThreadpoolTimer
0x180008fc5  mov     rsi, [rdi+30h]
0x180008fc9  mov     r14, rax
0x180008fcc  test    rsi, rsi
0x180008fcf  jz      short loc_180009009
0x180008fd1  call    cs:__imp_GetLastError
0x180008fd7  xor     r9d, r9d; msWindowLength
0x180008fda  xor     r8d, r8d; msPeriod
0x180008fdd  xor     edx, edx; pftDueTime
0x180008fdf  mov     rcx, rsi; pti
0x180008fe2  mov     ebx, eax
0x180008fe4  call    cs:__imp_SetThreadpoolTimer
0x180008fea  mov     edx, 1; fCancelPendingCallbacks
0x180008fef  mov     rcx, rsi; pti
0x180008ff2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008ff8  mov     rcx, rsi; pti
0x180008ffb  call    cs:__imp_CloseThreadpoolTimer
0x180009001  mov     ecx, ebx; dwErrCode
0x180009003  call    cs:__imp_SetLastError
0x180009009  mov     ecx, ebp; dwErrCode
0x18000900b  mov     [rdi+30h], r14
0x18000900f  call    cs:__imp_SetLastError
0x180009015  mov     rcx, [rdi+30h]; pti
0x180009019  test    rcx, rcx
0x18000901c  jz      short loc_180009045
0x18000901e  mov     rax, 0FFFFFFFF4D2FA200h
0x180009028  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000902d  mov     r9d, 124F8h; msWindowLength
0x180009033  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180009038  xor     r8d, r8d; msPeriod
0x18000903b  call    cs:__imp_SetThreadpoolTimer
0x180009041  mov     byte ptr [rdi+41h], 1
0x180009045  mov     rbx, [rsp+38h+arg_8]
0x18000904a  mov     rbp, [rsp+38h+arg_10]
0x18000904f  add     rsp, 20h
0x180009053  pop     r14
0x180009055  pop     rdi
0x180009056  pop     rsi
0x180009057  retn
```
