# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18002f734`
- end: `0x18002f79a`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002fa84`
- `0x180030280`

## callees

- `0x18002f734`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002f769`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002f769`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002f77c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002f77c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f751`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f751`

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
0x18002f734  push    rbx
0x18002f736  sub     rsp, 20h
0x18002f73a  mov     rbx, rcx
0x18002f73d  mov     rcx, [rcx+158h]; pti
0x18002f744  test    rcx, rcx
0x18002f747  jz      short loc_18002F793
0x18002f749  xor     r9d, r9d; msWindowLength
0x18002f74c  xor     r8d, r8d; msPeriod
0x18002f74f  xor     edx, edx; pftDueTime
0x18002f751  call    cs:__imp_SetThreadpoolTimer
0x18002f758  nop     dword ptr [rax+rax+00h]
0x18002f75d  mov     rcx, [rbx+158h]; pti
0x18002f764  mov     edx, 1; fCancelPendingCallbacks
0x18002f769  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002f770  nop     dword ptr [rax+rax+00h]
0x18002f775  mov     rcx, [rbx+158h]; pti
0x18002f77c  call    cs:__imp_CloseThreadpoolTimer
0x18002f783  nop     dword ptr [rax+rax+00h]
0x18002f788  mov     qword ptr [rbx+158h], 0
0x18002f793  add     rsp, 20h
0x18002f797  pop     rbx
0x18002f798  retn
```
