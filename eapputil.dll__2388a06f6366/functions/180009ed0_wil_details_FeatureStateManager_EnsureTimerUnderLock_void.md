# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180009ed0`
- end: `0x180009fa4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000accc`

## callees

- `0x180009ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f1d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009f0b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009f0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009f47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009f47`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f87`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f87`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009f3e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009f3e`

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
0x180009ed0  mov     [rsp+arg_8], rbx
0x180009ed5  mov     [rsp+arg_10], rbp
0x180009eda  push    rsi
0x180009edb  push    rdi
0x180009edc  push    r14
0x180009ede  sub     rsp, 20h
0x180009ee2  cmp     byte ptr [rcx+41h], 0
0x180009ee6  mov     rdi, rcx
0x180009ee9  jnz     loc_180009F91
0x180009eef  cmp     qword ptr [rcx+30h], 0
0x180009ef4  jnz     short loc_180009F61
0x180009ef6  call    cs:__imp_GetLastError
0x180009efc  xor     r8d, r8d; pcbe
0x180009eff  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009f06  mov     rdx, rdi; pv
0x180009f09  mov     ebp, eax
0x180009f0b  call    cs:__imp_CreateThreadpoolTimer
0x180009f11  mov     rsi, [rdi+30h]
0x180009f15  mov     r14, rax
0x180009f18  test    rsi, rsi
0x180009f1b  jz      short loc_180009F55
0x180009f1d  call    cs:__imp_GetLastError
0x180009f23  xor     r9d, r9d; msWindowLength
0x180009f26  xor     r8d, r8d; msPeriod
0x180009f29  xor     edx, edx; pftDueTime
0x180009f2b  mov     rcx, rsi; pti
0x180009f2e  mov     ebx, eax
0x180009f30  call    cs:__imp_SetThreadpoolTimer
0x180009f36  mov     edx, 1; fCancelPendingCallbacks
0x180009f3b  mov     rcx, rsi; pti
0x180009f3e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009f44  mov     rcx, rsi; pti
0x180009f47  call    cs:__imp_CloseThreadpoolTimer
0x180009f4d  mov     ecx, ebx; dwErrCode
0x180009f4f  call    cs:__imp_SetLastError
0x180009f55  mov     ecx, ebp; dwErrCode
0x180009f57  mov     [rdi+30h], r14
0x180009f5b  call    cs:__imp_SetLastError
0x180009f61  mov     rcx, [rdi+30h]; pti
0x180009f65  test    rcx, rcx
0x180009f68  jz      short loc_180009F91
0x180009f6a  mov     rax, 0FFFFFFFF4D2FA200h
0x180009f74  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180009f79  mov     r9d, 124F8h; msWindowLength
0x180009f7f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180009f84  xor     r8d, r8d; msPeriod
0x180009f87  call    cs:__imp_SetThreadpoolTimer
0x180009f8d  mov     byte ptr [rdi+41h], 1
0x180009f91  mov     rbx, [rsp+38h+arg_8]
0x180009f96  mov     rbp, [rsp+38h+arg_10]
0x180009f9b  add     rsp, 20h
0x180009f9f  pop     r14
0x180009fa1  pop     rdi
0x180009fa2  pop     rsi
0x180009fa3  retn
```
