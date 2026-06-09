# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140004e64`
- end: `0x140004f0c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007284`

## callees

- `0x140004e64`
- `0x14000a6e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004eba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004eba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004eeb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004eeb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140004ea1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140004ea1`

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
0x140004e64  mov     [rsp+arg_8], rbx
0x140004e69  mov     [rsp+arg_10], rsi
0x140004e6e  push    rdi
0x140004e6f  sub     rsp, 20h
0x140004e73  cmp     byte ptr [rcx+41h], 0
0x140004e77  mov     rdi, rcx
0x140004e7a  jnz     short loc_140004EFB
0x140004e7c  lea     rsi, [rcx+30h]
0x140004e80  cmp     qword ptr [rsi], 0
0x140004e84  jnz     short loc_140004EC6
0x140004e86  call    cs:__imp_GetLastError
0x140004e8d  nop     dword ptr [rax+rax+00h]
0x140004e92  xor     r8d, r8d; pcbe
0x140004e95  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140004e9c  mov     rdx, rdi; pv
0x140004e9f  mov     ebx, eax
0x140004ea1  call    cs:__imp_CreateThreadpoolTimer
0x140004ea8  nop     dword ptr [rax+rax+00h]
0x140004ead  mov     rdx, rax
0x140004eb0  mov     rcx, rsi
0x140004eb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140004eb8  mov     ecx, ebx; dwErrCode
0x140004eba  call    cs:__imp_SetLastError
0x140004ec1  nop     dword ptr [rax+rax+00h]
0x140004ec6  mov     rcx, [rsi]; pti
0x140004ec9  test    rcx, rcx
0x140004ecc  jz      short loc_140004EFB
0x140004ece  mov     rax, 0FFFFFFFF4D2FA200h
0x140004ed8  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x140004edd  mov     r9d, 124F8h; msWindowLength
0x140004ee3  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x140004ee8  xor     r8d, r8d; msPeriod
0x140004eeb  call    cs:__imp_SetThreadpoolTimer
0x140004ef2  nop     dword ptr [rax+rax+00h]
0x140004ef7  mov     byte ptr [rdi+41h], 1
0x140004efb  mov     rbx, [rsp+28h+arg_8]
0x140004f00  mov     rsi, [rsp+28h+arg_10]
0x140004f05  add     rsp, 20h
0x140004f09  pop     rdi
0x140004f0a  retn
```
