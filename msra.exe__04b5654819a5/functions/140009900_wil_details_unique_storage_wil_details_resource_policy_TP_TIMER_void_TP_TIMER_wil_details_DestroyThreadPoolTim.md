# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x140009900`
- end: `0x14000997a`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140003548`
- `0x14000377c`
- `0x1400048f4`
- `0x140006128`
- `0x1400061e0`

## callees

- `0x140009900`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140009961`
- `KERNEL32!SetLastError` at `0x140009961`
- `KERNEL32!SetThreadpoolTimer` at `0x140009930`
- `KERNEL32!SetThreadpoolTimer` at `0x140009930`
- `KERNEL32!CloseThreadpoolTimer` at `0x140009953`
- `KERNEL32!CloseThreadpoolTimer` at `0x140009953`
- `KERNEL32!GetLastError` at `0x140009917`
- `KERNEL32!GetLastError` at `0x140009917`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140009944`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140009944`

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
0x140009900  push    rbx
0x140009902  push    rbp
0x140009903  push    rsi
0x140009904  push    rdi
0x140009905  sub     rsp, 28h
0x140009909  mov     rsi, [rcx]
0x14000990c  mov     rbp, rdx
0x14000990f  mov     rdi, rcx
0x140009912  test    rsi, rsi
0x140009915  jz      short loc_14000996D
0x140009917  call    cs:__imp_GetLastError
0x14000991e  nop     dword ptr [rax+rax+00h]
0x140009923  xor     r9d, r9d; msWindowLength
0x140009926  xor     r8d, r8d; msPeriod
0x140009929  xor     edx, edx; pftDueTime
0x14000992b  mov     rcx, rsi; pti
0x14000992e  mov     ebx, eax
0x140009930  call    cs:__imp_SetThreadpoolTimer
0x140009937  nop     dword ptr [rax+rax+00h]
0x14000993c  mov     edx, 1; fCancelPendingCallbacks
0x140009941  mov     rcx, rsi; pti
0x140009944  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000994b  nop     dword ptr [rax+rax+00h]
0x140009950  mov     rcx, rsi; pti
0x140009953  call    cs:__imp_CloseThreadpoolTimer
0x14000995a  nop     dword ptr [rax+rax+00h]
0x14000995f  mov     ecx, ebx; dwErrCode
0x140009961  call    cs:__imp_SetLastError
0x140009968  nop     dword ptr [rax+rax+00h]
0x14000996d  mov     [rdi], rbp
0x140009970  add     rsp, 28h
0x140009974  pop     rdi
0x140009975  pop     rsi
0x140009976  pop     rbp
0x140009977  pop     rbx
0x140009978  retn
```
