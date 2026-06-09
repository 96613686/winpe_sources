# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000b850`
- end: `0x18000b940`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000de34`

## callees

- `0x1800067c0`
- `0x18000b850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b8de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b8ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b8de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b8ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8ac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b89a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b89a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b8d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b8d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b8cd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b8cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b8bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b916`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b8bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b916`

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
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

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
0x18000b850  mov     [rsp+arg_8], rbx
0x18000b855  mov     [rsp+arg_10], rbp
0x18000b85a  push    rsi
0x18000b85b  push    rdi
0x18000b85c  push    r14
0x18000b85e  sub     rsp, 30h
0x18000b862  mov     rax, cs:__security_cookie
0x18000b869  xor     rax, rsp
0x18000b86c  mov     [rsp+48h+var_20], rax
0x18000b871  cmp     byte ptr [rcx+41h], 0
0x18000b875  mov     rdi, rcx
0x18000b878  jnz     loc_18000B920
0x18000b87e  cmp     qword ptr [rcx+30h], 0
0x18000b883  jnz     short loc_18000B8F0
0x18000b885  call    cs:__imp_GetLastError
0x18000b88b  xor     r8d, r8d; pcbe
0x18000b88e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b895  mov     rdx, rdi; pv
0x18000b898  mov     ebp, eax
0x18000b89a  call    cs:__imp_CreateThreadpoolTimer
0x18000b8a0  mov     rsi, [rdi+30h]
0x18000b8a4  mov     r14, rax
0x18000b8a7  test    rsi, rsi
0x18000b8aa  jz      short loc_18000B8E4
0x18000b8ac  call    cs:__imp_GetLastError
0x18000b8b2  xor     r9d, r9d; msWindowLength
0x18000b8b5  xor     r8d, r8d; msPeriod
0x18000b8b8  xor     edx, edx; pftDueTime
0x18000b8ba  mov     rcx, rsi; pti
0x18000b8bd  mov     ebx, eax
0x18000b8bf  call    cs:__imp_SetThreadpoolTimer
0x18000b8c5  mov     edx, 1; fCancelPendingCallbacks
0x18000b8ca  mov     rcx, rsi; pti
0x18000b8cd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b8d3  mov     rcx, rsi; pti
0x18000b8d6  call    cs:__imp_CloseThreadpoolTimer
0x18000b8dc  mov     ecx, ebx; dwErrCode
0x18000b8de  call    cs:__imp_SetLastError
0x18000b8e4  mov     ecx, ebp; dwErrCode
0x18000b8e6  mov     [rdi+30h], r14
0x18000b8ea  call    cs:__imp_SetLastError
0x18000b8f0  mov     rcx, [rdi+30h]; pti
0x18000b8f4  test    rcx, rcx
0x18000b8f7  jz      short loc_18000B920
0x18000b8f9  mov     rax, 0FFFFFFFF4D2FA200h
0x18000b903  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000b908  mov     r9d, 124F8h; msWindowLength
0x18000b90e  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18000b913  xor     r8d, r8d; msPeriod
0x18000b916  call    cs:__imp_SetThreadpoolTimer
0x18000b91c  mov     byte ptr [rdi+41h], 1
0x18000b920  mov     rcx, [rsp+48h+var_20]
0x18000b925  xor     rcx, rsp; StackCookie
0x18000b928  call    __security_check_cookie
0x18000b92d  mov     rbx, [rsp+48h+arg_8]
0x18000b932  mov     rbp, [rsp+48h+arg_10]
0x18000b937  add     rsp, 30h
0x18000b93b  pop     r14
0x18000b93d  pop     rdi
0x18000b93e  pop     rsi
0x18000b93f  retn
```
