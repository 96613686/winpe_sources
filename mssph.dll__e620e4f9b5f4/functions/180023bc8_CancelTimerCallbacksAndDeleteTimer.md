# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180023bc8`
- end: `0x180023c1b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000df08`
- `0x180023ef8`

## callees

- `0x180023bc8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023be5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023be5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023c04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023c04`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023bf7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023bf7`

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
0x180023bc8  push    rbx
0x180023bca  sub     rsp, 20h
0x180023bce  mov     rbx, rcx
0x180023bd1  mov     rcx, [rcx+158h]; pti
0x180023bd8  test    rcx, rcx
0x180023bdb  jz      short loc_180023C15
0x180023bdd  xor     r9d, r9d; msWindowLength
0x180023be0  xor     r8d, r8d; msPeriod
0x180023be3  xor     edx, edx; pftDueTime
0x180023be5  call    cs:__imp_SetThreadpoolTimer
0x180023beb  mov     rcx, [rbx+158h]; pti
0x180023bf2  mov     edx, 1; fCancelPendingCallbacks
0x180023bf7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023bfd  mov     rcx, [rbx+158h]; pti
0x180023c04  call    cs:__imp_CloseThreadpoolTimer
0x180023c0a  mov     qword ptr [rbx+158h], 0
0x180023c15  add     rsp, 20h
0x180023c19  pop     rbx
0x180023c1a  retn
```
