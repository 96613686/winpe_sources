# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180008550`
- end: `0x180008584`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007c68`
- `0x18000ca38`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008561`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008561`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000856f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000856f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000857d`

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
0x180008550  push    rbx
0x180008552  sub     rsp, 20h
0x180008556  xor     r9d, r9d; msWindowLength
0x180008559  xor     r8d, r8d; msPeriod
0x18000855c  xor     edx, edx; pftDueTime
0x18000855e  mov     rbx, rcx
0x180008561  call    cs:__imp_SetThreadpoolTimer
0x180008567  mov     edx, 1; fCancelPendingCallbacks
0x18000856c  mov     rcx, rbx; pti
0x18000856f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008575  mov     rcx, rbx
0x180008578  add     rsp, 20h
0x18000857c  pop     rbx
0x18000857d  jmp     cs:__imp_CloseThreadpoolTimer
```
