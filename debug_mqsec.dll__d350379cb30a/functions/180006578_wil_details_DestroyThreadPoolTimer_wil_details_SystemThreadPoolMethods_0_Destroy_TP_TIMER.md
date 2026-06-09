# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006578`
- end: `0x1800065af`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `55`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005cac`
- `0x18000af74`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180006589`
- `KERNEL32!SetThreadpoolTimer` at `0x180006589`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006598`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006598`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800065a2`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800065a2`

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
0x180006578  push    rbx
0x18000657a  sub     rsp, 20h
0x18000657e  mov     rbx, rcx
0x180006581  xor     r9d, r9d; msWindowLength
0x180006584  xor     r8d, r8d; msPeriod
0x180006587  xor     edx, edx; pftDueTime
0x180006589  call    cs:__imp_SetThreadpoolTimer
0x18000658f  nop
0x180006590  mov     edx, 1; fCancelPendingCallbacks
0x180006595  mov     rcx, rbx; pti
0x180006598  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000659e  nop
0x18000659f  mov     rcx, rbx; pti
0x1800065a2  call    cs:__imp_CloseThreadpoolTimer
0x1800065a8  nop
0x1800065a9  add     rsp, 20h
0x1800065ad  pop     rbx
0x1800065ae  retn
```
