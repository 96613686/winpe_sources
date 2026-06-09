# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800070c0`
- end: `0x180007108`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `72`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006714`
- `0x18000f54c`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x1800070f4`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800070f4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800070e5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800070e5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800070d1`
- `KERNEL32!SetThreadpoolTimer` at `0x1800070d1`

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
0x1800070c0  push    rbx
0x1800070c2  sub     rsp, 20h
0x1800070c6  mov     rbx, rcx
0x1800070c9  xor     r9d, r9d; msWindowLength
0x1800070cc  xor     r8d, r8d; msPeriod
0x1800070cf  xor     edx, edx; pftDueTime
0x1800070d1  call    cs:__imp_SetThreadpoolTimer
0x1800070d8  nop     dword ptr [rax+rax+00h]
0x1800070dd  mov     edx, 1; fCancelPendingCallbacks
0x1800070e2  mov     rcx, rbx; pti
0x1800070e5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800070ec  nop     dword ptr [rax+rax+00h]
0x1800070f1  mov     rcx, rbx; pti
0x1800070f4  call    cs:__imp_CloseThreadpoolTimer
0x1800070fb  nop     dword ptr [rax+rax+00h]
0x180007100  nop
0x180007101  add     rsp, 20h
0x180007105  pop     rbx
0x180007106  retn
```
