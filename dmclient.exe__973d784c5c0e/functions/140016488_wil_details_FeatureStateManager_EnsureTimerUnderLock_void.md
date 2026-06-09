# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140016488`
- end: `0x140016530`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400170f0`

## callees

- `0x140016488`
- `0x140018a8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400164de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400164de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001650f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001650f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400164c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400164c5`

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
0x140016488  mov     [rsp+arg_8], rbx
0x14001648d  mov     [rsp+arg_10], rsi
0x140016492  push    rdi
0x140016493  sub     rsp, 20h
0x140016497  cmp     byte ptr [rcx+41h], 0
0x14001649b  mov     rdi, rcx
0x14001649e  jnz     short loc_14001651F
0x1400164a0  lea     rsi, [rcx+30h]
0x1400164a4  cmp     qword ptr [rsi], 0
0x1400164a8  jnz     short loc_1400164EA
0x1400164aa  call    cs:__imp_GetLastError
0x1400164b1  nop     dword ptr [rax+rax+00h]
0x1400164b6  xor     r8d, r8d; pcbe
0x1400164b9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400164c0  mov     rdx, rdi; pv
0x1400164c3  mov     ebx, eax
0x1400164c5  call    cs:__imp_CreateThreadpoolTimer
0x1400164cc  nop     dword ptr [rax+rax+00h]
0x1400164d1  mov     rdx, rax
0x1400164d4  mov     rcx, rsi
0x1400164d7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400164dc  mov     ecx, ebx; dwErrCode
0x1400164de  call    cs:__imp_SetLastError
0x1400164e5  nop     dword ptr [rax+rax+00h]
0x1400164ea  mov     rcx, [rsi]; pti
0x1400164ed  test    rcx, rcx
0x1400164f0  jz      short loc_14001651F
0x1400164f2  mov     rax, 0FFFFFFFF4D2FA200h
0x1400164fc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x140016501  mov     r9d, 124F8h; msWindowLength
0x140016507  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x14001650c  xor     r8d, r8d; msPeriod
0x14001650f  call    cs:__imp_SetThreadpoolTimer
0x140016516  nop     dword ptr [rax+rax+00h]
0x14001651b  mov     byte ptr [rdi+41h], 1
0x14001651f  mov     rbx, [rsp+28h+arg_8]
0x140016524  mov     rsi, [rsp+28h+arg_10]
0x140016529  add     rsp, 20h
0x14001652d  pop     rdi
0x14001652e  retn
```
