# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180007130`
- end: `0x180007183`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800073bc`
- `0x180007ed8`
- `0x180008090`

## callees

- `0x180007130`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000716c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000716c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000714d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000714d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000715f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000715f`

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
0x180007130  push    rbx
0x180007132  sub     rsp, 20h
0x180007136  mov     rbx, rcx
0x180007139  mov     rcx, [rcx+158h]; pti
0x180007140  test    rcx, rcx
0x180007143  jz      short loc_18000717D
0x180007145  xor     r9d, r9d; msWindowLength
0x180007148  xor     r8d, r8d; msPeriod
0x18000714b  xor     edx, edx; pftDueTime
0x18000714d  call    cs:__imp_SetThreadpoolTimer
0x180007153  mov     rcx, [rbx+158h]; pti
0x18000715a  mov     edx, 1; fCancelPendingCallbacks
0x18000715f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007165  mov     rcx, [rbx+158h]; pti
0x18000716c  call    cs:__imp_CloseThreadpoolTimer
0x180007172  mov     qword ptr [rbx+158h], 0
0x18000717d  add     rsp, 20h
0x180007181  pop     rbx
0x180007182  retn
```
