# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001261c`
- end: `0x180012650`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d788`
- `0x18000d7d8`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001262d`
- `KERNEL32!SetThreadpoolTimer` at `0x18001262d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001263b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001263b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180012649`

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
0x18001261c  push    rbx
0x18001261e  sub     rsp, 20h
0x180012622  xor     r9d, r9d; msWindowLength
0x180012625  xor     r8d, r8d; msPeriod
0x180012628  xor     edx, edx; pftDueTime
0x18001262a  mov     rbx, rcx
0x18001262d  call    cs:__imp_SetThreadpoolTimer
0x180012633  mov     edx, 1; fCancelPendingCallbacks
0x180012638  mov     rcx, rbx; pti
0x18001263b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012641  mov     rcx, rbx
0x180012644  add     rsp, 20h
0x180012648  pop     rbx
0x180012649  jmp     cs:__imp_CloseThreadpoolTimer
```
