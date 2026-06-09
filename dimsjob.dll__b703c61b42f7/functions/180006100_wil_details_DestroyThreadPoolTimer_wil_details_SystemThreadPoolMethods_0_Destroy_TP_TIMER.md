# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006100`
- end: `0x180006134`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000373c`
- `0x18000378c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006111`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006111`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000611f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000611f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000612d`

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
0x180006100  push    rbx
0x180006102  sub     rsp, 20h
0x180006106  xor     r9d, r9d; msWindowLength
0x180006109  xor     r8d, r8d; msPeriod
0x18000610c  xor     edx, edx; pftDueTime
0x18000610e  mov     rbx, rcx
0x180006111  call    cs:__imp_SetThreadpoolTimer
0x180006117  mov     edx, 1; fCancelPendingCallbacks
0x18000611c  mov     rcx, rbx; pti
0x18000611f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006125  mov     rcx, rbx
0x180006128  add     rsp, 20h
0x18000612c  pop     rbx
0x18000612d  jmp     cs:__imp_CloseThreadpoolTimer
```
