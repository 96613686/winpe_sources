# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1801cdbd8`
- end: `0x1801cdc33`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1801b3a48`
- `0x1801d2954`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1801cdc0e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1801cdc0e`
- `KERNEL32!CloseThreadpoolTimer` at `0x1801cdc20`
- `KERNEL32!CloseThreadpoolTimer` at `0x1801cdc20`
- `KERNEL32!SetThreadpoolTimer` at `0x1801cdbf7`
- `KERNEL32!SetThreadpoolTimer` at `0x1801cdbf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(
        struct _TP_TIMER *a1)
{
  SetThreadpoolTimer(a1, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(a1, 1);
  CloseThreadpoolTimer(a1);
}

```

## disassembly

```asm
0x1801cdbd8  mov     [rsp+pti], rcx
0x1801cdbdd  sub     rsp, 38h
0x1801cdbe1  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1801cdbea  xor     r9d, r9d; msWindowLength
0x1801cdbed  xor     r8d, r8d; msPeriod
0x1801cdbf0  xor     edx, edx; pftDueTime
0x1801cdbf2  mov     rcx, [rsp+38h+pti]; pti
0x1801cdbf7  call    cs:__imp_SetThreadpoolTimer
0x1801cdbfe  nop     dword ptr [rax+rax+00h]
0x1801cdc03  nop
0x1801cdc04  mov     edx, 1; fCancelPendingCallbacks
0x1801cdc09  mov     rcx, [rsp+38h+pti]; pti
0x1801cdc0e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1801cdc15  nop     dword ptr [rax+rax+00h]
0x1801cdc1a  nop
0x1801cdc1b  mov     rcx, [rsp+38h+pti]; pti
0x1801cdc20  call    cs:__imp_CloseThreadpoolTimer
0x1801cdc27  nop     dword ptr [rax+rax+00h]
0x1801cdc2c  nop
0x1801cdc2d  add     rsp, 38h
0x1801cdc31  retn
```
