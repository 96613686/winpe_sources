# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000f660`
- end: `0x18000f694`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000eda8`
- `0x180013170`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f671`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f671`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f68d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f67f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f67f`

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
0x18000f660  push    rbx
0x18000f662  sub     rsp, 20h
0x18000f666  xor     r9d, r9d; msWindowLength
0x18000f669  xor     r8d, r8d; msPeriod
0x18000f66c  xor     edx, edx; pftDueTime
0x18000f66e  mov     rbx, rcx
0x18000f671  call    cs:__imp_SetThreadpoolTimer
0x18000f677  mov     edx, 1; fCancelPendingCallbacks
0x18000f67c  mov     rcx, rbx; pti
0x18000f67f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f685  mov     rcx, rbx
0x18000f688  add     rsp, 20h
0x18000f68c  pop     rbx
0x18000f68d  jmp     cs:__imp_CloseThreadpoolTimer
```
