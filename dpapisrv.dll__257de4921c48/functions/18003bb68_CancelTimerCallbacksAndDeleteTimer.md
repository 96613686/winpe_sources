# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18003bb68`
- end: `0x18003bbce`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003bfd4`
- `0x18003c31c`

## callees

- `0x18003bb68`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003bbb0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003bbb0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003bb85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003bb85`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003bb9d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003bb9d`

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
0x18003bb68  push    rbx
0x18003bb6a  sub     rsp, 20h
0x18003bb6e  mov     rbx, rcx
0x18003bb71  mov     rcx, [rcx+158h]; pti
0x18003bb78  test    rcx, rcx
0x18003bb7b  jz      short loc_18003BBC7
0x18003bb7d  xor     r9d, r9d; msWindowLength
0x18003bb80  xor     r8d, r8d; msPeriod
0x18003bb83  xor     edx, edx; pftDueTime
0x18003bb85  call    cs:__imp_SetThreadpoolTimer
0x18003bb8c  nop     dword ptr [rax+rax+00h]
0x18003bb91  mov     rcx, [rbx+158h]; pti
0x18003bb98  mov     edx, 1; fCancelPendingCallbacks
0x18003bb9d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003bba4  nop     dword ptr [rax+rax+00h]
0x18003bba9  mov     rcx, [rbx+158h]; pti
0x18003bbb0  call    cs:__imp_CloseThreadpoolTimer
0x18003bbb7  nop     dword ptr [rax+rax+00h]
0x18003bbbc  mov     qword ptr [rbx+158h], 0
0x18003bbc7  add     rsp, 20h
0x18003bbcb  pop     rbx
0x18003bbcc  retn
```
