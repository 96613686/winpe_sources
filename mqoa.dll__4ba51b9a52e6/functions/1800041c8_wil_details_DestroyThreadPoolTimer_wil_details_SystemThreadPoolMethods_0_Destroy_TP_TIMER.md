# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800041c8`
- end: `0x1800041ff`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `55`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800037ac`
- `0x180008a9c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1800041d9`
- `KERNEL32!SetThreadpoolTimer` at `0x1800041d9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800041e8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800041e8`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800041f2`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800041f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x1800041c8  push    rbx
0x1800041ca  sub     rsp, 20h
0x1800041ce  mov     rbx, rcx
0x1800041d1  xor     r9d, r9d; msWindowLength
0x1800041d4  xor     r8d, r8d; msPeriod
0x1800041d7  xor     edx, edx; pftDueTime
0x1800041d9  call    cs:__imp_SetThreadpoolTimer
0x1800041df  nop
0x1800041e0  mov     edx, 1; fCancelPendingCallbacks
0x1800041e5  mov     rcx, rbx; pti
0x1800041e8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800041ee  nop
0x1800041ef  mov     rcx, rbx; pti
0x1800041f2  call    cs:__imp_CloseThreadpoolTimer
0x1800041f8  nop
0x1800041f9  add     rsp, 20h
0x1800041fd  pop     rbx
0x1800041fe  retn
```
