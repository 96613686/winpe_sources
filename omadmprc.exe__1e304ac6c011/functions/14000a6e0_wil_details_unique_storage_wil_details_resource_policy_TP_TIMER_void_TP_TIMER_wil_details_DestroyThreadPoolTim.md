# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14000a6e0`
- end: `0x14000a75a`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140003a80`
- `0x140003cb4`
- `0x140004e64`
- `0x1400068b8`
- `0x140006b24`
- `0x140006c9c`

## callees

- `0x14000a6e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a6f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a6f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a741`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a741`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000a733`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000a733`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000a724`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000a724`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a710`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a710`

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
0x14000a6e0  push    rbx
0x14000a6e2  push    rbp
0x14000a6e3  push    rsi
0x14000a6e4  push    rdi
0x14000a6e5  sub     rsp, 28h
0x14000a6e9  mov     rsi, [rcx]
0x14000a6ec  mov     rbp, rdx
0x14000a6ef  mov     rdi, rcx
0x14000a6f2  test    rsi, rsi
0x14000a6f5  jz      short loc_14000A74D
0x14000a6f7  call    cs:__imp_GetLastError
0x14000a6fe  nop     dword ptr [rax+rax+00h]
0x14000a703  xor     r9d, r9d; msWindowLength
0x14000a706  xor     r8d, r8d; msPeriod
0x14000a709  xor     edx, edx; pftDueTime
0x14000a70b  mov     rcx, rsi; pti
0x14000a70e  mov     ebx, eax
0x14000a710  call    cs:__imp_SetThreadpoolTimer
0x14000a717  nop     dword ptr [rax+rax+00h]
0x14000a71c  mov     edx, 1; fCancelPendingCallbacks
0x14000a721  mov     rcx, rsi; pti
0x14000a724  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000a72b  nop     dword ptr [rax+rax+00h]
0x14000a730  mov     rcx, rsi; pti
0x14000a733  call    cs:__imp_CloseThreadpoolTimer
0x14000a73a  nop     dword ptr [rax+rax+00h]
0x14000a73f  mov     ecx, ebx; dwErrCode
0x14000a741  call    cs:__imp_SetLastError
0x14000a748  nop     dword ptr [rax+rax+00h]
0x14000a74d  mov     [rdi], rbp
0x14000a750  add     rsp, 28h
0x14000a754  pop     rdi
0x14000a755  pop     rsi
0x14000a756  pop     rbp
0x14000a757  pop     rbx
0x14000a758  retn
```
