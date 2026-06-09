# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14001967c`
- end: `0x140019724`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001c7f0`

## callees

- `0x14001967c`
- `0x1400204b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400196d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400196d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001969e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001969e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400196b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400196b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140019703`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140019703`

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
0x14001967c  mov     [rsp+arg_8], rbx
0x140019681  mov     [rsp+arg_10], rsi
0x140019686  push    rdi
0x140019687  sub     rsp, 20h
0x14001968b  cmp     byte ptr [rcx+41h], 0
0x14001968f  mov     rdi, rcx
0x140019692  jnz     short loc_140019713
0x140019694  lea     rsi, [rcx+30h]
0x140019698  cmp     qword ptr [rsi], 0
0x14001969c  jnz     short loc_1400196DE
0x14001969e  call    cs:__imp_GetLastError
0x1400196a5  nop     dword ptr [rax+rax+00h]
0x1400196aa  xor     r8d, r8d; pcbe
0x1400196ad  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400196b4  mov     rdx, rdi; pv
0x1400196b7  mov     ebx, eax
0x1400196b9  call    cs:__imp_CreateThreadpoolTimer
0x1400196c0  nop     dword ptr [rax+rax+00h]
0x1400196c5  mov     rdx, rax
0x1400196c8  mov     rcx, rsi
0x1400196cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400196d0  mov     ecx, ebx; dwErrCode
0x1400196d2  call    cs:__imp_SetLastError
0x1400196d9  nop     dword ptr [rax+rax+00h]
0x1400196de  mov     rcx, [rsi]; pti
0x1400196e1  test    rcx, rcx
0x1400196e4  jz      short loc_140019713
0x1400196e6  mov     rax, 0FFFFFFFF4D2FA200h
0x1400196f0  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1400196f5  mov     r9d, 124F8h; msWindowLength
0x1400196fb  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x140019700  xor     r8d, r8d; msPeriod
0x140019703  call    cs:__imp_SetThreadpoolTimer
0x14001970a  nop     dword ptr [rax+rax+00h]
0x14001970f  mov     byte ptr [rdi+41h], 1
0x140019713  mov     rbx, [rsp+28h+arg_8]
0x140019718  mov     rsi, [rsp+28h+arg_10]
0x14001971d  add     rsp, 20h
0x140019721  pop     rdi
0x140019722  retn
```
