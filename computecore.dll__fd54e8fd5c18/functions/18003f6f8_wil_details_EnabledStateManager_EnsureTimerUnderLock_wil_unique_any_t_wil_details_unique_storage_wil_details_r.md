# wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18003f6f8`
- end: `0x18003f7e8`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `240`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800404c4`

## callees

- `0x1800067c0`
- `0x18003f6f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f786`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f786`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f754`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003f742`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003f742`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003f77e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003f77e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003f775`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003f775`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003f767`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003f7be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003f767`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003f7be`

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
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_, pv, 0);
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
0x18003f6f8  mov     [rsp+arg_8], rbx
0x18003f6fd  mov     [rsp+arg_10], rbp
0x18003f702  push    rsi
0x18003f703  push    rdi
0x18003f704  push    r14
0x18003f706  sub     rsp, 30h
0x18003f70a  mov     rax, cs:__security_cookie
0x18003f711  xor     rax, rsp
0x18003f714  mov     [rsp+48h+var_20], rax
0x18003f719  cmp     byte ptr [rcx+18h], 0
0x18003f71d  mov     rdi, rcx
0x18003f720  jnz     loc_18003F7C8
0x18003f726  cmp     qword ptr [rcx+10h], 0
0x18003f72b  jnz     short loc_18003F798
0x18003f72d  call    cs:__imp_GetLastError
0x18003f733  xor     r8d, r8d; pcbe
0x18003f736  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003f73d  mov     rdx, rdi; pv
0x18003f740  mov     ebp, eax
0x18003f742  call    cs:__imp_CreateThreadpoolTimer
0x18003f748  mov     rsi, [rdi+10h]
0x18003f74c  mov     r14, rax
0x18003f74f  test    rsi, rsi
0x18003f752  jz      short loc_18003F78C
0x18003f754  call    cs:__imp_GetLastError
0x18003f75a  xor     r9d, r9d; msWindowLength
0x18003f75d  xor     r8d, r8d; msPeriod
0x18003f760  xor     edx, edx; pftDueTime
0x18003f762  mov     rcx, rsi; pti
0x18003f765  mov     ebx, eax
0x18003f767  call    cs:__imp_SetThreadpoolTimer
0x18003f76d  mov     edx, 1; fCancelPendingCallbacks
0x18003f772  mov     rcx, rsi; pti
0x18003f775  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003f77b  mov     rcx, rsi; pti
0x18003f77e  call    cs:__imp_CloseThreadpoolTimer
0x18003f784  mov     ecx, ebx; dwErrCode
0x18003f786  call    cs:__imp_SetLastError
0x18003f78c  mov     ecx, ebp; dwErrCode
0x18003f78e  mov     [rdi+10h], r14
0x18003f792  call    cs:__imp_SetLastError
0x18003f798  mov     rcx, [rdi+10h]; pti
0x18003f79c  test    rcx, rcx
0x18003f79f  jz      short loc_18003F7C8
0x18003f7a1  mov     rax, 0FFFFFFFF4D2FA200h
0x18003f7ab  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18003f7b0  mov     r9d, 124F8h; msWindowLength
0x18003f7b6  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18003f7bb  xor     r8d, r8d; msPeriod
0x18003f7be  call    cs:__imp_SetThreadpoolTimer
0x18003f7c4  mov     byte ptr [rdi+18h], 1
0x18003f7c8  mov     rcx, [rsp+48h+var_20]
0x18003f7cd  xor     rcx, rsp; StackCookie
0x18003f7d0  call    __security_check_cookie
0x18003f7d5  mov     rbx, [rsp+48h+arg_8]
0x18003f7da  mov     rbp, [rsp+48h+arg_10]
0x18003f7df  add     rsp, 30h
0x18003f7e3  pop     r14
0x18003f7e5  pop     rdi
0x18003f7e6  pop     rsi
0x18003f7e7  retn
```
