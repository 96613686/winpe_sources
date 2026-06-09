# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180003bdc`
- end: `0x180003c2f`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e78`
- `0x180004998`
- `0x180004b50`

## callees

- `0x180003bdc`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003c0b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003c0b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003c18`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003c18`
- `KERNEL32!SetThreadpoolTimer` at `0x180003bf9`
- `KERNEL32!SetThreadpoolTimer` at `0x180003bf9`

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
0x180003bdc  push    rbx
0x180003bde  sub     rsp, 20h
0x180003be2  mov     rbx, rcx
0x180003be5  mov     rcx, [rcx+158h]; pti
0x180003bec  test    rcx, rcx
0x180003bef  jz      short loc_180003C29
0x180003bf1  xor     r9d, r9d; msWindowLength
0x180003bf4  xor     r8d, r8d; msPeriod
0x180003bf7  xor     edx, edx; pftDueTime
0x180003bf9  call    cs:__imp_SetThreadpoolTimer
0x180003bff  mov     rcx, [rbx+158h]; pti
0x180003c06  mov     edx, 1; fCancelPendingCallbacks
0x180003c0b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003c11  mov     rcx, [rbx+158h]; pti
0x180003c18  call    cs:__imp_CloseThreadpoolTimer
0x180003c1e  mov     qword ptr [rbx+158h], 0
0x180003c29  add     rsp, 20h
0x180003c2d  pop     rbx
0x180003c2e  retn
```
