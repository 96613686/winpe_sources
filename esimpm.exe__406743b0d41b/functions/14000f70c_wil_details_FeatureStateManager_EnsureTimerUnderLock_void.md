# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14000f70c`
- end: `0x14000f7e0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011524`

## callees

- `0x14000f70c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f78b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f797`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f78b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f797`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000f747`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000f747`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000f783`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000f783`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000f77a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000f77a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000f76c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000f7c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000f76c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000f7c3`

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
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
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
0x14000f70c  mov     [rsp+arg_8], rbx
0x14000f711  mov     [rsp+arg_10], rbp
0x14000f716  push    rsi
0x14000f717  push    rdi
0x14000f718  push    r14
0x14000f71a  sub     rsp, 20h
0x14000f71e  cmp     byte ptr [rcx+41h], 0
0x14000f722  mov     rdi, rcx
0x14000f725  jnz     loc_14000F7CD
0x14000f72b  cmp     qword ptr [rcx+30h], 0
0x14000f730  jnz     short loc_14000F79D
0x14000f732  call    cs:__imp_GetLastError
0x14000f738  xor     r8d, r8d; pcbe
0x14000f73b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000f742  mov     rdx, rdi; pv
0x14000f745  mov     ebp, eax
0x14000f747  call    cs:__imp_CreateThreadpoolTimer
0x14000f74d  mov     rsi, [rdi+30h]
0x14000f751  mov     r14, rax
0x14000f754  test    rsi, rsi
0x14000f757  jz      short loc_14000F791
0x14000f759  call    cs:__imp_GetLastError
0x14000f75f  xor     r9d, r9d; msWindowLength
0x14000f762  xor     r8d, r8d; msPeriod
0x14000f765  xor     edx, edx; pftDueTime
0x14000f767  mov     rcx, rsi; pti
0x14000f76a  mov     ebx, eax
0x14000f76c  call    cs:__imp_SetThreadpoolTimer
0x14000f772  mov     edx, 1; fCancelPendingCallbacks
0x14000f777  mov     rcx, rsi; pti
0x14000f77a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000f780  mov     rcx, rsi; pti
0x14000f783  call    cs:__imp_CloseThreadpoolTimer
0x14000f789  mov     ecx, ebx; dwErrCode
0x14000f78b  call    cs:__imp_SetLastError
0x14000f791  mov     ecx, ebp; dwErrCode
0x14000f793  mov     [rdi+30h], r14
0x14000f797  call    cs:__imp_SetLastError
0x14000f79d  mov     rcx, [rdi+30h]; pti
0x14000f7a1  test    rcx, rcx
0x14000f7a4  jz      short loc_14000F7CD
0x14000f7a6  mov     rax, 0FFFFFFFF4D2FA200h
0x14000f7b0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x14000f7b5  mov     r9d, 124F8h; msWindowLength
0x14000f7bb  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x14000f7c0  xor     r8d, r8d; msPeriod
0x14000f7c3  call    cs:__imp_SetThreadpoolTimer
0x14000f7c9  mov     byte ptr [rdi+41h], 1
0x14000f7cd  mov     rbx, [rsp+38h+arg_8]
0x14000f7d2  mov     rbp, [rsp+38h+arg_10]
0x14000f7d7  add     rsp, 20h
0x14000f7db  pop     r14
0x14000f7dd  pop     rdi
0x14000f7de  pop     rsi
0x14000f7df  retn
```
