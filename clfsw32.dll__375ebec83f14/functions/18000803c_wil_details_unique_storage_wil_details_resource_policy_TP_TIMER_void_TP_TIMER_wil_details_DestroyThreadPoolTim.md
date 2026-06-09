# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000803c`
- end: `0x1800080b6`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800033c0`
- `0x180004268`
- `0x1800059d0`

## callees

- `0x18000803c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000809d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000809d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008053`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008080`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008080`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000806c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000806c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000808f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000808f`

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
0x18000803c  push    rbx
0x18000803e  push    rbp
0x18000803f  push    rsi
0x180008040  push    rdi
0x180008041  sub     rsp, 28h
0x180008045  mov     rsi, [rcx]
0x180008048  mov     rbp, rdx
0x18000804b  mov     rdi, rcx
0x18000804e  test    rsi, rsi
0x180008051  jz      short loc_1800080A9
0x180008053  call    cs:__imp_GetLastError
0x18000805a  nop     dword ptr [rax+rax+00h]
0x18000805f  xor     r9d, r9d; msWindowLength
0x180008062  xor     r8d, r8d; msPeriod
0x180008065  xor     edx, edx; pftDueTime
0x180008067  mov     rcx, rsi; pti
0x18000806a  mov     ebx, eax
0x18000806c  call    cs:__imp_SetThreadpoolTimer
0x180008073  nop     dword ptr [rax+rax+00h]
0x180008078  mov     edx, 1; fCancelPendingCallbacks
0x18000807d  mov     rcx, rsi; pti
0x180008080  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008087  nop     dword ptr [rax+rax+00h]
0x18000808c  mov     rcx, rsi; pti
0x18000808f  call    cs:__imp_CloseThreadpoolTimer
0x180008096  nop     dword ptr [rax+rax+00h]
0x18000809b  mov     ecx, ebx; dwErrCode
0x18000809d  call    cs:__imp_SetLastError
0x1800080a4  nop     dword ptr [rax+rax+00h]
0x1800080a9  mov     [rdi], rbp
0x1800080ac  add     rsp, 28h
0x1800080b0  pop     rdi
0x1800080b1  pop     rsi
0x1800080b2  pop     rbp
0x1800080b3  pop     rbx
0x1800080b4  retn
```
