# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140006c1c`
- end: `0x140006c50`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140005e58`
- `0x14000e638`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006c2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006c2d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006c3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006c3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006c49`

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
0x140006c1c  push    rbx
0x140006c1e  sub     rsp, 20h
0x140006c22  xor     r9d, r9d; msWindowLength
0x140006c25  xor     r8d, r8d; msPeriod
0x140006c28  xor     edx, edx; pftDueTime
0x140006c2a  mov     rbx, rcx
0x140006c2d  call    cs:__imp_SetThreadpoolTimer
0x140006c33  mov     edx, 1; fCancelPendingCallbacks
0x140006c38  mov     rcx, rbx; pti
0x140006c3b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006c41  mov     rcx, rbx
0x140006c44  add     rsp, 20h
0x140006c48  pop     rbx
0x140006c49  jmp     cs:__imp_CloseThreadpoolTimer
```
