# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400784e0`
- end: `0x140078514`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400734bc`
- `0x1400749ec`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1400784f1`
- `KERNEL32!SetThreadpoolTimer` at `0x1400784f1`
- `KERNEL32!CloseThreadpoolTimer` at `0x14007850d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400784ff`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400784ff`

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
0x1400784e0  push    rbx
0x1400784e2  sub     rsp, 20h
0x1400784e6  xor     r9d, r9d; msWindowLength
0x1400784e9  xor     r8d, r8d; msPeriod
0x1400784ec  xor     edx, edx; pftDueTime
0x1400784ee  mov     rbx, rcx
0x1400784f1  call    cs:__imp_SetThreadpoolTimer
0x1400784f7  mov     edx, 1; fCancelPendingCallbacks
0x1400784fc  mov     rcx, rbx; pti
0x1400784ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140078505  mov     rcx, rbx
0x140078508  add     rsp, 20h
0x14007850c  pop     rbx
0x14007850d  jmp     cs:__imp_CloseThreadpoolTimer
```
