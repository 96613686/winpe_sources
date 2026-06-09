# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003b2d0`
- end: `0x18003b304`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800218f0`
- `0x180021a6c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b2e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b2e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003b2fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b2ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b2ef`

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
0x18003b2d0  push    rbx
0x18003b2d2  sub     rsp, 20h
0x18003b2d6  xor     r9d, r9d; msWindowLength
0x18003b2d9  xor     r8d, r8d; msPeriod
0x18003b2dc  xor     edx, edx; pftDueTime
0x18003b2de  mov     rbx, rcx
0x18003b2e1  call    cs:__imp_SetThreadpoolTimer
0x18003b2e7  mov     edx, 1; fCancelPendingCallbacks
0x18003b2ec  mov     rcx, rbx; pti
0x18003b2ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003b2f5  mov     rcx, rbx
0x18003b2f8  add     rsp, 20h
0x18003b2fc  pop     rbx
0x18003b2fd  jmp     cs:__imp_CloseThreadpoolTimer
```
