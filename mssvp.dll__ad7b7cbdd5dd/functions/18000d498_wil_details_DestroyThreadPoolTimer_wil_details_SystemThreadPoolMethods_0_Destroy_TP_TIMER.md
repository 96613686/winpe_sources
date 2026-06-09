# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000d498`
- end: `0x18000d4cc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a5ac`
- `0x1800130a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d4a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d4a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d4c5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d4b7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d4b7`

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
0x18000d498  push    rbx
0x18000d49a  sub     rsp, 20h
0x18000d49e  xor     r9d, r9d; msWindowLength
0x18000d4a1  xor     r8d, r8d; msPeriod
0x18000d4a4  xor     edx, edx; pftDueTime
0x18000d4a6  mov     rbx, rcx
0x18000d4a9  call    cs:__imp_SetThreadpoolTimer
0x18000d4af  mov     edx, 1; fCancelPendingCallbacks
0x18000d4b4  mov     rcx, rbx; pti
0x18000d4b7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d4bd  mov     rcx, rbx
0x18000d4c0  add     rsp, 20h
0x18000d4c4  pop     rbx
0x18000d4c5  jmp     cs:__imp_CloseThreadpoolTimer
```
