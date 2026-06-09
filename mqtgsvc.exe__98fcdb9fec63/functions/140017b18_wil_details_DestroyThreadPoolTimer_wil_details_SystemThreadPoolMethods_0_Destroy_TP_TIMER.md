# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140017b18`
- end: `0x140017b4f`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `55`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140017294`
- `0x14001bd6c`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x140017b42`
- `KERNEL32!CloseThreadpoolTimer` at `0x140017b42`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140017b38`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140017b38`
- `KERNEL32!SetThreadpoolTimer` at `0x140017b29`
- `KERNEL32!SetThreadpoolTimer` at `0x140017b29`

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
0x140017b18  push    rbx
0x140017b1a  sub     rsp, 20h
0x140017b1e  mov     rbx, rcx
0x140017b21  xor     r9d, r9d; msWindowLength
0x140017b24  xor     r8d, r8d; msPeriod
0x140017b27  xor     edx, edx; pftDueTime
0x140017b29  call    cs:__imp_SetThreadpoolTimer
0x140017b2f  nop
0x140017b30  mov     edx, 1; fCancelPendingCallbacks
0x140017b35  mov     rcx, rbx; pti
0x140017b38  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140017b3e  nop
0x140017b3f  mov     rcx, rbx; pti
0x140017b42  call    cs:__imp_CloseThreadpoolTimer
0x140017b48  nop
0x140017b49  add     rsp, 20h
0x140017b4d  pop     rbx
0x140017b4e  retn
```
