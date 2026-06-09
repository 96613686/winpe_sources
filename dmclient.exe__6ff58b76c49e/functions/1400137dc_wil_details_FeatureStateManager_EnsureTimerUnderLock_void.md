# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1400137dc`
- end: `0x1400138b0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140014e18`

## callees

- `0x1400137dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013829`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001385b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013867`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001385b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013867`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001384a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001384a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001383c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013893`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001383c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013893`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013853`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013853`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140013817`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140013817`

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
0x1400137dc  mov     [rsp+arg_8], rbx
0x1400137e1  mov     [rsp+arg_10], rbp
0x1400137e6  push    rsi
0x1400137e7  push    rdi
0x1400137e8  push    r14
0x1400137ea  sub     rsp, 20h
0x1400137ee  cmp     byte ptr [rcx+41h], 0
0x1400137f2  mov     rdi, rcx
0x1400137f5  jnz     loc_14001389D
0x1400137fb  cmp     qword ptr [rcx+30h], 0
0x140013800  jnz     short loc_14001386D
0x140013802  call    cs:__imp_GetLastError
0x140013808  xor     r8d, r8d; pcbe
0x14001380b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140013812  mov     rdx, rdi; pv
0x140013815  mov     ebp, eax
0x140013817  call    cs:__imp_CreateThreadpoolTimer
0x14001381d  mov     rsi, [rdi+30h]
0x140013821  mov     r14, rax
0x140013824  test    rsi, rsi
0x140013827  jz      short loc_140013861
0x140013829  call    cs:__imp_GetLastError
0x14001382f  xor     r9d, r9d; msWindowLength
0x140013832  xor     r8d, r8d; msPeriod
0x140013835  xor     edx, edx; pftDueTime
0x140013837  mov     rcx, rsi; pti
0x14001383a  mov     ebx, eax
0x14001383c  call    cs:__imp_SetThreadpoolTimer
0x140013842  mov     edx, 1; fCancelPendingCallbacks
0x140013847  mov     rcx, rsi; pti
0x14001384a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013850  mov     rcx, rsi; pti
0x140013853  call    cs:__imp_CloseThreadpoolTimer
0x140013859  mov     ecx, ebx; dwErrCode
0x14001385b  call    cs:__imp_SetLastError
0x140013861  mov     ecx, ebp; dwErrCode
0x140013863  mov     [rdi+30h], r14
0x140013867  call    cs:__imp_SetLastError
0x14001386d  mov     rcx, [rdi+30h]; pti
0x140013871  test    rcx, rcx
0x140013874  jz      short loc_14001389D
0x140013876  mov     rax, 0FFFFFFFF4D2FA200h
0x140013880  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140013885  mov     r9d, 124F8h; msWindowLength
0x14001388b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140013890  xor     r8d, r8d; msPeriod
0x140013893  call    cs:__imp_SetThreadpoolTimer
0x140013899  mov     byte ptr [rdi+41h], 1
0x14001389d  mov     rbx, [rsp+38h+arg_8]
0x1400138a2  mov     rbp, [rsp+38h+arg_10]
0x1400138a7  add     rsp, 20h
0x1400138ab  pop     r14
0x1400138ad  pop     rdi
0x1400138ae  pop     rsi
0x1400138af  retn
```
