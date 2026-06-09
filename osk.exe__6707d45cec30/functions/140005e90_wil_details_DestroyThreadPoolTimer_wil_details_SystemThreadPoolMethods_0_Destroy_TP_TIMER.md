# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140005e90`
- end: `0x140005ec4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000511c`
- `0x14000c978`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005eaf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005eaf`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005ebd`
- `KERNEL32!SetThreadpoolTimer` at `0x140005ea1`
- `KERNEL32!SetThreadpoolTimer` at `0x140005ea1`

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
0x140005e90  push    rbx
0x140005e92  sub     rsp, 20h
0x140005e96  xor     r9d, r9d; msWindowLength
0x140005e99  xor     r8d, r8d; msPeriod
0x140005e9c  xor     edx, edx; pftDueTime
0x140005e9e  mov     rbx, rcx
0x140005ea1  call    cs:__imp_SetThreadpoolTimer
0x140005ea7  mov     edx, 1; fCancelPendingCallbacks
0x140005eac  mov     rcx, rbx; pti
0x140005eaf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005eb5  mov     rcx, rbx
0x140005eb8  add     rsp, 20h
0x140005ebc  pop     rbx
0x140005ebd  jmp     cs:__imp_CloseThreadpoolTimer
```
