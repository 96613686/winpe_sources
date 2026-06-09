# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800057e8`
- end: `0x18000581c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000478c`
- `0x18000da34`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180005815`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005807`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005807`
- `KERNEL32!SetThreadpoolTimer` at `0x1800057f9`
- `KERNEL32!SetThreadpoolTimer` at `0x1800057f9`

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
0x1800057e8  push    rbx
0x1800057ea  sub     rsp, 20h
0x1800057ee  xor     r9d, r9d; msWindowLength
0x1800057f1  xor     r8d, r8d; msPeriod
0x1800057f4  xor     edx, edx; pftDueTime
0x1800057f6  mov     rbx, rcx
0x1800057f9  call    cs:__imp_SetThreadpoolTimer
0x1800057ff  mov     edx, 1; fCancelPendingCallbacks
0x180005804  mov     rcx, rbx; pti
0x180005807  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000580d  mov     rcx, rbx
0x180005810  add     rsp, 20h
0x180005814  pop     rbx
0x180005815  jmp     cs:__imp_CloseThreadpoolTimer
```
