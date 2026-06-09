# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180004980`
- end: `0x180004a05`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `133`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002ee0`
- `0x180003760`
- `0x180003c90`
- `0x180004100`
- `0x180004630`
- `0x180004c78`
- `0x180004f88`
- `0x180005298`
- `0x180005750`
- `0x180012910`
- `0x180013fb4`
- `0x1800194f0`
- `0x180019700`
- `0x180026d7c`
- `0x180077730`

## callees

- `0x180004980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049d6`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // edi

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
0x180004980  mov     [rsp+arg_8], rbx
0x180004985  mov     [rsp+arg_10], rbp
0x18000498a  push    rsi
0x18000498b  sub     rsp, 20h
0x18000498f  mov     rsi, [rcx]
0x180004992  mov     rbp, rdx
0x180004995  mov     rbx, rcx
0x180004998  test    rsi, rsi
0x18000499b  jnz     short loc_1800049B0
0x18000499d  mov     [rcx], rdx
0x1800049a0  mov     rbx, [rsp+28h+arg_8]
0x1800049a5  mov     rbp, [rsp+28h+arg_10]
0x1800049aa  add     rsp, 20h
0x1800049ae  pop     rsi
0x1800049af  retn
0x1800049b0  mov     [rsp+28h+arg_0], rdi
0x1800049b5  call    cs:__imp_GetLastError
0x1800049bb  xor     r9d, r9d; msWindowLength
0x1800049be  xor     r8d, r8d; msPeriod
0x1800049c1  xor     edx, edx; pftDueTime
0x1800049c3  mov     rcx, rsi; pti
0x1800049c6  mov     edi, eax
0x1800049c8  call    cs:__imp_SetThreadpoolTimer
0x1800049ce  mov     edx, 1; fCancelPendingCallbacks
0x1800049d3  mov     rcx, rsi; pti
0x1800049d6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800049dc  mov     rcx, rsi; pti
0x1800049df  call    cs:__imp_CloseThreadpoolTimer
0x1800049e5  mov     ecx, edi; dwErrCode
0x1800049e7  call    cs:__imp_SetLastError
0x1800049ed  mov     rdi, [rsp+28h+arg_0]
0x1800049f2  mov     [rbx], rbp
0x1800049f5  mov     rbx, [rsp+28h+arg_8]
0x1800049fa  mov     rbp, [rsp+28h+arg_10]
0x1800049ff  add     rsp, 20h
0x180004a03  pop     rsi
0x180004a04  retn
```
