# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180078d90`
- end: `0x180078de3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180078eb0`
- `0x1800792bc`

## callees

- `0x180078d90`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180078dbf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180078dbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180078dad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180078dad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180078dcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180078dcc`

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
0x180078d90  push    rbx
0x180078d92  sub     rsp, 20h
0x180078d96  mov     rbx, rcx
0x180078d99  mov     rcx, [rcx+158h]; pti
0x180078da0  test    rcx, rcx
0x180078da3  jz      short loc_180078DDD
0x180078da5  xor     r9d, r9d; msWindowLength
0x180078da8  xor     r8d, r8d; msPeriod
0x180078dab  xor     edx, edx; pftDueTime
0x180078dad  call    cs:__imp_SetThreadpoolTimer
0x180078db3  mov     rcx, [rbx+158h]; pti
0x180078dba  mov     edx, 1; fCancelPendingCallbacks
0x180078dbf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180078dc5  mov     rcx, [rbx+158h]; pti
0x180078dcc  call    cs:__imp_CloseThreadpoolTimer
0x180078dd2  mov     qword ptr [rbx+158h], 0
0x180078ddd  add     rsp, 20h
0x180078de1  pop     rbx
0x180078de2  retn
```
