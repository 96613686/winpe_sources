# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18001e35c`
- end: `0x18001e3af`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e5f8`
- `0x18001f118`
- `0x18001f2d0`

## callees

- `0x18001e35c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001e379`
- `KERNEL32!SetThreadpoolTimer` at `0x18001e379`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001e398`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001e398`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001e38b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001e38b`

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
0x18001e35c  push    rbx
0x18001e35e  sub     rsp, 20h
0x18001e362  mov     rbx, rcx
0x18001e365  mov     rcx, [rcx+158h]; pti
0x18001e36c  test    rcx, rcx
0x18001e36f  jz      short loc_18001E3A9
0x18001e371  xor     r9d, r9d; msWindowLength
0x18001e374  xor     r8d, r8d; msPeriod
0x18001e377  xor     edx, edx; pftDueTime
0x18001e379  call    cs:__imp_SetThreadpoolTimer
0x18001e37f  mov     rcx, [rbx+158h]; pti
0x18001e386  mov     edx, 1; fCancelPendingCallbacks
0x18001e38b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001e391  mov     rcx, [rbx+158h]; pti
0x18001e398  call    cs:__imp_CloseThreadpoolTimer
0x18001e39e  mov     qword ptr [rbx+158h], 0
0x18001e3a9  add     rsp, 20h
0x18001e3ad  pop     rbx
0x18001e3ae  retn
```
