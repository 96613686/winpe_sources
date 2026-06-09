# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800135f8`
- end: `0x1800136cc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001baa4`

## callees

- `0x1800135f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013677`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013683`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013677`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001361e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001361e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013645`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013658`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800136af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013658`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800136af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001366f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001366f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013633`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013633`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013666`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013666`

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
0x1800135f8  mov     [rsp+arg_8], rbx
0x1800135fd  mov     [rsp+arg_10], rbp
0x180013602  push    rsi
0x180013603  push    rdi
0x180013604  push    r14
0x180013606  sub     rsp, 20h
0x18001360a  cmp     byte ptr [rcx+41h], 0
0x18001360e  mov     rdi, rcx
0x180013611  jnz     loc_1800136B9
0x180013617  cmp     qword ptr [rcx+30h], 0
0x18001361c  jnz     short loc_180013689
0x18001361e  call    cs:__imp_GetLastError
0x180013624  xor     r8d, r8d; pcbe
0x180013627  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001362e  mov     rdx, rdi; pv
0x180013631  mov     ebp, eax
0x180013633  call    cs:__imp_CreateThreadpoolTimer
0x180013639  mov     rsi, [rdi+30h]
0x18001363d  mov     r14, rax
0x180013640  test    rsi, rsi
0x180013643  jz      short loc_18001367D
0x180013645  call    cs:__imp_GetLastError
0x18001364b  xor     r9d, r9d; msWindowLength
0x18001364e  xor     r8d, r8d; msPeriod
0x180013651  xor     edx, edx; pftDueTime
0x180013653  mov     rcx, rsi; pti
0x180013656  mov     ebx, eax
0x180013658  call    cs:__imp_SetThreadpoolTimer
0x18001365e  mov     edx, 1; fCancelPendingCallbacks
0x180013663  mov     rcx, rsi; pti
0x180013666  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001366c  mov     rcx, rsi; pti
0x18001366f  call    cs:__imp_CloseThreadpoolTimer
0x180013675  mov     ecx, ebx; dwErrCode
0x180013677  call    cs:__imp_SetLastError
0x18001367d  mov     ecx, ebp; dwErrCode
0x18001367f  mov     [rdi+30h], r14
0x180013683  call    cs:__imp_SetLastError
0x180013689  mov     rcx, [rdi+30h]; pti
0x18001368d  test    rcx, rcx
0x180013690  jz      short loc_1800136B9
0x180013692  mov     rax, 0FFFFFFFF4D2FA200h
0x18001369c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800136a1  mov     r9d, 124F8h; msWindowLength
0x1800136a7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800136ac  xor     r8d, r8d; msPeriod
0x1800136af  call    cs:__imp_SetThreadpoolTimer
0x1800136b5  mov     byte ptr [rdi+41h], 1
0x1800136b9  mov     rbx, [rsp+38h+arg_8]
0x1800136be  mov     rbp, [rsp+38h+arg_10]
0x1800136c3  add     rsp, 20h
0x1800136c7  pop     r14
0x1800136c9  pop     rdi
0x1800136ca  pop     rsi
0x1800136cb  retn
```
