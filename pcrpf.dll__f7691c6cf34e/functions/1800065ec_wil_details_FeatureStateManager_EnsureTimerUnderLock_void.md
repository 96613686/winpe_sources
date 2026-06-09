# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800065ec`
- end: `0x180006694`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008824`

## callees

- `0x1800065ec`
- `0x18000b8a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006642`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000660e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000660e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006629`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006629`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006673`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006673`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v2; // rsi
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
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
0x1800065ec  mov     [rsp+arg_8], rbx
0x1800065f1  mov     [rsp+arg_10], rsi
0x1800065f6  push    rdi
0x1800065f7  sub     rsp, 20h
0x1800065fb  cmp     byte ptr [rcx+41h], 0
0x1800065ff  mov     rdi, rcx
0x180006602  jnz     short loc_180006683
0x180006604  lea     rsi, [rcx+30h]
0x180006608  cmp     qword ptr [rsi], 0
0x18000660c  jnz     short loc_18000664E
0x18000660e  call    cs:__imp_GetLastError
0x180006615  nop     dword ptr [rax+rax+00h]
0x18000661a  xor     r8d, r8d; pcbe
0x18000661d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006624  mov     rdx, rdi; pv
0x180006627  mov     ebx, eax
0x180006629  call    cs:__imp_CreateThreadpoolTimer
0x180006630  nop     dword ptr [rax+rax+00h]
0x180006635  mov     rdx, rax
0x180006638  mov     rcx, rsi
0x18000663b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006640  mov     ecx, ebx; dwErrCode
0x180006642  call    cs:__imp_SetLastError
0x180006649  nop     dword ptr [rax+rax+00h]
0x18000664e  mov     rcx, [rsi]; pti
0x180006651  test    rcx, rcx
0x180006654  jz      short loc_180006683
0x180006656  mov     rax, 0FFFFFFFF4D2FA200h
0x180006660  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180006665  mov     r9d, 124F8h; msWindowLength
0x18000666b  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180006670  xor     r8d, r8d; msPeriod
0x180006673  call    cs:__imp_SetThreadpoolTimer
0x18000667a  nop     dword ptr [rax+rax+00h]
0x18000667f  mov     byte ptr [rdi+41h], 1
0x180006683  mov     rbx, [rsp+28h+arg_8]
0x180006688  mov     rsi, [rsp+28h+arg_10]
0x18000668d  add     rsp, 20h
0x180006691  pop     rdi
0x180006692  retn
```
