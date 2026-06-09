# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18005db38`
- end: `0x18005dba0`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18005d2b8`
- `0x18005daf8`

## callees

- `0x18005db38`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005db5c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005db5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005db87`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005db87`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005db74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005db74`

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
0x18005db38  push    rbx
0x18005db3a  sub     rsp, 20h
0x18005db3e  mov     rbx, rcx
0x18005db41  mov     rcx, [rcx+158h]; pti
0x18005db48  test    rcx, rcx
0x18005db4b  jnz     short loc_18005DB54
0x18005db4d  add     rsp, 20h
0x18005db51  pop     rbx
0x18005db52  retn
0x18005db54  xor     r9d, r9d; msWindowLength
0x18005db57  xor     r8d, r8d; msPeriod
0x18005db5a  xor     edx, edx; pftDueTime
0x18005db5c  call    cs:__imp_SetThreadpoolTimer
0x18005db63  nop     dword ptr [rax+rax+00h]
0x18005db68  mov     rcx, [rbx+158h]; pti
0x18005db6f  mov     edx, 1; fCancelPendingCallbacks
0x18005db74  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005db7b  nop     dword ptr [rax+rax+00h]
0x18005db80  mov     rcx, [rbx+158h]; pti
0x18005db87  call    cs:__imp_CloseThreadpoolTimer
0x18005db8e  nop     dword ptr [rax+rax+00h]
0x18005db93  mov     qword ptr [rbx+158h], 0
0x18005db9e  jmp     short loc_18005DB4D
```
