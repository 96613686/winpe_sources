# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18000c3a8`
- end: `0x18000c40e`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c230`
- `0x18000c270`

## callees

- `0x18000c3a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c3f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c3f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c3dd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c3dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c3c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c3c5`

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
0x18000c3a8  push    rbx
0x18000c3aa  sub     rsp, 20h
0x18000c3ae  mov     rbx, rcx
0x18000c3b1  mov     rcx, [rcx+158h]; pti
0x18000c3b8  test    rcx, rcx
0x18000c3bb  jz      short loc_18000C407
0x18000c3bd  xor     r9d, r9d; msWindowLength
0x18000c3c0  xor     r8d, r8d; msPeriod
0x18000c3c3  xor     edx, edx; pftDueTime
0x18000c3c5  call    cs:__imp_SetThreadpoolTimer
0x18000c3cc  nop     dword ptr [rax+rax+00h]
0x18000c3d1  mov     rcx, [rbx+158h]; pti
0x18000c3d8  mov     edx, 1; fCancelPendingCallbacks
0x18000c3dd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c3e4  nop     dword ptr [rax+rax+00h]
0x18000c3e9  mov     rcx, [rbx+158h]; pti
0x18000c3f0  call    cs:__imp_CloseThreadpoolTimer
0x18000c3f7  nop     dword ptr [rax+rax+00h]
0x18000c3fc  mov     qword ptr [rbx+158h], 0
0x18000c407  add     rsp, 20h
0x18000c40b  pop     rbx
0x18000c40c  retn
```
