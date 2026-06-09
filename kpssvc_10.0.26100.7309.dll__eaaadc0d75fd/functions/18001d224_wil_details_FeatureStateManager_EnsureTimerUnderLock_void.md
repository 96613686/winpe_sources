# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18001d224`
- end: `0x18001d2cc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180023c84`

## callees

- `0x18001d224`
- `0x1800265e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d27a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d27a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d246`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d2ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d2ab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d261`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d261`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v1; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v1 = pv + 6;
  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !*v1 )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v1,
        ThreadpoolTimer);
      SetLastError(LastError);
    }
    v5 = *v1;
    if ( *v1 )
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
0x18001d224  mov     [rsp+arg_8], rbx
0x18001d229  mov     [rsp+arg_10], rsi
0x18001d22e  push    rdi
0x18001d22f  sub     rsp, 20h
0x18001d233  cmp     byte ptr [rcx+41h], 0
0x18001d237  lea     rsi, [rcx+30h]
0x18001d23b  mov     rdi, rcx
0x18001d23e  jnz     short loc_18001D2BB
0x18001d240  cmp     qword ptr [rsi], 0
0x18001d244  jnz     short loc_18001D286
0x18001d246  call    cs:__imp_GetLastError
0x18001d24d  nop     dword ptr [rax+rax+00h]
0x18001d252  xor     r8d, r8d; pcbe
0x18001d255  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d25c  mov     rdx, rdi; pv
0x18001d25f  mov     ebx, eax
0x18001d261  call    cs:__imp_CreateThreadpoolTimer
0x18001d268  nop     dword ptr [rax+rax+00h]
0x18001d26d  mov     rdx, rax
0x18001d270  mov     rcx, rsi
0x18001d273  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001d278  mov     ecx, ebx; dwErrCode
0x18001d27a  call    cs:__imp_SetLastError
0x18001d281  nop     dword ptr [rax+rax+00h]
0x18001d286  mov     rcx, [rsi]; pti
0x18001d289  test    rcx, rcx
0x18001d28c  jz      short loc_18001D2BB
0x18001d28e  mov     rax, 0FFFFFFFF4D2FA200h
0x18001d298  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001d29d  mov     r9d, 124F8h; msWindowLength
0x18001d2a3  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18001d2a8  xor     r8d, r8d; msPeriod
0x18001d2ab  call    cs:__imp_SetThreadpoolTimer
0x18001d2b2  nop     dword ptr [rax+rax+00h]
0x18001d2b7  mov     byte ptr [rdi+41h], 1
0x18001d2bb  mov     rbx, [rsp+28h+arg_8]
0x18001d2c0  mov     rsi, [rsp+28h+arg_10]
0x18001d2c5  add     rsp, 20h
0x18001d2c9  pop     rdi
0x18001d2ca  retn
```
