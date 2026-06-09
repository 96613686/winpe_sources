# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180059898`
- end: `0x1800598cc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(struct _TP_TIMER *threadpoolTimer)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180058818`
- `0x18005e5c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800598b7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800598b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800598c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800598a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800598a9`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(
        struct _TP_TIMER *threadpoolTimer)
{
  SetThreadpoolTimer(threadpoolTimer, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(threadpoolTimer, 1);
  CloseThreadpoolTimer(threadpoolTimer);
}

```

## disassembly

```asm
0x180059898  push    rbx
0x18005989a  sub     rsp, 20h
0x18005989e  xor     r9d, r9d; msWindowLength
0x1800598a1  xor     r8d, r8d; msPeriod
0x1800598a4  xor     edx, edx; pftDueTime
0x1800598a6  mov     rbx, threadpoolTimer
0x1800598a9  call    cs:__imp_SetThreadpoolTimer
0x1800598af  mov     edx, 1; fCancelPendingCallbacks
0x1800598b4  mov     threadpoolTimer, rbx; pti
0x1800598b7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800598bd  mov     threadpoolTimer, rbx
0x1800598c0  add     rsp, 20h
0x1800598c4  pop     rbx
0x1800598c5  jmp     cs:__imp_CloseThreadpoolTimer
```
