# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18001b8b0`
- end: `0x18001b916`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001bc44`
- `0x18001c920`

## callees

- `0x18001b8b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b8e5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b8e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b8f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b8f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b8cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b8cd`

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
0x18001b8b0  push    rbx
0x18001b8b2  sub     rsp, 20h
0x18001b8b6  mov     rbx, rcx
0x18001b8b9  mov     rcx, [rcx+158h]; pti
0x18001b8c0  test    rcx, rcx
0x18001b8c3  jz      short loc_18001B90F
0x18001b8c5  xor     r9d, r9d; msWindowLength
0x18001b8c8  xor     r8d, r8d; msPeriod
0x18001b8cb  xor     edx, edx; pftDueTime
0x18001b8cd  call    cs:__imp_SetThreadpoolTimer
0x18001b8d4  nop     dword ptr [rax+rax+00h]
0x18001b8d9  mov     rcx, [rbx+158h]; pti
0x18001b8e0  mov     edx, 1; fCancelPendingCallbacks
0x18001b8e5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001b8ec  nop     dword ptr [rax+rax+00h]
0x18001b8f1  mov     rcx, [rbx+158h]; pti
0x18001b8f8  call    cs:__imp_CloseThreadpoolTimer
0x18001b8ff  nop     dword ptr [rax+rax+00h]
0x18001b904  mov     qword ptr [rbx+158h], 0
0x18001b90f  add     rsp, 20h
0x18001b913  pop     rbx
0x18001b914  retn
```
