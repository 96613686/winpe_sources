# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005b54`
- end: `0x180005c28`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800086f4`

## callees

- `0x180005b54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ba1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ba1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005bb4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c0b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005bb4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005bcb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005bcb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005b8f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005b8f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005bc2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005bc2`

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
0x180005b54  mov     [rsp+arg_8], rbx
0x180005b59  mov     [rsp+arg_10], rbp
0x180005b5e  push    rsi
0x180005b5f  push    rdi
0x180005b60  push    r14
0x180005b62  sub     rsp, 20h
0x180005b66  cmp     byte ptr [rcx+41h], 0
0x180005b6a  mov     rdi, rcx
0x180005b6d  jnz     loc_180005C15
0x180005b73  cmp     qword ptr [rcx+30h], 0
0x180005b78  jnz     short loc_180005BE5
0x180005b7a  call    cs:__imp_GetLastError
0x180005b80  xor     r8d, r8d; pcbe
0x180005b83  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005b8a  mov     rdx, rdi; pv
0x180005b8d  mov     ebp, eax
0x180005b8f  call    cs:__imp_CreateThreadpoolTimer
0x180005b95  mov     rsi, [rdi+30h]
0x180005b99  mov     r14, rax
0x180005b9c  test    rsi, rsi
0x180005b9f  jz      short loc_180005BD9
0x180005ba1  call    cs:__imp_GetLastError
0x180005ba7  xor     r9d, r9d; msWindowLength
0x180005baa  xor     r8d, r8d; msPeriod
0x180005bad  xor     edx, edx; pftDueTime
0x180005baf  mov     rcx, rsi; pti
0x180005bb2  mov     ebx, eax
0x180005bb4  call    cs:__imp_SetThreadpoolTimer
0x180005bba  mov     edx, 1; fCancelPendingCallbacks
0x180005bbf  mov     rcx, rsi; pti
0x180005bc2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005bc8  mov     rcx, rsi; pti
0x180005bcb  call    cs:__imp_CloseThreadpoolTimer
0x180005bd1  mov     ecx, ebx; dwErrCode
0x180005bd3  call    cs:__imp_SetLastError
0x180005bd9  mov     ecx, ebp; dwErrCode
0x180005bdb  mov     [rdi+30h], r14
0x180005bdf  call    cs:__imp_SetLastError
0x180005be5  mov     rcx, [rdi+30h]; pti
0x180005be9  test    rcx, rcx
0x180005bec  jz      short loc_180005C15
0x180005bee  mov     rax, 0FFFFFFFF4D2FA200h
0x180005bf8  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005bfd  mov     r9d, 124F8h; msWindowLength
0x180005c03  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005c08  xor     r8d, r8d; msPeriod
0x180005c0b  call    cs:__imp_SetThreadpoolTimer
0x180005c11  mov     byte ptr [rdi+41h], 1
0x180005c15  mov     rbx, [rsp+38h+arg_8]
0x180005c1a  mov     rbp, [rsp+38h+arg_10]
0x180005c1f  add     rsp, 20h
0x180005c23  pop     r14
0x180005c25  pop     rdi
0x180005c26  pop     rsi
0x180005c27  retn
```
