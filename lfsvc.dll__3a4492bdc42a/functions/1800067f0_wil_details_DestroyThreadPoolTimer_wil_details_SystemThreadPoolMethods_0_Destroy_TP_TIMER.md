# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800067f0`
- end: `0x180006824`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c7c`
- `0x180002d5c`
- `0x1800033b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006801`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006801`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000680f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000680f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000681d`

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
0x1800067f0  push    rbx
0x1800067f2  sub     rsp, 20h
0x1800067f6  xor     r9d, r9d; msWindowLength
0x1800067f9  xor     r8d, r8d; msPeriod
0x1800067fc  xor     edx, edx; pftDueTime
0x1800067fe  mov     rbx, rcx
0x180006801  call    cs:__imp_SetThreadpoolTimer
0x180006807  mov     edx, 1; fCancelPendingCallbacks
0x18000680c  mov     rcx, rbx; pti
0x18000680f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006815  mov     rcx, rbx
0x180006818  add     rsp, 20h
0x18000681c  pop     rbx
0x18000681d  jmp     cs:__imp_CloseThreadpoolTimer
```
