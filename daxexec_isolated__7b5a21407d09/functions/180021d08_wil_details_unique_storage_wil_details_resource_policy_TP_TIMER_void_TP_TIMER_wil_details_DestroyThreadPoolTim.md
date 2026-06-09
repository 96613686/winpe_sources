# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180021d08`
- end: `0x180021d82`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800173cc`
- `0x1800176d4`
- `0x18001975c`
- `0x18001d650`
- `0x18001d708`
- `0x18001d86c`

## callees

- `0x180021d08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021d69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021d38`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021d38`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180021d5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180021d5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021d4c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021d4c`

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
0x180021d08  push    rbx
0x180021d0a  push    rbp
0x180021d0b  push    rsi
0x180021d0c  push    rdi
0x180021d0d  sub     rsp, 28h
0x180021d11  mov     rsi, [rcx]
0x180021d14  mov     rbp, rdx
0x180021d17  mov     rdi, rcx
0x180021d1a  test    rsi, rsi
0x180021d1d  jz      short loc_180021D75
0x180021d1f  call    cs:__imp_GetLastError
0x180021d26  nop     dword ptr [rax+rax+00h]
0x180021d2b  xor     r9d, r9d; msWindowLength
0x180021d2e  xor     r8d, r8d; msPeriod
0x180021d31  xor     edx, edx; pftDueTime
0x180021d33  mov     rcx, rsi; pti
0x180021d36  mov     ebx, eax
0x180021d38  call    cs:__imp_SetThreadpoolTimer
0x180021d3f  nop     dword ptr [rax+rax+00h]
0x180021d44  mov     edx, 1; fCancelPendingCallbacks
0x180021d49  mov     rcx, rsi; pti
0x180021d4c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180021d53  nop     dword ptr [rax+rax+00h]
0x180021d58  mov     rcx, rsi; pti
0x180021d5b  call    cs:__imp_CloseThreadpoolTimer
0x180021d62  nop     dword ptr [rax+rax+00h]
0x180021d67  mov     ecx, ebx; dwErrCode
0x180021d69  call    cs:__imp_SetLastError
0x180021d70  nop     dword ptr [rax+rax+00h]
0x180021d75  mov     [rdi], rbp
0x180021d78  add     rsp, 28h
0x180021d7c  pop     rdi
0x180021d7d  pop     rsi
0x180021d7e  pop     rbp
0x180021d7f  pop     rbx
0x180021d80  retn
```
