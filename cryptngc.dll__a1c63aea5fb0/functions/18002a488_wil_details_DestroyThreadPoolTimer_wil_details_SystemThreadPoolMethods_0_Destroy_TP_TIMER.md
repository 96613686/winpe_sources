# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002a488`
- end: `0x18002a4bc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800104e0`
- `0x180017280`
- `0x18002ceb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002a499`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002a499`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002a4b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002a4a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002a4a7`

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
0x18002a488  push    rbx
0x18002a48a  sub     rsp, 20h
0x18002a48e  xor     r9d, r9d; msWindowLength
0x18002a491  xor     r8d, r8d; msPeriod
0x18002a494  xor     edx, edx; pftDueTime
0x18002a496  mov     rbx, rcx
0x18002a499  call    cs:__imp_SetThreadpoolTimer
0x18002a49f  mov     edx, 1; fCancelPendingCallbacks
0x18002a4a4  mov     rcx, rbx; pti
0x18002a4a7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002a4ad  mov     rcx, rbx
0x18002a4b0  add     rsp, 20h
0x18002a4b4  pop     rbx
0x18002a4b5  jmp     cs:__imp_CloseThreadpoolTimer
```
