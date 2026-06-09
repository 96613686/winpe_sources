# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18007693c`
- end: `0x180076970`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180075f94`
- `0x18007b1c4`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18007694d`
- `KERNEL32!SetThreadpoolTimer` at `0x18007694d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18007695b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18007695b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180076969`

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
0x18007693c  push    rbx
0x18007693e  sub     rsp, 20h
0x180076942  xor     r9d, r9d; msWindowLength
0x180076945  xor     r8d, r8d; msPeriod
0x180076948  xor     edx, edx; pftDueTime
0x18007694a  mov     rbx, rcx
0x18007694d  call    cs:__imp_SetThreadpoolTimer
0x180076953  mov     edx, 1; fCancelPendingCallbacks
0x180076958  mov     rcx, rbx; pti
0x18007695b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180076961  mov     rcx, rbx
0x180076964  add     rsp, 20h
0x180076968  pop     rbx
0x180076969  jmp     cs:__imp_CloseThreadpoolTimer
```
