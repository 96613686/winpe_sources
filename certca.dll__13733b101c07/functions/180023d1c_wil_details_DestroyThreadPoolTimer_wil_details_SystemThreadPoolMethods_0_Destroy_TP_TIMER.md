# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180023d1c`
- end: `0x180023d51`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `53`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800233b4`
- `0x180026c30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023d3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023d3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023d44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023d44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023d2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023d2d`

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
0x180023d1c  push    rbx
0x180023d1e  sub     rsp, 20h
0x180023d22  mov     rbx, rcx
0x180023d25  xor     r9d, r9d; msWindowLength
0x180023d28  xor     r8d, r8d; msPeriod
0x180023d2b  xor     edx, edx; pftDueTime
0x180023d2d  call    cs:__imp_SetThreadpoolTimer
0x180023d33  mov     edx, 1; fCancelPendingCallbacks
0x180023d38  mov     rcx, rbx; pti
0x180023d3b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023d41  mov     rcx, rbx; pti
0x180023d44  call    cs:__imp_CloseThreadpoolTimer
0x180023d4a  nop
0x180023d4b  add     rsp, 20h
0x180023d4f  pop     rbx
0x180023d50  retn
```
