# Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(_TP_TIMER *)

- ea: `0x180140dc0`
- end: `0x180140df4`
- name: `?DeleteAsyncTimerAndUnloadLibrary@details@Concurrency@@YAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18014055c`
- `0x180144a38`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180140dd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180140dd1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180140ded`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180140ddf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180140ddf`

## pseudocode

```c
void __fastcall Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(PTP_TIMER pti, struct _TP_TIMER *a2)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180140dc0  push    rbx
0x180140dc2  sub     rsp, 20h
0x180140dc6  xor     r9d, r9d; msWindowLength
0x180140dc9  xor     r8d, r8d; msPeriod
0x180140dcc  xor     edx, edx; pftDueTime
0x180140dce  mov     rbx, rcx
0x180140dd1  call    cs:SetThreadpoolTimer
0x180140dd7  mov     edx, 1; fCancelPendingCallbacks
0x180140ddc  mov     rcx, rbx; pti
0x180140ddf  call    cs:WaitForThreadpoolTimerCallbacks
0x180140de5  mov     rcx, rbx
0x180140de8  add     rsp, 20h
0x180140dec  pop     rbx
0x180140ded  jmp     cs:CloseThreadpoolTimer
```
