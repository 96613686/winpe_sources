# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000479c`
- end: `0x1800047d0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000473c`
- `0x180004758`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800047ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800047ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800047c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800047bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800047bb`

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
0x18000479c  push    rbx
0x18000479e  sub     rsp, 20h
0x1800047a2  xor     r9d, r9d; msWindowLength
0x1800047a5  xor     r8d, r8d; msPeriod
0x1800047a8  xor     edx, edx; pftDueTime
0x1800047aa  mov     rbx, rcx
0x1800047ad  call    cs:__imp_SetThreadpoolTimer
0x1800047b3  mov     edx, 1; fCancelPendingCallbacks
0x1800047b8  mov     rcx, rbx; pti
0x1800047bb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800047c1  mov     rcx, rbx
0x1800047c4  add     rsp, 20h
0x1800047c8  pop     rbx
0x1800047c9  jmp     cs:__imp_CloseThreadpoolTimer
```
