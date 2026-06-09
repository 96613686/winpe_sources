# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180032a60`
- end: `0x180032a94`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180032304`
- `0x1800364f8`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180032a7f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180032a7f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180032a8d`
- `KERNEL32!SetThreadpoolTimer` at `0x180032a71`
- `KERNEL32!SetThreadpoolTimer` at `0x180032a71`

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
0x180032a60  push    rbx
0x180032a62  sub     rsp, 20h
0x180032a66  xor     r9d, r9d; msWindowLength
0x180032a69  xor     r8d, r8d; msPeriod
0x180032a6c  xor     edx, edx; pftDueTime
0x180032a6e  mov     rbx, rcx
0x180032a71  call    cs:__imp_SetThreadpoolTimer
0x180032a77  mov     edx, 1; fCancelPendingCallbacks
0x180032a7c  mov     rcx, rbx; pti
0x180032a7f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180032a85  mov     rcx, rbx
0x180032a88  add     rsp, 20h
0x180032a8c  pop     rbx
0x180032a8d  jmp     cs:__imp_CloseThreadpoolTimer
```
