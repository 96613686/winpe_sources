# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x180025b3c`
- end: `0x180025c2c`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025c88`

## callees

- `0x180025b3c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bd6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025bc2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025bc2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025bb9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025bb9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025bab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025c02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025bab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025c02`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025b86`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025b86`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 24) )
  {
    if ( !pv[2] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
      v4 = pv[2];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[2] = v5;
      SetLastError(LastError);
    }
    v7 = pv[2];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 24) = 1;
    }
  }
}

```

## disassembly

```asm
0x180025b3c  mov     [rsp+arg_8], rbx
0x180025b41  mov     [rsp+arg_10], rbp
0x180025b46  push    rsi
0x180025b47  push    rdi
0x180025b48  push    r14
0x180025b4a  sub     rsp, 30h
0x180025b4e  mov     rax, cs:__security_cookie
0x180025b55  xor     rax, rsp
0x180025b58  mov     [rsp+48h+var_20], rax
0x180025b5d  cmp     byte ptr [rcx+18h], 0
0x180025b61  mov     rdi, rcx
0x180025b64  jnz     loc_180025C0C
0x180025b6a  cmp     qword ptr [rcx+10h], 0
0x180025b6f  jnz     short loc_180025BDC
0x180025b71  call    cs:__imp_GetLastError
0x180025b77  xor     r8d, r8d; pcbe
0x180025b7a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180025b81  mov     rdx, rdi; pv
0x180025b84  mov     ebp, eax
0x180025b86  call    cs:__imp_CreateThreadpoolTimer
0x180025b8c  mov     rsi, [rdi+10h]
0x180025b90  mov     r14, rax
0x180025b93  test    rsi, rsi
0x180025b96  jz      short loc_180025BD0
0x180025b98  call    cs:__imp_GetLastError
0x180025b9e  xor     r9d, r9d; msWindowLength
0x180025ba1  xor     r8d, r8d; msPeriod
0x180025ba4  xor     edx, edx; pftDueTime
0x180025ba6  mov     rcx, rsi; pti
0x180025ba9  mov     ebx, eax
0x180025bab  call    cs:__imp_SetThreadpoolTimer
0x180025bb1  mov     edx, 1; fCancelPendingCallbacks
0x180025bb6  mov     rcx, rsi; pti
0x180025bb9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180025bbf  mov     rcx, rsi; pti
0x180025bc2  call    cs:__imp_CloseThreadpoolTimer
0x180025bc8  mov     ecx, ebx; dwErrCode
0x180025bca  call    cs:__imp_SetLastError
0x180025bd0  mov     ecx, ebp; dwErrCode
0x180025bd2  mov     [rdi+10h], r14
0x180025bd6  call    cs:__imp_SetLastError
0x180025bdc  mov     rcx, [rdi+10h]; pti
0x180025be0  test    rcx, rcx
0x180025be3  jz      short loc_180025C0C
0x180025be5  mov     rax, 0FFFFFFFF4D2FA200h
0x180025bef  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180025bf4  mov     r9d, 124F8h; msWindowLength
0x180025bfa  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180025bff  xor     r8d, r8d; msPeriod
0x180025c02  call    cs:__imp_SetThreadpoolTimer
0x180025c08  mov     byte ptr [rdi+18h], 1
0x180025c0c  mov     rcx, [rsp+48h+var_20]
0x180025c11  xor     rcx, rsp; StackCookie
0x180025c14  call    __security_check_cookie
0x180025c19  mov     rbx, [rsp+48h+arg_8]
0x180025c1e  mov     rbp, [rsp+48h+arg_10]
0x180025c23  add     rsp, 30h
0x180025c27  pop     r14
0x180025c29  pop     rdi
0x180025c2a  pop     rsi
0x180025c2b  retn
```
