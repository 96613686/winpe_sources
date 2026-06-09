# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180004f94`
- end: `0x18000503c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006eb4`

## callees

- `0x180004f94`
- `0x180009c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004fd1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004fd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000501b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000501b`

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
0x180004f94  mov     [rsp+arg_8], rbx
0x180004f99  mov     [rsp+arg_10], rsi
0x180004f9e  push    rdi
0x180004f9f  sub     rsp, 20h
0x180004fa3  cmp     byte ptr [rcx+41h], 0
0x180004fa7  lea     rsi, [rcx+30h]
0x180004fab  mov     rdi, rcx
0x180004fae  jnz     short loc_18000502B
0x180004fb0  cmp     qword ptr [rsi], 0
0x180004fb4  jnz     short loc_180004FF6
0x180004fb6  call    cs:__imp_GetLastError
0x180004fbd  nop     dword ptr [rax+rax+00h]
0x180004fc2  xor     r8d, r8d; pcbe
0x180004fc5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004fcc  mov     rdx, rdi; pv
0x180004fcf  mov     ebx, eax
0x180004fd1  call    cs:__imp_CreateThreadpoolTimer
0x180004fd8  nop     dword ptr [rax+rax+00h]
0x180004fdd  mov     rdx, rax
0x180004fe0  mov     rcx, rsi
0x180004fe3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180004fe8  mov     ecx, ebx; dwErrCode
0x180004fea  call    cs:__imp_SetLastError
0x180004ff1  nop     dword ptr [rax+rax+00h]
0x180004ff6  mov     rcx, [rsi]; pti
0x180004ff9  test    rcx, rcx
0x180004ffc  jz      short loc_18000502B
0x180004ffe  mov     rax, 0FFFFFFFF4D2FA200h
0x180005008  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000500d  mov     r9d, 124F8h; msWindowLength
0x180005013  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180005018  xor     r8d, r8d; msPeriod
0x18000501b  call    cs:__imp_SetThreadpoolTimer
0x180005022  nop     dword ptr [rax+rax+00h]
0x180005027  mov     byte ptr [rdi+41h], 1
0x18000502b  mov     rbx, [rsp+28h+arg_8]
0x180005030  mov     rsi, [rsp+28h+arg_10]
0x180005035  add     rsp, 20h
0x180005039  pop     rdi
0x18000503a  retn
```
