# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180013164`
- end: `0x180013198`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011554`
- `0x1800174b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013183`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013183`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013175`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013175`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013191`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180013164  push    rbx
0x180013166  sub     rsp, 20h
0x18001316a  xor     r9d, r9d; msWindowLength
0x18001316d  xor     r8d, r8d; msPeriod
0x180013170  xor     edx, edx; pftDueTime
0x180013172  mov     rbx, rcx
0x180013175  call    cs:__imp_SetThreadpoolTimer
0x18001317b  mov     edx, 1; fCancelPendingCallbacks
0x180013180  mov     rcx, rbx; pti
0x180013183  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013189  mov     rcx, rbx
0x18001318c  add     rsp, 20h
0x180013190  pop     rbx
0x180013191  jmp     cs:__imp_CloseThreadpoolTimer
```
