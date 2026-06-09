# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18001f6a4`
- end: `0x18001f6f7`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f5c0`
- `0x18002ef48`

## callees

- `0x18001f6a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f6c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f6c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f6e0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f6e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f6d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f6d3`

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
0x18001f6a4  push    rbx
0x18001f6a6  sub     rsp, 20h
0x18001f6aa  mov     rbx, rcx
0x18001f6ad  mov     rcx, [rcx+158h]; pti
0x18001f6b4  test    rcx, rcx
0x18001f6b7  jz      short loc_18001F6F1
0x18001f6b9  xor     r9d, r9d; msWindowLength
0x18001f6bc  xor     r8d, r8d; msPeriod
0x18001f6bf  xor     edx, edx; pftDueTime
0x18001f6c1  call    cs:__imp_SetThreadpoolTimer
0x18001f6c7  mov     rcx, [rbx+158h]; pti
0x18001f6ce  mov     edx, 1; fCancelPendingCallbacks
0x18001f6d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001f6d9  mov     rcx, [rbx+158h]; pti
0x18001f6e0  call    cs:__imp_CloseThreadpoolTimer
0x18001f6e6  mov     qword ptr [rbx+158h], 0
0x18001f6f1  add     rsp, 20h
0x18001f6f5  pop     rbx
0x18001f6f6  retn
```
