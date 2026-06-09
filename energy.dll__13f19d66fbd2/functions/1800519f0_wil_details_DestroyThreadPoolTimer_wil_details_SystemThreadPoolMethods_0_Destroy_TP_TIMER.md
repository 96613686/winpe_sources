# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800519f0`
- end: `0x180051a24`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18003e400`
- `0x18003e450`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180051a1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051a01`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051a01`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051a0f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051a0f`

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
0x1800519f0  push    rbx
0x1800519f2  sub     rsp, 20h
0x1800519f6  xor     r9d, r9d; msWindowLength
0x1800519f9  xor     r8d, r8d; msPeriod
0x1800519fc  xor     edx, edx; pftDueTime
0x1800519fe  mov     rbx, rcx
0x180051a01  call    cs:__imp_SetThreadpoolTimer
0x180051a07  mov     edx, 1; fCancelPendingCallbacks
0x180051a0c  mov     rcx, rbx; pti
0x180051a0f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180051a15  mov     rcx, rbx
0x180051a18  add     rsp, 20h
0x180051a1c  pop     rbx
0x180051a1d  jmp     cs:__imp_CloseThreadpoolTimer
```
