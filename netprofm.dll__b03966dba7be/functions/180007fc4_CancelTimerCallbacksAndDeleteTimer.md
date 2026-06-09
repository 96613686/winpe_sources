# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180007fc4`
- end: `0x180008017`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007718`
- `0x180007b94`

## callees

- `0x180007fc4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007fe1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007fe1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007ff3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007ff3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008000`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008000`

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
0x180007fc4  push    rbx
0x180007fc6  sub     rsp, 20h
0x180007fca  mov     rbx, rcx
0x180007fcd  mov     rcx, [rcx+158h]; pti
0x180007fd4  test    rcx, rcx
0x180007fd7  jz      short loc_180008011
0x180007fd9  xor     r9d, r9d; msWindowLength
0x180007fdc  xor     r8d, r8d; msPeriod
0x180007fdf  xor     edx, edx; pftDueTime
0x180007fe1  call    cs:__imp_SetThreadpoolTimer
0x180007fe7  mov     rcx, [rbx+158h]; pti
0x180007fee  mov     edx, 1; fCancelPendingCallbacks
0x180007ff3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007ff9  mov     rcx, [rbx+158h]; pti
0x180008000  call    cs:__imp_CloseThreadpoolTimer
0x180008006  mov     qword ptr [rbx+158h], 0
0x180008011  add     rsp, 20h
0x180008015  pop     rbx
0x180008016  retn
```
