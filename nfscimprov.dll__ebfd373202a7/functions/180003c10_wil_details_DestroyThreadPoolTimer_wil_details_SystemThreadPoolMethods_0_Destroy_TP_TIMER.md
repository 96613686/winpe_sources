# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180003c10`
- end: `0x180003c44`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800033b4`
- `0x180007f3c`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003c2f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003c2f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003c3d`
- `KERNEL32!SetThreadpoolTimer` at `0x180003c21`
- `KERNEL32!SetThreadpoolTimer` at `0x180003c21`

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
0x180003c10  push    rbx
0x180003c12  sub     rsp, 20h
0x180003c16  xor     r9d, r9d; msWindowLength
0x180003c19  xor     r8d, r8d; msPeriod
0x180003c1c  xor     edx, edx; pftDueTime
0x180003c1e  mov     rbx, rcx
0x180003c21  call    cs:__imp_SetThreadpoolTimer
0x180003c27  mov     edx, 1; fCancelPendingCallbacks
0x180003c2c  mov     rcx, rbx; pti
0x180003c2f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003c35  mov     rcx, rbx
0x180003c38  add     rsp, 20h
0x180003c3c  pop     rbx
0x180003c3d  jmp     cs:__imp_CloseThreadpoolTimer
```
