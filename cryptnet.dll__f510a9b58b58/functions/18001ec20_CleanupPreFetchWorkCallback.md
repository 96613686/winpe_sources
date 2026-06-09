# _CleanupPreFetchWorkCallback

- ea: `0x18001ec20`
- end: `0x18001ec5c`
- name: `_CleanupPreFetchWorkCallback`
- size: `60`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PTP_TIMER *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001e660`
- `0x18001ec20`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ec48`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ec48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ec39`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ec39`

## pseudocode

```c
void __fastcall CleanupPreFetchWorkCallback(PTP_CALLBACK_INSTANCE Instance, PTP_TIMER *Context, PTP_WORK Work)
{
  if ( Context )
  {
    SetThreadpoolTimer(Context[3], 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(Context[3], 1);
    FreeCrlPreFetchEntry(Context);
  }
}

```

## disassembly

```asm
0x18001ec20  test    rdx, rdx
0x18001ec23  jz      short locret_18001EC5B
0x18001ec25  push    rbx
0x18001ec26  sub     rsp, 20h
0x18001ec2a  mov     rbx, rdx
0x18001ec2d  xor     r9d, r9d; msWindowLength
0x18001ec30  xor     r8d, r8d; msPeriod
0x18001ec33  xor     edx, edx; pftDueTime
0x18001ec35  mov     rcx, [rbx+18h]; pti
0x18001ec39  call    cs:__imp_SetThreadpoolTimer
0x18001ec3f  mov     rcx, [rbx+18h]; pti
0x18001ec43  mov     edx, 1; fCancelPendingCallbacks
0x18001ec48  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ec4e  mov     rcx, rbx; hMem
0x18001ec51  call    ?FreeCrlPreFetchEntry@@YAXPEAU_CRL_PRE_FETCH_ENTRY@@@Z; FreeCrlPreFetchEntry(_CRL_PRE_FETCH_ENTRY *)
0x18001ec56  add     rsp, 20h
0x18001ec5a  pop     rbx
0x18001ec5b  retn
```
