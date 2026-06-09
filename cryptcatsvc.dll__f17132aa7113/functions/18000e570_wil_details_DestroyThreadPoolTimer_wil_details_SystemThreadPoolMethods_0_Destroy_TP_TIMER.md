# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000e570`
- end: `0x18000e5a4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a0c8`
- `0x18000a118`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e58f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e58f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e59d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e581`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e581`

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
0x18000e570  push    rbx
0x18000e572  sub     rsp, 20h
0x18000e576  xor     r9d, r9d; msWindowLength
0x18000e579  xor     r8d, r8d; msPeriod
0x18000e57c  xor     edx, edx; pftDueTime
0x18000e57e  mov     rbx, rcx
0x18000e581  call    cs:__imp_SetThreadpoolTimer
0x18000e587  mov     edx, 1; fCancelPendingCallbacks
0x18000e58c  mov     rcx, rbx; pti
0x18000e58f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e595  mov     rcx, rbx
0x18000e598  add     rsp, 20h
0x18000e59c  pop     rbx
0x18000e59d  jmp     cs:__imp_CloseThreadpoolTimer
```
