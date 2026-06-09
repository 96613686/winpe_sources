# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180017b94`
- end: `0x180017c3c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001d1dc`

## callees

- `0x180017b94`
- `0x180021468`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017bb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017bea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017bea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017c1b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017c1b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017bd1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017bd1`

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
0x180017b94  mov     [rsp+arg_8], rbx
0x180017b99  mov     [rsp+arg_10], rsi
0x180017b9e  push    rdi
0x180017b9f  sub     rsp, 20h
0x180017ba3  cmp     byte ptr [rcx+41h], 0
0x180017ba7  lea     rsi, [rcx+30h]
0x180017bab  mov     rdi, rcx
0x180017bae  jnz     short loc_180017C2B
0x180017bb0  cmp     qword ptr [rsi], 0
0x180017bb4  jnz     short loc_180017BF6
0x180017bb6  call    cs:__imp_GetLastError
0x180017bbd  nop     dword ptr [rax+rax+00h]
0x180017bc2  xor     r8d, r8d; pcbe
0x180017bc5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017bcc  mov     rdx, rdi; pv
0x180017bcf  mov     ebx, eax
0x180017bd1  call    cs:__imp_CreateThreadpoolTimer
0x180017bd8  nop     dword ptr [rax+rax+00h]
0x180017bdd  mov     rdx, rax
0x180017be0  mov     rcx, rsi
0x180017be3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180017be8  mov     ecx, ebx; dwErrCode
0x180017bea  call    cs:__imp_SetLastError
0x180017bf1  nop     dword ptr [rax+rax+00h]
0x180017bf6  mov     rcx, [rsi]; pti
0x180017bf9  test    rcx, rcx
0x180017bfc  jz      short loc_180017C2B
0x180017bfe  mov     rax, 0FFFFFFFF4D2FA200h
0x180017c08  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180017c0d  mov     r9d, 124F8h; msWindowLength
0x180017c13  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180017c18  xor     r8d, r8d; msPeriod
0x180017c1b  call    cs:__imp_SetThreadpoolTimer
0x180017c22  nop     dword ptr [rax+rax+00h]
0x180017c27  mov     byte ptr [rdi+41h], 1
0x180017c2b  mov     rbx, [rsp+28h+arg_8]
0x180017c30  mov     rsi, [rsp+28h+arg_10]
0x180017c35  add     rsp, 20h
0x180017c39  pop     rdi
0x180017c3a  retn
```
