# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000cfb4`
- end: `0x18000d02e`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006708`
- `0x18000693c`
- `0x180007dac`
- `0x180009728`
- `0x1800099e0`
- `0x180019354`

## callees

- `0x18000cfb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d015`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d015`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d007`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d007`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cfe4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cfe4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cff8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cff8`

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
0x18000cfb4  push    rbx
0x18000cfb6  push    rbp
0x18000cfb7  push    rsi
0x18000cfb8  push    rdi
0x18000cfb9  sub     rsp, 28h
0x18000cfbd  mov     rsi, [rcx]
0x18000cfc0  mov     rbp, rdx
0x18000cfc3  mov     rdi, rcx
0x18000cfc6  test    rsi, rsi
0x18000cfc9  jz      short loc_18000D021
0x18000cfcb  call    cs:__imp_GetLastError
0x18000cfd2  nop     dword ptr [rax+rax+00h]
0x18000cfd7  xor     r9d, r9d; msWindowLength
0x18000cfda  xor     r8d, r8d; msPeriod
0x18000cfdd  xor     edx, edx; pftDueTime
0x18000cfdf  mov     rcx, rsi; pti
0x18000cfe2  mov     ebx, eax
0x18000cfe4  call    cs:__imp_SetThreadpoolTimer
0x18000cfeb  nop     dword ptr [rax+rax+00h]
0x18000cff0  mov     edx, 1; fCancelPendingCallbacks
0x18000cff5  mov     rcx, rsi; pti
0x18000cff8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cfff  nop     dword ptr [rax+rax+00h]
0x18000d004  mov     rcx, rsi; pti
0x18000d007  call    cs:__imp_CloseThreadpoolTimer
0x18000d00e  nop     dword ptr [rax+rax+00h]
0x18000d013  mov     ecx, ebx; dwErrCode
0x18000d015  call    cs:__imp_SetLastError
0x18000d01c  nop     dword ptr [rax+rax+00h]
0x18000d021  mov     [rdi], rbp
0x18000d024  add     rsp, 28h
0x18000d028  pop     rdi
0x18000d029  pop     rsi
0x18000d02a  pop     rbp
0x18000d02b  pop     rbx
0x18000d02c  retn
```
