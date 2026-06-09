# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180004148`
- end: `0x18000417f`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `55`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800038c4`
- `0x180007f64`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180004159`
- `KERNEL32!SetThreadpoolTimer` at `0x180004159`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004168`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004168`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004172`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004172`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180004148  push    rbx
0x18000414a  sub     rsp, 20h
0x18000414e  mov     rbx, rcx
0x180004151  xor     r9d, r9d; msWindowLength
0x180004154  xor     r8d, r8d; msPeriod
0x180004157  xor     edx, edx; pftDueTime
0x180004159  call    cs:__imp_SetThreadpoolTimer
0x18000415f  nop
0x180004160  mov     edx, 1; fCancelPendingCallbacks
0x180004165  mov     rcx, rbx; pti
0x180004168  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000416e  nop
0x18000416f  mov     rcx, rbx; pti
0x180004172  call    cs:__imp_CloseThreadpoolTimer
0x180004178  nop
0x180004179  add     rsp, 20h
0x18000417d  pop     rbx
0x18000417e  retn
```
