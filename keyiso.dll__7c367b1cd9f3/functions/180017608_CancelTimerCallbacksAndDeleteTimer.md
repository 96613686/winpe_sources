# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180017608`
- end: `0x18001765b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800179b4`
- `0x1800185ec`

## callees

- `0x180017608`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017644`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017644`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017637`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017637`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017625`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017625`

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
0x180017608  push    rbx
0x18001760a  sub     rsp, 20h
0x18001760e  mov     rbx, rcx
0x180017611  mov     rcx, [rcx+158h]; pti
0x180017618  test    rcx, rcx
0x18001761b  jz      short loc_180017655
0x18001761d  xor     r9d, r9d; msWindowLength
0x180017620  xor     r8d, r8d; msPeriod
0x180017623  xor     edx, edx; pftDueTime
0x180017625  call    cs:__imp_SetThreadpoolTimer
0x18001762b  mov     rcx, [rbx+158h]; pti
0x180017632  mov     edx, 1; fCancelPendingCallbacks
0x180017637  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001763d  mov     rcx, [rbx+158h]; pti
0x180017644  call    cs:__imp_CloseThreadpoolTimer
0x18001764a  mov     qword ptr [rbx+158h], 0
0x180017655  add     rsp, 20h
0x180017659  pop     rbx
0x18001765a  retn
```
