# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180014528`
- end: `0x18001457b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b6bc`
- `0x1800147c4`
- `0x1800152e8`

## callees

- `0x180014528`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014545`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014545`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014564`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014564`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014557`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014557`

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
0x180014528  push    rbx
0x18001452a  sub     rsp, 20h
0x18001452e  mov     rbx, rcx
0x180014531  mov     rcx, [rcx+158h]; pti
0x180014538  test    rcx, rcx
0x18001453b  jz      short loc_180014575
0x18001453d  xor     r9d, r9d; msWindowLength
0x180014540  xor     r8d, r8d; msPeriod
0x180014543  xor     edx, edx; pftDueTime
0x180014545  call    cs:__imp_SetThreadpoolTimer
0x18001454b  mov     rcx, [rbx+158h]; pti
0x180014552  mov     edx, 1; fCancelPendingCallbacks
0x180014557  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001455d  mov     rcx, [rbx+158h]; pti
0x180014564  call    cs:__imp_CloseThreadpoolTimer
0x18001456a  mov     qword ptr [rbx+158h], 0
0x180014575  add     rsp, 20h
0x180014579  pop     rbx
0x18001457a  retn
```
