# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800069e8`
- end: `0x180006a90`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008e24`

## callees

- `0x1800069e8`
- `0x18000c100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006a3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006a3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006a6f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006a6f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006a25`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006a25`

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
0x1800069e8  mov     [rsp+arg_8], rbx
0x1800069ed  mov     [rsp+arg_10], rsi
0x1800069f2  push    rdi
0x1800069f3  sub     rsp, 20h
0x1800069f7  cmp     byte ptr [rcx+41h], 0
0x1800069fb  mov     rdi, rcx
0x1800069fe  jnz     short loc_180006A7F
0x180006a00  lea     rsi, [rcx+30h]
0x180006a04  cmp     qword ptr [rsi], 0
0x180006a08  jnz     short loc_180006A4A
0x180006a0a  call    cs:__imp_GetLastError
0x180006a11  nop     dword ptr [rax+rax+00h]
0x180006a16  xor     r8d, r8d; pcbe
0x180006a19  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006a20  mov     rdx, rdi; pv
0x180006a23  mov     ebx, eax
0x180006a25  call    cs:__imp_CreateThreadpoolTimer
0x180006a2c  nop     dword ptr [rax+rax+00h]
0x180006a31  mov     rdx, rax
0x180006a34  mov     rcx, rsi
0x180006a37  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006a3c  mov     ecx, ebx; dwErrCode
0x180006a3e  call    cs:__imp_SetLastError
0x180006a45  nop     dword ptr [rax+rax+00h]
0x180006a4a  mov     rcx, [rsi]; pti
0x180006a4d  test    rcx, rcx
0x180006a50  jz      short loc_180006A7F
0x180006a52  mov     rax, 0FFFFFFFF4D2FA200h
0x180006a5c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180006a61  mov     r9d, 124F8h; msWindowLength
0x180006a67  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180006a6c  xor     r8d, r8d; msPeriod
0x180006a6f  call    cs:__imp_SetThreadpoolTimer
0x180006a76  nop     dword ptr [rax+rax+00h]
0x180006a7b  mov     byte ptr [rdi+41h], 1
0x180006a7f  mov     rbx, [rsp+28h+arg_8]
0x180006a84  mov     rsi, [rsp+28h+arg_10]
0x180006a89  add     rsp, 20h
0x180006a8d  pop     rdi
0x180006a8e  retn
```
