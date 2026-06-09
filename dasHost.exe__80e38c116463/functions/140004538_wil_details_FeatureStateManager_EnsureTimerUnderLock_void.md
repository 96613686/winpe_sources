# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140004538`
- end: `0x14000460c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005cf4`

## callees

- `0x140004538`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000455e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000455e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004585`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400045b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400045c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400045b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400045c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140004573`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140004573`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004598`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400045ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004598`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400045ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400045af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400045af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400045a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400045a6`

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
0x140004538  mov     [rsp+arg_8], rbx
0x14000453d  mov     [rsp+arg_10], rbp
0x140004542  push    rsi
0x140004543  push    rdi
0x140004544  push    r14
0x140004546  sub     rsp, 20h
0x14000454a  cmp     byte ptr [rcx+41h], 0
0x14000454e  mov     rdi, rcx
0x140004551  jnz     loc_1400045F9
0x140004557  cmp     qword ptr [rcx+30h], 0
0x14000455c  jnz     short loc_1400045C9
0x14000455e  call    cs:__imp_GetLastError
0x140004564  xor     r8d, r8d; pcbe
0x140004567  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000456e  mov     rdx, rdi; pv
0x140004571  mov     ebp, eax
0x140004573  call    cs:__imp_CreateThreadpoolTimer
0x140004579  mov     rsi, [rdi+30h]
0x14000457d  mov     r14, rax
0x140004580  test    rsi, rsi
0x140004583  jz      short loc_1400045BD
0x140004585  call    cs:__imp_GetLastError
0x14000458b  xor     r9d, r9d; msWindowLength
0x14000458e  xor     r8d, r8d; msPeriod
0x140004591  xor     edx, edx; pftDueTime
0x140004593  mov     rcx, rsi; pti
0x140004596  mov     ebx, eax
0x140004598  call    cs:__imp_SetThreadpoolTimer
0x14000459e  mov     edx, 1; fCancelPendingCallbacks
0x1400045a3  mov     rcx, rsi; pti
0x1400045a6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400045ac  mov     rcx, rsi; pti
0x1400045af  call    cs:__imp_CloseThreadpoolTimer
0x1400045b5  mov     ecx, ebx; dwErrCode
0x1400045b7  call    cs:__imp_SetLastError
0x1400045bd  mov     ecx, ebp; dwErrCode
0x1400045bf  mov     [rdi+30h], r14
0x1400045c3  call    cs:__imp_SetLastError
0x1400045c9  mov     rcx, [rdi+30h]; pti
0x1400045cd  test    rcx, rcx
0x1400045d0  jz      short loc_1400045F9
0x1400045d2  mov     rax, 0FFFFFFFF4D2FA200h
0x1400045dc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1400045e1  mov     r9d, 124F8h; msWindowLength
0x1400045e7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1400045ec  xor     r8d, r8d; msPeriod
0x1400045ef  call    cs:__imp_SetThreadpoolTimer
0x1400045f5  mov     byte ptr [rdi+41h], 1
0x1400045f9  mov     rbx, [rsp+38h+arg_8]
0x1400045fe  mov     rbp, [rsp+38h+arg_10]
0x140004603  add     rsp, 20h
0x140004607  pop     r14
0x140004609  pop     rdi
0x14000460a  pop     rsi
0x14000460b  retn
```
