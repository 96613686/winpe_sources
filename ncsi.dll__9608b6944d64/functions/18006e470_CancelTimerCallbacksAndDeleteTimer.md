# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18006e470`
- end: `0x18006e4c3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180043614`
- `0x18006e83c`

## callees

- `0x18006e470`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006e48d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006e48d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006e4ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006e4ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006e49f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006e49f`

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
0x18006e470  push    rbx
0x18006e472  sub     rsp, 20h
0x18006e476  mov     rbx, rcx
0x18006e479  mov     rcx, [rcx+158h]; pti
0x18006e480  test    rcx, rcx
0x18006e483  jz      short loc_18006E4BD
0x18006e485  xor     r9d, r9d; msWindowLength
0x18006e488  xor     r8d, r8d; msPeriod
0x18006e48b  xor     edx, edx; pftDueTime
0x18006e48d  call    cs:__imp_SetThreadpoolTimer
0x18006e493  mov     rcx, [rbx+158h]; pti
0x18006e49a  mov     edx, 1; fCancelPendingCallbacks
0x18006e49f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006e4a5  mov     rcx, [rbx+158h]; pti
0x18006e4ac  call    cs:__imp_CloseThreadpoolTimer
0x18006e4b2  mov     qword ptr [rbx+158h], 0
0x18006e4bd  add     rsp, 20h
0x18006e4c1  pop     rbx
0x18006e4c2  retn
```
