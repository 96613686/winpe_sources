# CancelTimerCallbacksAndDeleteTimer

- ea: `0x14001d544`
- end: `0x14001d597`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d664`
- `0x14001ddc0`

## callees

- `0x14001d544`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001d580`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001d580`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001d573`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001d573`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001d561`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001d561`

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
0x14001d544  push    rbx
0x14001d546  sub     rsp, 20h
0x14001d54a  mov     rbx, rcx
0x14001d54d  mov     rcx, [rcx+158h]; pti
0x14001d554  test    rcx, rcx
0x14001d557  jz      short loc_14001D591
0x14001d559  xor     r9d, r9d; msWindowLength
0x14001d55c  xor     r8d, r8d; msPeriod
0x14001d55f  xor     edx, edx; pftDueTime
0x14001d561  call    cs:__imp_SetThreadpoolTimer
0x14001d567  mov     rcx, [rbx+158h]; pti
0x14001d56e  mov     edx, 1; fCancelPendingCallbacks
0x14001d573  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14001d579  mov     rcx, [rbx+158h]; pti
0x14001d580  call    cs:__imp_CloseThreadpoolTimer
0x14001d586  mov     qword ptr [rbx+158h], 0
0x14001d591  add     rsp, 20h
0x14001d595  pop     rbx
0x14001d596  retn
```
