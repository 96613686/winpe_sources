# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1400048f4`
- end: `0x14000499c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140006764`

## callees

- `0x1400048f4`
- `0x140009900`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000494a`
- `KERNEL32!SetLastError` at `0x14000494a`
- `KERNEL32!CreateThreadpoolTimer` at `0x140004931`
- `KERNEL32!CreateThreadpoolTimer` at `0x140004931`
- `KERNEL32!SetThreadpoolTimer` at `0x14000497b`
- `KERNEL32!SetThreadpoolTimer` at `0x14000497b`
- `KERNEL32!GetLastError` at `0x140004916`
- `KERNEL32!GetLastError` at `0x140004916`

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
0x1400048f4  mov     [rsp+arg_8], rbx
0x1400048f9  mov     [rsp+arg_10], rsi
0x1400048fe  push    rdi
0x1400048ff  sub     rsp, 20h
0x140004903  cmp     byte ptr [rcx+41h], 0
0x140004907  mov     rdi, rcx
0x14000490a  jnz     short loc_14000498B
0x14000490c  lea     rsi, [rcx+30h]
0x140004910  cmp     qword ptr [rsi], 0
0x140004914  jnz     short loc_140004956
0x140004916  call    cs:__imp_GetLastError
0x14000491d  nop     dword ptr [rax+rax+00h]
0x140004922  xor     r8d, r8d; pcbe
0x140004925  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000492c  mov     rdx, rdi; pv
0x14000492f  mov     ebx, eax
0x140004931  call    cs:__imp_CreateThreadpoolTimer
0x140004938  nop     dword ptr [rax+rax+00h]
0x14000493d  mov     rdx, rax
0x140004940  mov     rcx, rsi
0x140004943  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140004948  mov     ecx, ebx; dwErrCode
0x14000494a  call    cs:__imp_SetLastError
0x140004951  nop     dword ptr [rax+rax+00h]
0x140004956  mov     rcx, [rsi]; pti
0x140004959  test    rcx, rcx
0x14000495c  jz      short loc_14000498B
0x14000495e  mov     rax, 0FFFFFFFF4D2FA200h
0x140004968  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x14000496d  mov     r9d, 124F8h; msWindowLength
0x140004973  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x140004978  xor     r8d, r8d; msPeriod
0x14000497b  call    cs:__imp_SetThreadpoolTimer
0x140004982  nop     dword ptr [rax+rax+00h]
0x140004987  mov     byte ptr [rdi+41h], 1
0x14000498b  mov     rbx, [rsp+28h+arg_8]
0x140004990  mov     rsi, [rsp+28h+arg_10]
0x140004995  add     rsp, 20h
0x140004999  pop     rdi
0x14000499a  retn
```
