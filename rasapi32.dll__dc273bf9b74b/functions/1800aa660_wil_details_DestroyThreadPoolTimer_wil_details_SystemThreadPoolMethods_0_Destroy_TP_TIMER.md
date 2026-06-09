# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800aa660`
- end: `0x1800aa694`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800a9a88`
- `0x1800aeb38`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aa671`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aa671`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aa67f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aa67f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aa68d`

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
0x1800aa660  push    rbx
0x1800aa662  sub     rsp, 20h
0x1800aa666  xor     r9d, r9d; msWindowLength
0x1800aa669  xor     r8d, r8d; msPeriod
0x1800aa66c  xor     edx, edx; pftDueTime
0x1800aa66e  mov     rbx, rcx
0x1800aa671  call    cs:__imp_SetThreadpoolTimer
0x1800aa677  mov     edx, 1; fCancelPendingCallbacks
0x1800aa67c  mov     rcx, rbx; pti
0x1800aa67f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800aa685  mov     rcx, rbx
0x1800aa688  add     rsp, 20h
0x1800aa68c  pop     rbx
0x1800aa68d  jmp     cs:__imp_CloseThreadpoolTimer
```
