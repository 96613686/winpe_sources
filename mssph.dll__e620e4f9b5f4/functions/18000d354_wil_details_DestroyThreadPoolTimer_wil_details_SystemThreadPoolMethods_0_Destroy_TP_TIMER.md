# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000d354`
- end: `0x18000d388`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d138`
- `0x18000d194`
- `0x18000d280`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d365`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d365`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d381`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d373`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d373`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x18000d354  push    rbx
0x18000d356  sub     rsp, 20h
0x18000d35a  xor     r9d, r9d; msWindowLength
0x18000d35d  xor     r8d, r8d; msPeriod
0x18000d360  xor     edx, edx; pftDueTime
0x18000d362  mov     rbx, rcx
0x18000d365  call    cs:__imp_SetThreadpoolTimer
0x18000d36b  mov     edx, 1; fCancelPendingCallbacks
0x18000d370  mov     rcx, rbx; pti
0x18000d373  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d379  mov     rcx, rbx
0x18000d37c  add     rsp, 20h
0x18000d380  pop     rbx
0x18000d381  jmp     cs:__imp_CloseThreadpoolTimer
```
