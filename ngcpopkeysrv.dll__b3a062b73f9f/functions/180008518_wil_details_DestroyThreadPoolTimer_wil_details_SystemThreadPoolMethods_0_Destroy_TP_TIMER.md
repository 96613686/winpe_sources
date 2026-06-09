# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180008518`
- end: `0x18000854d`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000792c`
- `0x18000c91c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008529`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008529`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008540`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008540`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008537`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008537`

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
0x180008518  push    rbx
0x18000851a  sub     rsp, 20h
0x18000851e  mov     rbx, rcx
0x180008521  xor     r9d, r9d; msWindowLength
0x180008524  xor     r8d, r8d; msPeriod
0x180008527  xor     edx, edx; pftDueTime
0x180008529  call    cs:__imp_SetThreadpoolTimer
0x18000852f  mov     edx, 1; fCancelPendingCallbacks
0x180008534  mov     rcx, rbx; pti
0x180008537  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000853d  mov     rcx, rbx; pti
0x180008540  call    cs:__imp_CloseThreadpoolTimer
0x180008546  nop
0x180008547  add     rsp, 20h
0x18000854b  pop     rbx
0x18000854c  retn
```
