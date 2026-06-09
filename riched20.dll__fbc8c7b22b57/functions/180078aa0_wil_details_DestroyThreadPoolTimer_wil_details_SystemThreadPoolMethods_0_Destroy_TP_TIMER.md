# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180078aa0`
- end: `0x180078ae5`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180078028`
- `0x18007d500`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180078ab1`
- `KERNEL32!SetThreadpoolTimer` at `0x180078ab1`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180078ac5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180078ac5`
- `KERNEL32!CloseThreadpoolTimer` at `0x180078ad9`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180078aa0  push    rbx
0x180078aa2  sub     rsp, 20h
0x180078aa6  xor     r9d, r9d; msWindowLength
0x180078aa9  xor     r8d, r8d; msPeriod
0x180078aac  xor     edx, edx; pftDueTime
0x180078aae  mov     rbx, rcx
0x180078ab1  call    cs:__imp_SetThreadpoolTimer
0x180078ab8  nop     dword ptr [rax+rax+00h]
0x180078abd  mov     edx, 1; fCancelPendingCallbacks
0x180078ac2  mov     rcx, rbx; pti
0x180078ac5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180078acc  nop     dword ptr [rax+rax+00h]
0x180078ad1  mov     rcx, rbx
0x180078ad4  add     rsp, 20h
0x180078ad8  pop     rbx
0x180078ad9  jmp     cs:__imp_CloseThreadpoolTimer
```
