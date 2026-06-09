# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000beb4`
- end: `0x18000bf5c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010900`

## callees

- `0x18000beb4`
- `0x1800142b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bed6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bef1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bef1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bf3b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bf3b`

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
0x18000beb4  mov     [rsp+arg_8], rbx
0x18000beb9  mov     [rsp+arg_10], rsi
0x18000bebe  push    rdi
0x18000bebf  sub     rsp, 20h
0x18000bec3  cmp     byte ptr [rcx+41h], 0
0x18000bec7  mov     rdi, rcx
0x18000beca  jnz     short loc_18000BF4B
0x18000becc  lea     rsi, [rcx+30h]
0x18000bed0  cmp     qword ptr [rsi], 0
0x18000bed4  jnz     short loc_18000BF16
0x18000bed6  call    cs:__imp_GetLastError
0x18000bedd  nop     dword ptr [rax+rax+00h]
0x18000bee2  xor     r8d, r8d; pcbe
0x18000bee5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000beec  mov     rdx, rdi; pv
0x18000beef  mov     ebx, eax
0x18000bef1  call    cs:__imp_CreateThreadpoolTimer
0x18000bef8  nop     dword ptr [rax+rax+00h]
0x18000befd  mov     rdx, rax
0x18000bf00  mov     rcx, rsi
0x18000bf03  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000bf08  mov     ecx, ebx; dwErrCode
0x18000bf0a  call    cs:__imp_SetLastError
0x18000bf11  nop     dword ptr [rax+rax+00h]
0x18000bf16  mov     rcx, [rsi]; pti
0x18000bf19  test    rcx, rcx
0x18000bf1c  jz      short loc_18000BF4B
0x18000bf1e  mov     rax, 0FFFFFFFF4D2FA200h
0x18000bf28  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000bf2d  mov     r9d, 124F8h; msWindowLength
0x18000bf33  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000bf38  xor     r8d, r8d; msPeriod
0x18000bf3b  call    cs:__imp_SetThreadpoolTimer
0x18000bf42  nop     dword ptr [rax+rax+00h]
0x18000bf47  mov     byte ptr [rdi+41h], 1
0x18000bf4b  mov     rbx, [rsp+28h+arg_8]
0x18000bf50  mov     rsi, [rsp+28h+arg_10]
0x18000bf55  add     rsp, 20h
0x18000bf59  pop     rdi
0x18000bf5a  retn
```
