# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003ff30`
- end: `0x18003ff64`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180014360`
- `0x1800143b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003ff4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003ff4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003ff5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ff41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ff41`

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
0x18003ff30  push    rbx
0x18003ff32  sub     rsp, 20h
0x18003ff36  xor     r9d, r9d; msWindowLength
0x18003ff39  xor     r8d, r8d; msPeriod
0x18003ff3c  xor     edx, edx; pftDueTime
0x18003ff3e  mov     rbx, rcx
0x18003ff41  call    cs:__imp_SetThreadpoolTimer
0x18003ff47  mov     edx, 1; fCancelPendingCallbacks
0x18003ff4c  mov     rcx, rbx; pti
0x18003ff4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003ff55  mov     rcx, rbx
0x18003ff58  add     rsp, 20h
0x18003ff5c  pop     rbx
0x18003ff5d  jmp     cs:__imp_CloseThreadpoolTimer
```
