# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180029820`
- end: `0x1800298a5`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `133`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180022710`
- `0x180025fe0`
- `0x1800265d0`
- `0x180028b30`
- `0x180029580`

## callees

- `0x180029820`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029874`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029842`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029855`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029855`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180029863`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180029863`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002986c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002986c`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
    *a1 = a2;
  }
  else
  {
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x180029820  mov     [rsp+arg_8], rbp
0x180029825  mov     [rsp+arg_10], rsi
0x18002982a  push    rdi
0x18002982b  sub     rsp, 20h
0x18002982f  mov     rsi, [rcx]
0x180029832  mov     rbp, rdx
0x180029835  mov     rdi, rcx
0x180029838  test    rsi, rsi
0x18002983b  jz      short loc_180029892
0x18002983d  mov     [rsp+28h+arg_0], rbx
0x180029842  call    cs:__imp_GetLastError
0x180029848  xor     r9d, r9d; msWindowLength
0x18002984b  xor     r8d, r8d; msPeriod
0x18002984e  xor     edx, edx; pftDueTime
0x180029850  mov     rcx, rsi; pti
0x180029853  mov     ebx, eax
0x180029855  call    cs:__imp_SetThreadpoolTimer
0x18002985b  mov     edx, 1; fCancelPendingCallbacks
0x180029860  mov     rcx, rsi; pti
0x180029863  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180029869  mov     rcx, rsi; pti
0x18002986c  call    cs:__imp_CloseThreadpoolTimer
0x180029872  mov     ecx, ebx; dwErrCode
0x180029874  call    cs:__imp_SetLastError
0x18002987a  mov     rbx, [rsp+28h+arg_0]
0x18002987f  mov     [rdi], rbp
0x180029882  mov     rbp, [rsp+28h+arg_8]
0x180029887  mov     rsi, [rsp+28h+arg_10]
0x18002988c  add     rsp, 20h
0x180029890  pop     rdi
0x180029891  retn
0x180029892  mov     rsi, [rsp+28h+arg_10]
0x180029897  mov     [rcx], rbp
0x18002989a  mov     rbp, [rsp+28h+arg_8]
0x18002989f  add     rsp, 20h
0x1800298a3  pop     rdi
0x1800298a4  retn
```
