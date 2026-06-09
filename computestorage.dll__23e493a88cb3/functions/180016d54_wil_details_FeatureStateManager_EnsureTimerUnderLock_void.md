# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180016d54`
- end: `0x180016e18`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `196`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017d44`

## callees

- `0x180002690`
- `0x180016d54`
- `0x180019f1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016db9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d85`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016da0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016da0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016dea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016dea`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v2; // rsi
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    v2 = pv + 6;
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v2,
        ThreadpoolTimer);
      SetLastError(LastError);
    }
    v5 = *v2;
    if ( *v2 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v5, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180016d54  mov     [rsp+arg_8], rbx
0x180016d59  mov     [rsp+arg_10], rsi
0x180016d5e  push    rdi
0x180016d5f  sub     rsp, 30h
0x180016d63  mov     rax, cs:__security_cookie
0x180016d6a  xor     rax, rsp
0x180016d6d  mov     [rsp+38h+var_10], rax
0x180016d72  cmp     byte ptr [rcx+41h], 0
0x180016d76  mov     rdi, rcx
0x180016d79  jnz     short loc_180016DFA
0x180016d7b  lea     rsi, [rcx+30h]
0x180016d7f  cmp     qword ptr [rsi], 0
0x180016d83  jnz     short loc_180016DC5
0x180016d85  call    cs:__imp_GetLastError
0x180016d8c  nop     dword ptr [rax+rax+00h]
0x180016d91  xor     r8d, r8d; pcbe
0x180016d94  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180016d9b  mov     rdx, rdi; pv
0x180016d9e  mov     ebx, eax
0x180016da0  call    cs:__imp_CreateThreadpoolTimer
0x180016da7  nop     dword ptr [rax+rax+00h]
0x180016dac  mov     rdx, rax
0x180016daf  mov     rcx, rsi
0x180016db2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180016db7  mov     ecx, ebx; dwErrCode
0x180016db9  call    cs:__imp_SetLastError
0x180016dc0  nop     dword ptr [rax+rax+00h]
0x180016dc5  mov     rcx, [rsi]; pti
0x180016dc8  test    rcx, rcx
0x180016dcb  jz      short loc_180016DFA
0x180016dcd  mov     rax, 0FFFFFFFF4D2FA200h
0x180016dd7  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180016ddc  mov     r9d, 124F8h; msWindowLength
0x180016de2  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180016de7  xor     r8d, r8d; msPeriod
0x180016dea  call    cs:__imp_SetThreadpoolTimer
0x180016df1  nop     dword ptr [rax+rax+00h]
0x180016df6  mov     byte ptr [rdi+41h], 1
0x180016dfa  mov     rcx, [rsp+38h+var_10]
0x180016dff  xor     rcx, rsp; StackCookie
0x180016e02  call    __security_check_cookie
0x180016e07  mov     rbx, [rsp+38h+arg_8]
0x180016e0c  mov     rsi, [rsp+38h+arg_10]
0x180016e11  add     rsp, 30h
0x180016e15  pop     rdi
0x180016e16  retn
```
