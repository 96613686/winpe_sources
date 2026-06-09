# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000c100`
- end: `0x18000c17a`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005518`
- `0x1800069e8`
- `0x180008a1c`

## callees

- `0x18000c100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c117`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c161`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c161`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c144`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c144`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c130`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c130`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c153`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c153`

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
0x18000c100  push    rbx
0x18000c102  push    rbp
0x18000c103  push    rsi
0x18000c104  push    rdi
0x18000c105  sub     rsp, 28h
0x18000c109  mov     rsi, [rcx]
0x18000c10c  mov     rbp, rdx
0x18000c10f  mov     rdi, rcx
0x18000c112  test    rsi, rsi
0x18000c115  jz      short loc_18000C16D
0x18000c117  call    cs:__imp_GetLastError
0x18000c11e  nop     dword ptr [rax+rax+00h]
0x18000c123  xor     r9d, r9d; msWindowLength
0x18000c126  xor     r8d, r8d; msPeriod
0x18000c129  xor     edx, edx; pftDueTime
0x18000c12b  mov     rcx, rsi; pti
0x18000c12e  mov     ebx, eax
0x18000c130  call    cs:__imp_SetThreadpoolTimer
0x18000c137  nop     dword ptr [rax+rax+00h]
0x18000c13c  mov     edx, 1; fCancelPendingCallbacks
0x18000c141  mov     rcx, rsi; pti
0x18000c144  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c14b  nop     dword ptr [rax+rax+00h]
0x18000c150  mov     rcx, rsi; pti
0x18000c153  call    cs:__imp_CloseThreadpoolTimer
0x18000c15a  nop     dword ptr [rax+rax+00h]
0x18000c15f  mov     ecx, ebx; dwErrCode
0x18000c161  call    cs:__imp_SetLastError
0x18000c168  nop     dword ptr [rax+rax+00h]
0x18000c16d  mov     [rdi], rbp
0x18000c170  add     rsp, 28h
0x18000c174  pop     rdi
0x18000c175  pop     rsi
0x18000c176  pop     rbp
0x18000c177  pop     rbx
0x18000c178  retn
```
