# wil::details::close_invoke_helper<1,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),_TP_TIMER *>::close_reset(_TP_TIMER *)

- ea: `0x180010f5c`
- end: `0x180010fac`
- name: `?close_reset@?$close_invoke_helper@$00P6AXPEAU_TP_TIMER@@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZPEAU1@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18001fb20`
- `0x18001fbb4`
- `0x18001fe48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010fa5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010f7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010f7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010f93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010f93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010f8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010f8a`

## pseudocode

```c
void __fastcall wil::details::close_invoke_helper<1,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),_TP_TIMER *>::close_reset(
        PTP_TIMER pti)
{
  DWORD LastError; // ebx

  LastError = GetLastError();
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
  SetLastError(LastError);
}

```

## disassembly

```asm
0x180010f5c  mov     [rsp+arg_0], rbx
0x180010f61  push    rdi
0x180010f62  sub     rsp, 20h
0x180010f66  mov     rdi, rcx
0x180010f69  call    cs:__imp_GetLastError
0x180010f6f  xor     r9d, r9d; msWindowLength
0x180010f72  xor     r8d, r8d; msPeriod
0x180010f75  xor     edx, edx; pftDueTime
0x180010f77  mov     rcx, rdi; pti
0x180010f7a  mov     ebx, eax
0x180010f7c  call    cs:__imp_SetThreadpoolTimer
0x180010f82  mov     edx, 1; fCancelPendingCallbacks
0x180010f87  mov     rcx, rdi; pti
0x180010f8a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010f90  mov     rcx, rdi; pti
0x180010f93  call    cs:__imp_CloseThreadpoolTimer
0x180010f99  mov     ecx, ebx
0x180010f9b  mov     rbx, [rsp+28h+arg_0]
0x180010fa0  add     rsp, 20h
0x180010fa4  pop     rdi
0x180010fa5  jmp     cs:__imp_SetLastError
```
