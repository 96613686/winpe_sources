# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001772c`
- end: `0x180017760`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180015c00`
- `0x18001d698`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001773d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001773d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001774b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001774b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017759`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x18001772c  push    rbx
0x18001772e  sub     rsp, 20h
0x180017732  xor     r9d, r9d; msWindowLength
0x180017735  xor     r8d, r8d; msPeriod
0x180017738  xor     edx, edx; pftDueTime
0x18001773a  mov     rbx, rcx
0x18001773d  call    cs:__imp_SetThreadpoolTimer
0x180017743  mov     edx, 1; fCancelPendingCallbacks
0x180017748  mov     rcx, rbx; pti
0x18001774b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017751  mov     rcx, rbx
0x180017754  add     rsp, 20h
0x180017758  pop     rbx
0x180017759  jmp     cs:__imp_CloseThreadpoolTimer
```
