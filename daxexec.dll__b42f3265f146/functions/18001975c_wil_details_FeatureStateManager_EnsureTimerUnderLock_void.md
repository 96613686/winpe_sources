# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18001975c`
- end: `0x180019804`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001ddd8`

## callees

- `0x18001975c`
- `0x180021d08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800197b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800197b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001977e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001977e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800197e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800197e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019799`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019799`

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
0x18001975c  mov     [rsp+arg_8], rbx
0x180019761  mov     [rsp+arg_10], rsi
0x180019766  push    rdi
0x180019767  sub     rsp, 20h
0x18001976b  cmp     byte ptr [rcx+41h], 0
0x18001976f  mov     rdi, rcx
0x180019772  jnz     short loc_1800197F3
0x180019774  lea     rsi, [rcx+30h]
0x180019778  cmp     qword ptr [rsi], 0
0x18001977c  jnz     short loc_1800197BE
0x18001977e  call    cs:__imp_GetLastError
0x180019785  nop     dword ptr [rax+rax+00h]
0x18001978a  xor     r8d, r8d; pcbe
0x18001978d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019794  mov     rdx, rdi; pv
0x180019797  mov     ebx, eax
0x180019799  call    cs:__imp_CreateThreadpoolTimer
0x1800197a0  nop     dword ptr [rax+rax+00h]
0x1800197a5  mov     rdx, rax
0x1800197a8  mov     rcx, rsi
0x1800197ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800197b0  mov     ecx, ebx; dwErrCode
0x1800197b2  call    cs:__imp_SetLastError
0x1800197b9  nop     dword ptr [rax+rax+00h]
0x1800197be  mov     rcx, [rsi]; pti
0x1800197c1  test    rcx, rcx
0x1800197c4  jz      short loc_1800197F3
0x1800197c6  mov     rax, 0FFFFFFFF4D2FA200h
0x1800197d0  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800197d5  mov     r9d, 124F8h; msWindowLength
0x1800197db  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x1800197e0  xor     r8d, r8d; msPeriod
0x1800197e3  call    cs:__imp_SetThreadpoolTimer
0x1800197ea  nop     dword ptr [rax+rax+00h]
0x1800197ef  mov     byte ptr [rdi+41h], 1
0x1800197f3  mov     rbx, [rsp+28h+arg_8]
0x1800197f8  mov     rsi, [rsp+28h+arg_10]
0x1800197fd  add     rsp, 20h
0x180019801  pop     rdi
0x180019802  retn
```
