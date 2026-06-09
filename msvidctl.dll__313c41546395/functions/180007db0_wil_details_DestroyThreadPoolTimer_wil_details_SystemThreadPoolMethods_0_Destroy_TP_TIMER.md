# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180007db0`
- end: `0x180007de4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006d24`
- `0x18000c8f0`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180007ddd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007dcf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007dcf`
- `KERNEL32!SetThreadpoolTimer` at `0x180007dc1`
- `KERNEL32!SetThreadpoolTimer` at `0x180007dc1`

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
0x180007db0  push    rbx
0x180007db2  sub     rsp, 20h
0x180007db6  xor     r9d, r9d; msWindowLength
0x180007db9  xor     r8d, r8d; msPeriod
0x180007dbc  xor     edx, edx; pftDueTime
0x180007dbe  mov     rbx, rcx
0x180007dc1  call    cs:__imp_SetThreadpoolTimer
0x180007dc7  mov     edx, 1; fCancelPendingCallbacks
0x180007dcc  mov     rcx, rbx; pti
0x180007dcf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007dd5  mov     rcx, rbx
0x180007dd8  add     rsp, 20h
0x180007ddc  pop     rbx
0x180007ddd  jmp     cs:__imp_CloseThreadpoolTimer
```
