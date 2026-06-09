# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180027274`
- end: `0x1800272a8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800074c8`
- `0x1800089dc`
- `0x180008bb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180027293`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180027293`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800272a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027285`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027285`

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
0x180027274  push    rbx
0x180027276  sub     rsp, 20h
0x18002727a  xor     r9d, r9d; msWindowLength
0x18002727d  xor     r8d, r8d; msPeriod
0x180027280  xor     edx, edx; pftDueTime
0x180027282  mov     rbx, rcx
0x180027285  call    cs:__imp_SetThreadpoolTimer
0x18002728b  mov     edx, 1; fCancelPendingCallbacks
0x180027290  mov     rcx, rbx; pti
0x180027293  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180027299  mov     rcx, rbx
0x18002729c  add     rsp, 20h
0x1800272a0  pop     rbx
0x1800272a1  jmp     cs:__imp_CloseThreadpoolTimer
```
