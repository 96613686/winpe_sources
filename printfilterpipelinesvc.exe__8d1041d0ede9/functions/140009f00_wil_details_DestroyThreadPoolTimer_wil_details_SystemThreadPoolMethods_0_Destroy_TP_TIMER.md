# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140009f00`
- end: `0x140009f34`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140009514`
- `0x14000ed50`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x140009f2d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140009f1f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140009f1f`
- `KERNEL32!SetThreadpoolTimer` at `0x140009f11`
- `KERNEL32!SetThreadpoolTimer` at `0x140009f11`

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
0x140009f00  push    rbx
0x140009f02  sub     rsp, 20h
0x140009f06  xor     r9d, r9d; msWindowLength
0x140009f09  xor     r8d, r8d; msPeriod
0x140009f0c  xor     edx, edx; pftDueTime
0x140009f0e  mov     rbx, rcx
0x140009f11  call    cs:__imp_SetThreadpoolTimer
0x140009f17  mov     edx, 1; fCancelPendingCallbacks
0x140009f1c  mov     rcx, rbx; pti
0x140009f1f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009f25  mov     rcx, rbx
0x140009f28  add     rsp, 20h
0x140009f2c  pop     rbx
0x140009f2d  jmp     cs:__imp_CloseThreadpoolTimer
```
