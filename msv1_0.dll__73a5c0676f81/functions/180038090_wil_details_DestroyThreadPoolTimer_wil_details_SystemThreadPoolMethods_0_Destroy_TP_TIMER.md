# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180038090`
- end: `0x1800380c4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002dae4`
- `0x18002db34`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800380a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800380a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800380bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800380af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800380af`

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
0x180038090  push    rbx
0x180038092  sub     rsp, 20h
0x180038096  xor     r9d, r9d; msWindowLength
0x180038099  xor     r8d, r8d; msPeriod
0x18003809c  xor     edx, edx; pftDueTime
0x18003809e  mov     rbx, rcx
0x1800380a1  call    cs:__imp_SetThreadpoolTimer
0x1800380a7  mov     edx, 1; fCancelPendingCallbacks
0x1800380ac  mov     rcx, rbx; pti
0x1800380af  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800380b5  mov     rcx, rbx
0x1800380b8  add     rsp, 20h
0x1800380bc  pop     rbx
0x1800380bd  jmp     cs:__imp_CloseThreadpoolTimer
```
