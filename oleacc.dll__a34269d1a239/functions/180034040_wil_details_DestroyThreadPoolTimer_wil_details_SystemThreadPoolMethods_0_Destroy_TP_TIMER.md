# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180034040`
- end: `0x180034074`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18003345c`
- `0x18003b03c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003406d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003405f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003405f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034051`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034051`

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
0x180034040  push    rbx
0x180034042  sub     rsp, 20h
0x180034046  xor     r9d, r9d; msWindowLength
0x180034049  xor     r8d, r8d; msPeriod
0x18003404c  xor     edx, edx; pftDueTime
0x18003404e  mov     rbx, rcx
0x180034051  call    cs:__imp_SetThreadpoolTimer
0x180034057  mov     edx, 1; fCancelPendingCallbacks
0x18003405c  mov     rcx, rbx; pti
0x18003405f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180034065  mov     rcx, rbx
0x180034068  add     rsp, 20h
0x18003406c  pop     rbx
0x18003406d  jmp     cs:__imp_CloseThreadpoolTimer
```
