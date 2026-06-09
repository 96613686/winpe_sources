# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800265e4`
- end: `0x180026675`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001c004`
- `0x18001c224`
- `0x18001d224`
- `0x1800235e0`
- `0x18002372c`

## callees

- `0x1800265e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026650`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026606`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002661f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002661f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180026642`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180026642`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026633`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026633`

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
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x1800265e4  mov     [rsp+arg_0], rbx
0x1800265e9  mov     [rsp+arg_8], rbp
0x1800265ee  mov     [rsp+arg_10], rsi
0x1800265f3  push    rdi
0x1800265f4  sub     rsp, 20h
0x1800265f8  mov     rsi, [rcx]
0x1800265fb  mov     rbp, rdx
0x1800265fe  mov     rdi, rcx
0x180026601  test    rsi, rsi
0x180026604  jz      short loc_18002665C
0x180026606  call    cs:__imp_GetLastError
0x18002660d  nop     dword ptr [rax+rax+00h]
0x180026612  xor     r9d, r9d; msWindowLength
0x180026615  xor     r8d, r8d; msPeriod
0x180026618  xor     edx, edx; pftDueTime
0x18002661a  mov     rcx, rsi; pti
0x18002661d  mov     ebx, eax
0x18002661f  call    cs:__imp_SetThreadpoolTimer
0x180026626  nop     dword ptr [rax+rax+00h]
0x18002662b  mov     edx, 1; fCancelPendingCallbacks
0x180026630  mov     rcx, rsi; pti
0x180026633  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002663a  nop     dword ptr [rax+rax+00h]
0x18002663f  mov     rcx, rsi; pti
0x180026642  call    cs:__imp_CloseThreadpoolTimer
0x180026649  nop     dword ptr [rax+rax+00h]
0x18002664e  mov     ecx, ebx; dwErrCode
0x180026650  call    cs:__imp_SetLastError
0x180026657  nop     dword ptr [rax+rax+00h]
0x18002665c  mov     rbx, [rsp+28h+arg_0]
0x180026661  mov     rsi, [rsp+28h+arg_10]
0x180026666  mov     [rdi], rbp
0x180026669  mov     rbp, [rsp+28h+arg_8]
0x18002666e  add     rsp, 20h
0x180026672  pop     rdi
0x180026673  retn
```
