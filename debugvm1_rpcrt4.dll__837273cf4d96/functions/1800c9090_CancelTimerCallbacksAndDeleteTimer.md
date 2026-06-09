# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800c9090`
- end: `0x1800c90e3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a1fa0`
- `0x1800a2460`

## callees

- `0x1800c9090`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c90cc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c90cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c90bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c90bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c90ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c90ad`

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
0x1800c9090  push    rbx
0x1800c9092  sub     rsp, 20h
0x1800c9096  mov     rbx, rcx
0x1800c9099  mov     rcx, [rcx+158h]; pti
0x1800c90a0  test    rcx, rcx
0x1800c90a3  jz      short loc_1800C90DD
0x1800c90a5  xor     r9d, r9d; msWindowLength
0x1800c90a8  xor     r8d, r8d; msPeriod
0x1800c90ab  xor     edx, edx; pftDueTime
0x1800c90ad  call    cs:__imp_SetThreadpoolTimer
0x1800c90b3  mov     rcx, [rbx+158h]; pti
0x1800c90ba  mov     edx, 1; fCancelPendingCallbacks
0x1800c90bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c90c5  mov     rcx, [rbx+158h]; pti
0x1800c90cc  call    cs:__imp_CloseThreadpoolTimer
0x1800c90d2  mov     qword ptr [rbx+158h], 0
0x1800c90dd  add     rsp, 20h
0x1800c90e1  pop     rbx
0x1800c90e2  retn
```
