# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400073fc`
- end: `0x140007430`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140006e48`
- `0x14000a874`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007429`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000741b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000741b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000740d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000740d`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x1400073fc  push    rbx
0x1400073fe  sub     rsp, 20h
0x140007402  xor     r9d, r9d; msWindowLength
0x140007405  xor     r8d, r8d; msPeriod
0x140007408  xor     edx, edx; pftDueTime
0x14000740a  mov     rbx, rcx
0x14000740d  call    cs:__imp_SetThreadpoolTimer
0x140007413  mov     edx, 1; fCancelPendingCallbacks
0x140007418  mov     rcx, rbx; pti
0x14000741b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007421  mov     rcx, rbx
0x140007424  add     rsp, 20h
0x140007428  pop     rbx
0x140007429  jmp     cs:__imp_CloseThreadpoolTimer
```
