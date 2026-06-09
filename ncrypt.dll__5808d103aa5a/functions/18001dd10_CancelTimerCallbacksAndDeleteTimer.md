# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18001dd10`
- end: `0x18001dd63`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180018938`
- `0x180018d80`

## callees

- `0x18001dd10`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dd2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dd2d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001dd4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001dd4c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001dd3f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001dd3f`

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
0x18001dd10  push    rbx
0x18001dd12  sub     rsp, 20h
0x18001dd16  mov     rbx, rcx
0x18001dd19  mov     rcx, [rcx+158h]; pti
0x18001dd20  test    rcx, rcx
0x18001dd23  jz      short loc_18001DD5D
0x18001dd25  xor     r9d, r9d; msWindowLength
0x18001dd28  xor     r8d, r8d; msPeriod
0x18001dd2b  xor     edx, edx; pftDueTime
0x18001dd2d  call    cs:__imp_SetThreadpoolTimer
0x18001dd33  mov     rcx, [rbx+158h]; pti
0x18001dd3a  mov     edx, 1; fCancelPendingCallbacks
0x18001dd3f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001dd45  mov     rcx, [rbx+158h]; pti
0x18001dd4c  call    cs:__imp_CloseThreadpoolTimer
0x18001dd52  mov     qword ptr [rbx+158h], 0
0x18001dd5d  add     rsp, 20h
0x18001dd61  pop     rbx
0x18001dd62  retn
```
