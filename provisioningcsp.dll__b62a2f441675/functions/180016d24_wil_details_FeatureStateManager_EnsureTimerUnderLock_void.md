# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180016d24`
- end: `0x180016dcc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180020fd8`

## callees

- `0x180016d24`
- `0x180022a84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016d7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016d7a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016d61`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016d61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016dab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016dab`

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
0x180016d24  mov     [rsp+arg_8], rbx
0x180016d29  mov     [rsp+arg_10], rsi
0x180016d2e  push    rdi
0x180016d2f  sub     rsp, 20h
0x180016d33  cmp     byte ptr [rcx+41h], 0
0x180016d37  mov     rdi, rcx
0x180016d3a  jnz     short loc_180016DBB
0x180016d3c  lea     rsi, [rcx+30h]
0x180016d40  cmp     qword ptr [rsi], 0
0x180016d44  jnz     short loc_180016D86
0x180016d46  call    cs:__imp_GetLastError
0x180016d4d  nop     dword ptr [rax+rax+00h]
0x180016d52  xor     r8d, r8d; pcbe
0x180016d55  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180016d5c  mov     rdx, rdi; pv
0x180016d5f  mov     ebx, eax
0x180016d61  call    cs:__imp_CreateThreadpoolTimer
0x180016d68  nop     dword ptr [rax+rax+00h]
0x180016d6d  mov     rdx, rax
0x180016d70  mov     rcx, rsi
0x180016d73  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180016d78  mov     ecx, ebx; dwErrCode
0x180016d7a  call    cs:__imp_SetLastError
0x180016d81  nop     dword ptr [rax+rax+00h]
0x180016d86  mov     rcx, [rsi]; pti
0x180016d89  test    rcx, rcx
0x180016d8c  jz      short loc_180016DBB
0x180016d8e  mov     rax, 0FFFFFFFF4D2FA200h
0x180016d98  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180016d9d  mov     r9d, 124F8h; msWindowLength
0x180016da3  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180016da8  xor     r8d, r8d; msPeriod
0x180016dab  call    cs:__imp_SetThreadpoolTimer
0x180016db2  nop     dword ptr [rax+rax+00h]
0x180016db7  mov     byte ptr [rdi+41h], 1
0x180016dbb  mov     rbx, [rsp+28h+arg_8]
0x180016dc0  mov     rsi, [rsp+28h+arg_10]
0x180016dc5  add     rsp, 20h
0x180016dc9  pop     rdi
0x180016dca  retn
```
