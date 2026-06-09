# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800658dc`
- end: `0x18006592f`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800402ac`
- `0x180065ca0`

## callees

- `0x1800658dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006590b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006590b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800658f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800658f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180065918`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180065918`

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
0x1800658dc  push    rbx
0x1800658de  sub     rsp, 20h
0x1800658e2  mov     rbx, rcx
0x1800658e5  mov     rcx, [rcx+158h]; pti
0x1800658ec  test    rcx, rcx
0x1800658ef  jz      short loc_180065929
0x1800658f1  xor     r9d, r9d; msWindowLength
0x1800658f4  xor     r8d, r8d; msPeriod
0x1800658f7  xor     edx, edx; pftDueTime
0x1800658f9  call    cs:__imp_SetThreadpoolTimer
0x1800658ff  mov     rcx, [rbx+158h]; pti
0x180065906  mov     edx, 1; fCancelPendingCallbacks
0x18006590b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180065911  mov     rcx, [rbx+158h]; pti
0x180065918  call    cs:__imp_CloseThreadpoolTimer
0x18006591e  mov     qword ptr [rbx+158h], 0
0x180065929  add     rsp, 20h
0x18006592d  pop     rbx
0x18006592e  retn
```
