# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180046870`
- end: `0x1800468c3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180046b8c`
- `0x180047780`

## callees

- `0x180046870`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004689f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004689f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004688d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004688d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800468ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800468ac`

## pseudocode

```c
void __fastcall CancelTimerCallbacksAndDeleteTimer(__int64 a1)
{
  struct _TP_TIMER *v2; // rcx

  v2 = *(struct _TP_TIMER **)(a1 + 344);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(a1 + 344), 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)(a1 + 344));
    *(_QWORD *)(a1 + 344) = 0;
  }
}

```

## disassembly

```asm
0x180046870  push    rbx
0x180046872  sub     rsp, 20h
0x180046876  mov     rbx, rcx
0x180046879  mov     rcx, [rcx+158h]; pti
0x180046880  test    rcx, rcx
0x180046883  jz      short loc_1800468BD
0x180046885  xor     r9d, r9d; msWindowLength
0x180046888  xor     r8d, r8d; msPeriod
0x18004688b  xor     edx, edx; pftDueTime
0x18004688d  call    cs:__imp_SetThreadpoolTimer
0x180046893  mov     rcx, [rbx+158h]; pti
0x18004689a  mov     edx, 1; fCancelPendingCallbacks
0x18004689f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800468a5  mov     rcx, [rbx+158h]; pti
0x1800468ac  call    cs:__imp_CloseThreadpoolTimer
0x1800468b2  mov     qword ptr [rbx+158h], 0
0x1800468bd  add     rsp, 20h
0x1800468c1  pop     rbx
0x1800468c2  retn
```
