# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180017ea0`
- end: `0x180017ed4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180017930`
- `0x18001ad4c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017ecd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017eb1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017eb1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017ebf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017ebf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180017ea0  push    rbx
0x180017ea2  sub     rsp, 20h
0x180017ea6  xor     r9d, r9d; msWindowLength
0x180017ea9  xor     r8d, r8d; msPeriod
0x180017eac  xor     edx, edx; pftDueTime
0x180017eae  mov     rbx, rcx
0x180017eb1  call    cs:__imp_SetThreadpoolTimer
0x180017eb7  mov     edx, 1; fCancelPendingCallbacks
0x180017ebc  mov     rcx, rbx; pti
0x180017ebf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017ec5  mov     rcx, rbx
0x180017ec8  add     rsp, 20h
0x180017ecc  pop     rbx
0x180017ecd  jmp     cs:__imp_CloseThreadpoolTimer
```
