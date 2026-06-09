# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18003627c`
- end: `0x1800362e2`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d350`
- `0x18001d7b8`

## callees

- `0x18003627c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800362c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800362c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800362b1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800362b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036299`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036299`

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
0x18003627c  push    rbx
0x18003627e  sub     rsp, 20h
0x180036282  mov     rbx, rcx
0x180036285  mov     rcx, [rcx+158h]; pti
0x18003628c  test    rcx, rcx
0x18003628f  jz      short loc_1800362DB
0x180036291  xor     r9d, r9d; msWindowLength
0x180036294  xor     r8d, r8d; msPeriod
0x180036297  xor     edx, edx; pftDueTime
0x180036299  call    cs:__imp_SetThreadpoolTimer
0x1800362a0  nop     dword ptr [rax+rax+00h]
0x1800362a5  mov     rcx, [rbx+158h]; pti
0x1800362ac  mov     edx, 1; fCancelPendingCallbacks
0x1800362b1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800362b8  nop     dword ptr [rax+rax+00h]
0x1800362bd  mov     rcx, [rbx+158h]; pti
0x1800362c4  call    cs:__imp_CloseThreadpoolTimer
0x1800362cb  nop     dword ptr [rax+rax+00h]
0x1800362d0  mov     qword ptr [rbx+158h], 0
0x1800362db  add     rsp, 20h
0x1800362df  pop     rbx
0x1800362e0  retn
```
