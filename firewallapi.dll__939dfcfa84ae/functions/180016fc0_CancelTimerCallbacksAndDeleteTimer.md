# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180016fc0`
- end: `0x180017026`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180016ab8`
- `0x180016f80`

## callees

- `0x180016fc0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016fdd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016fdd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017008`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017008`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016ff5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016ff5`

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
0x180016fc0  push    rbx
0x180016fc2  sub     rsp, 20h
0x180016fc6  mov     rbx, rcx
0x180016fc9  mov     rcx, [rcx+158h]; pti
0x180016fd0  test    rcx, rcx
0x180016fd3  jz      short loc_18001701F
0x180016fd5  xor     r9d, r9d; msWindowLength
0x180016fd8  xor     r8d, r8d; msPeriod
0x180016fdb  xor     edx, edx; pftDueTime
0x180016fdd  call    cs:__imp_SetThreadpoolTimer
0x180016fe4  nop     dword ptr [rax+rax+00h]
0x180016fe9  mov     rcx, [rbx+158h]; pti
0x180016ff0  mov     edx, 1; fCancelPendingCallbacks
0x180016ff5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016ffc  nop     dword ptr [rax+rax+00h]
0x180017001  mov     rcx, [rbx+158h]; pti
0x180017008  call    cs:__imp_CloseThreadpoolTimer
0x18001700f  nop     dword ptr [rax+rax+00h]
0x180017014  mov     qword ptr [rbx+158h], 0
0x18001701f  add     rsp, 20h
0x180017023  pop     rbx
0x180017024  retn
```
