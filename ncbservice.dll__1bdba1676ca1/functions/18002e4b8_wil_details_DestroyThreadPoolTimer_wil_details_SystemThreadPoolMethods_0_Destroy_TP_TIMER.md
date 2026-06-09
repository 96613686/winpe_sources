# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002e4b8`
- end: `0x18002e4ec`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a378`
- `0x18001a3c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002e4d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002e4d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e4c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e4c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002e4e5`

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
0x18002e4b8  push    rbx
0x18002e4ba  sub     rsp, 20h
0x18002e4be  xor     r9d, r9d; msWindowLength
0x18002e4c1  xor     r8d, r8d; msPeriod
0x18002e4c4  xor     edx, edx; pftDueTime
0x18002e4c6  mov     rbx, rcx
0x18002e4c9  call    cs:__imp_SetThreadpoolTimer
0x18002e4cf  mov     edx, 1; fCancelPendingCallbacks
0x18002e4d4  mov     rcx, rbx; pti
0x18002e4d7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002e4dd  mov     rcx, rbx
0x18002e4e0  add     rsp, 20h
0x18002e4e4  pop     rbx
0x18002e4e5  jmp     cs:__imp_CloseThreadpoolTimer
```
