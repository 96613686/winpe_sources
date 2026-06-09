# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800b6a08`
- end: `0x1800b6ab0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800bb4f4`

## callees

- `0x1800b6a08`
- `0x1800be088`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6a2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b6a5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b6a5e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b6a8f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b6a8f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b6a45`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b6a45`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

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
0x1800b6a08  mov     [rsp+arg_8], rbx
0x1800b6a0d  mov     [rsp+arg_10], rsi
0x1800b6a12  push    rdi
0x1800b6a13  sub     rsp, 20h
0x1800b6a17  cmp     byte ptr [rcx+41h], 0
0x1800b6a1b  mov     rdi, rcx
0x1800b6a1e  jnz     short loc_1800B6A9F
0x1800b6a20  lea     rsi, [rcx+30h]
0x1800b6a24  cmp     qword ptr [rsi], 0
0x1800b6a28  jnz     short loc_1800B6A6A
0x1800b6a2a  call    cs:__imp_GetLastError
0x1800b6a31  nop     dword ptr [rax+rax+00h]
0x1800b6a36  xor     r8d, r8d; pcbe
0x1800b6a39  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800b6a40  mov     rdx, rdi; pv
0x1800b6a43  mov     ebx, eax
0x1800b6a45  call    cs:__imp_CreateThreadpoolTimer
0x1800b6a4c  nop     dword ptr [rax+rax+00h]
0x1800b6a51  mov     rdx, rax
0x1800b6a54  mov     rcx, rsi
0x1800b6a57  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800b6a5c  mov     ecx, ebx; dwErrCode
0x1800b6a5e  call    cs:__imp_SetLastError
0x1800b6a65  nop     dword ptr [rax+rax+00h]
0x1800b6a6a  mov     rcx, [rsi]; pti
0x1800b6a6d  test    rcx, rcx
0x1800b6a70  jz      short loc_1800B6A9F
0x1800b6a72  mov     rax, 0FFFFFFFF4D2FA200h
0x1800b6a7c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800b6a81  mov     r9d, 124F8h; msWindowLength
0x1800b6a87  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x1800b6a8c  xor     r8d, r8d; msPeriod
0x1800b6a8f  call    cs:__imp_SetThreadpoolTimer
0x1800b6a96  nop     dword ptr [rax+rax+00h]
0x1800b6a9b  mov     byte ptr [rdi+41h], 1
0x1800b6a9f  mov     rbx, [rsp+28h+arg_8]
0x1800b6aa4  mov     rsi, [rsp+28h+arg_10]
0x1800b6aa9  add     rsp, 20h
0x1800b6aad  pop     rdi
0x1800b6aae  retn
```
