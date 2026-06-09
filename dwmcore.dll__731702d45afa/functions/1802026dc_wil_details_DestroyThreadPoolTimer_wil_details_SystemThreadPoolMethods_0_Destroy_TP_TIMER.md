# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1802026dc`
- end: `0x180202710`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180202424`
- `0x180202548`
- `0x180202598`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802026fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802026fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180202709`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1802026ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1802026ed`

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
0x1802026dc  push    rbx
0x1802026de  sub     rsp, 20h
0x1802026e2  xor     r9d, r9d; msWindowLength
0x1802026e5  xor     r8d, r8d; msPeriod
0x1802026e8  xor     edx, edx; pftDueTime
0x1802026ea  mov     rbx, rcx
0x1802026ed  call    cs:__imp_SetThreadpoolTimer
0x1802026f3  mov     edx, 1; fCancelPendingCallbacks
0x1802026f8  mov     rcx, rbx; pti
0x1802026fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180202701  mov     rcx, rbx
0x180202704  add     rsp, 20h
0x180202708  pop     rbx
0x180202709  jmp     cs:__imp_CloseThreadpoolTimer
```
