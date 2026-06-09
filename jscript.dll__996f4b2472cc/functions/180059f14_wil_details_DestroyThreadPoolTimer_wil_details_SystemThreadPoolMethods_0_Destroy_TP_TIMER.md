# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180059f14`
- end: `0x180059f59`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18004b57c`
- `0x180054484`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180059f39`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180059f39`
- `KERNEL32!CloseThreadpoolTimer` at `0x180059f4d`
- `KERNEL32!SetThreadpoolTimer` at `0x180059f25`
- `KERNEL32!SetThreadpoolTimer` at `0x180059f25`

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
0x180059f14  push    rbx
0x180059f16  sub     rsp, 20h
0x180059f1a  xor     r9d, r9d; msWindowLength
0x180059f1d  xor     r8d, r8d; msPeriod
0x180059f20  xor     edx, edx; pftDueTime
0x180059f22  mov     rbx, rcx
0x180059f25  call    cs:__imp_SetThreadpoolTimer
0x180059f2c  nop     dword ptr [rax+rax+00h]
0x180059f31  mov     edx, 1; fCancelPendingCallbacks
0x180059f36  mov     rcx, rbx; pti
0x180059f39  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180059f40  nop     dword ptr [rax+rax+00h]
0x180059f45  mov     rcx, rbx
0x180059f48  add     rsp, 20h
0x180059f4c  pop     rbx
0x180059f4d  jmp     cs:__imp_CloseThreadpoolTimer
```
