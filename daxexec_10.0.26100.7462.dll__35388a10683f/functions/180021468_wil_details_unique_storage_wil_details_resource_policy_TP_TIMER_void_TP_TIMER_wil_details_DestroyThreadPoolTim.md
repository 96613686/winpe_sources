# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180021468`
- end: `0x1800214f9`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015788`
- `0x180015a90`
- `0x180017b94`
- `0x18001cb50`
- `0x18001cc98`

## callees

- `0x180021468`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002148a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002148a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800214d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800214d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800214b7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800214b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800214a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800214a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800214c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800214c6`

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
0x180021468  mov     [rsp+arg_0], rbx
0x18002146d  mov     [rsp+arg_8], rbp
0x180021472  mov     [rsp+arg_10], rsi
0x180021477  push    rdi
0x180021478  sub     rsp, 20h
0x18002147c  mov     rsi, [rcx]
0x18002147f  mov     rbp, rdx
0x180021482  mov     rdi, rcx
0x180021485  test    rsi, rsi
0x180021488  jz      short loc_1800214E0
0x18002148a  call    cs:__imp_GetLastError
0x180021491  nop     dword ptr [rax+rax+00h]
0x180021496  xor     r9d, r9d; msWindowLength
0x180021499  xor     r8d, r8d; msPeriod
0x18002149c  xor     edx, edx; pftDueTime
0x18002149e  mov     rcx, rsi; pti
0x1800214a1  mov     ebx, eax
0x1800214a3  call    cs:__imp_SetThreadpoolTimer
0x1800214aa  nop     dword ptr [rax+rax+00h]
0x1800214af  mov     edx, 1; fCancelPendingCallbacks
0x1800214b4  mov     rcx, rsi; pti
0x1800214b7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800214be  nop     dword ptr [rax+rax+00h]
0x1800214c3  mov     rcx, rsi; pti
0x1800214c6  call    cs:__imp_CloseThreadpoolTimer
0x1800214cd  nop     dword ptr [rax+rax+00h]
0x1800214d2  mov     ecx, ebx; dwErrCode
0x1800214d4  call    cs:__imp_SetLastError
0x1800214db  nop     dword ptr [rax+rax+00h]
0x1800214e0  mov     rbx, [rsp+28h+arg_0]
0x1800214e5  mov     rsi, [rsp+28h+arg_10]
0x1800214ea  mov     [rdi], rbp
0x1800214ed  mov     rbp, [rsp+28h+arg_8]
0x1800214f2  add     rsp, 20h
0x1800214f6  pop     rdi
0x1800214f7  retn
```
