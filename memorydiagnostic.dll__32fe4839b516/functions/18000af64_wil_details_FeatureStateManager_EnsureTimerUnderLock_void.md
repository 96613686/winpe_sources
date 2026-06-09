# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000af64`
- end: `0x18000b00c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000fb84`

## callees

- `0x18000af64`
- `0x180018824`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18000afa1`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000afa1`
- `KERNEL32!SetThreadpoolTimer` at `0x18000afeb`
- `KERNEL32!SetThreadpoolTimer` at `0x18000afeb`
- `KERNEL32!GetLastError` at `0x18000af86`
- `KERNEL32!GetLastError` at `0x18000af86`
- `KERNEL32!SetLastError` at `0x18000afba`
- `KERNEL32!SetLastError` at `0x18000afba`

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
0x18000af64  mov     [rsp+arg_8], rbx
0x18000af69  mov     [rsp+arg_10], rsi
0x18000af6e  push    rdi
0x18000af6f  sub     rsp, 20h
0x18000af73  cmp     byte ptr [rcx+41h], 0
0x18000af77  lea     rsi, [rcx+30h]
0x18000af7b  mov     rdi, rcx
0x18000af7e  jnz     short loc_18000AFFB
0x18000af80  cmp     qword ptr [rsi], 0
0x18000af84  jnz     short loc_18000AFC6
0x18000af86  call    cs:__imp_GetLastError
0x18000af8d  nop     dword ptr [rax+rax+00h]
0x18000af92  xor     r8d, r8d; pcbe
0x18000af95  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000af9c  mov     rdx, rdi; pv
0x18000af9f  mov     ebx, eax
0x18000afa1  call    cs:__imp_CreateThreadpoolTimer
0x18000afa8  nop     dword ptr [rax+rax+00h]
0x18000afad  mov     rdx, rax
0x18000afb0  mov     rcx, rsi
0x18000afb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000afb8  mov     ecx, ebx; dwErrCode
0x18000afba  call    cs:__imp_SetLastError
0x18000afc1  nop     dword ptr [rax+rax+00h]
0x18000afc6  mov     rcx, [rsi]; pti
0x18000afc9  test    rcx, rcx
0x18000afcc  jz      short loc_18000AFFB
0x18000afce  mov     rax, 0FFFFFFFF4D2FA200h
0x18000afd8  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000afdd  mov     r9d, 124F8h; msWindowLength
0x18000afe3  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000afe8  xor     r8d, r8d; msPeriod
0x18000afeb  call    cs:__imp_SetThreadpoolTimer
0x18000aff2  nop     dword ptr [rax+rax+00h]
0x18000aff7  mov     byte ptr [rdi+41h], 1
0x18000affb  mov     rbx, [rsp+28h+arg_8]
0x18000b000  mov     rsi, [rsp+28h+arg_10]
0x18000b005  add     rsp, 20h
0x18000b009  pop     rdi
0x18000b00a  retn
```
