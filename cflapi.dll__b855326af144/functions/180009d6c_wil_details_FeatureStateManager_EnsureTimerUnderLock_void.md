# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180009d6c`
- end: `0x180009e40`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b40c`

## callees

- `0x180009d6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009db9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009deb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009df7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009deb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009df7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009dda`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009dda`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009de3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009de3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009dcc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009e23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009dcc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009e23`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009da7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009da7`

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
0x180009d6c  mov     [rsp+arg_8], rbx
0x180009d71  mov     [rsp+arg_10], rbp
0x180009d76  push    rsi
0x180009d77  push    rdi
0x180009d78  push    r14
0x180009d7a  sub     rsp, 20h
0x180009d7e  cmp     byte ptr [rcx+41h], 0
0x180009d82  mov     rdi, rcx
0x180009d85  jnz     loc_180009E2D
0x180009d8b  cmp     qword ptr [rcx+30h], 0
0x180009d90  jnz     short loc_180009DFD
0x180009d92  call    cs:__imp_GetLastError
0x180009d98  xor     r8d, r8d; pcbe
0x180009d9b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009da2  mov     rdx, rdi; pv
0x180009da5  mov     ebp, eax
0x180009da7  call    cs:__imp_CreateThreadpoolTimer
0x180009dad  mov     rsi, [rdi+30h]
0x180009db1  mov     r14, rax
0x180009db4  test    rsi, rsi
0x180009db7  jz      short loc_180009DF1
0x180009db9  call    cs:__imp_GetLastError
0x180009dbf  xor     r9d, r9d; msWindowLength
0x180009dc2  xor     r8d, r8d; msPeriod
0x180009dc5  xor     edx, edx; pftDueTime
0x180009dc7  mov     rcx, rsi; pti
0x180009dca  mov     ebx, eax
0x180009dcc  call    cs:__imp_SetThreadpoolTimer
0x180009dd2  mov     edx, 1; fCancelPendingCallbacks
0x180009dd7  mov     rcx, rsi; pti
0x180009dda  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009de0  mov     rcx, rsi; pti
0x180009de3  call    cs:__imp_CloseThreadpoolTimer
0x180009de9  mov     ecx, ebx; dwErrCode
0x180009deb  call    cs:__imp_SetLastError
0x180009df1  mov     ecx, ebp; dwErrCode
0x180009df3  mov     [rdi+30h], r14
0x180009df7  call    cs:__imp_SetLastError
0x180009dfd  mov     rcx, [rdi+30h]; pti
0x180009e01  test    rcx, rcx
0x180009e04  jz      short loc_180009E2D
0x180009e06  mov     rax, 0FFFFFFFF4D2FA200h
0x180009e10  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180009e15  mov     r9d, 124F8h; msWindowLength
0x180009e1b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180009e20  xor     r8d, r8d; msPeriod
0x180009e23  call    cs:__imp_SetThreadpoolTimer
0x180009e29  mov     byte ptr [rdi+41h], 1
0x180009e2d  mov     rbx, [rsp+38h+arg_8]
0x180009e32  mov     rbp, [rsp+38h+arg_10]
0x180009e37  add     rsp, 20h
0x180009e3b  pop     r14
0x180009e3d  pop     rdi
0x180009e3e  pop     rsi
0x180009e3f  retn
```
