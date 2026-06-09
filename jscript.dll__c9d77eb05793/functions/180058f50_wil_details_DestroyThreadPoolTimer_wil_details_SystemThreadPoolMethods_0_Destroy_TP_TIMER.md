# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180058f50`
- end: `0x180058f84`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18004ac54`
- `0x180053648`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180058f6f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180058f6f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180058f7d`
- `KERNEL32!SetThreadpoolTimer` at `0x180058f61`
- `KERNEL32!SetThreadpoolTimer` at `0x180058f61`

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
0x180058f50  push    rbx
0x180058f52  sub     rsp, 20h
0x180058f56  xor     r9d, r9d; msWindowLength
0x180058f59  xor     r8d, r8d; msPeriod
0x180058f5c  xor     edx, edx; pftDueTime
0x180058f5e  mov     rbx, rcx
0x180058f61  call    cs:__imp_SetThreadpoolTimer
0x180058f67  mov     edx, 1; fCancelPendingCallbacks
0x180058f6c  mov     rcx, rbx; pti
0x180058f6f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180058f75  mov     rcx, rbx
0x180058f78  add     rsp, 20h
0x180058f7c  pop     rbx
0x180058f7d  jmp     cs:__imp_CloseThreadpoolTimer
```
