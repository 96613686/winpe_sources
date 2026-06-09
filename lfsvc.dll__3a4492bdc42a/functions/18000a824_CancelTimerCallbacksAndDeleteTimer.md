# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18000a824`
- end: `0x18000a877`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e20`
- `0x180002f60`
- `0x18000b104`

## callees

- `0x18000a824`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a841`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a841`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a853`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a853`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a860`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a860`

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
0x18000a824  push    rbx
0x18000a826  sub     rsp, 20h
0x18000a82a  mov     rbx, rcx
0x18000a82d  mov     rcx, [rcx+158h]; pti
0x18000a834  test    rcx, rcx
0x18000a837  jz      short loc_18000A871
0x18000a839  xor     r9d, r9d; msWindowLength
0x18000a83c  xor     r8d, r8d; msPeriod
0x18000a83f  xor     edx, edx; pftDueTime
0x18000a841  call    cs:__imp_SetThreadpoolTimer
0x18000a847  mov     rcx, [rbx+158h]; pti
0x18000a84e  mov     edx, 1; fCancelPendingCallbacks
0x18000a853  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a859  mov     rcx, [rbx+158h]; pti
0x18000a860  call    cs:__imp_CloseThreadpoolTimer
0x18000a866  mov     qword ptr [rbx+158h], 0
0x18000a871  add     rsp, 20h
0x18000a875  pop     rbx
0x18000a876  retn
```
