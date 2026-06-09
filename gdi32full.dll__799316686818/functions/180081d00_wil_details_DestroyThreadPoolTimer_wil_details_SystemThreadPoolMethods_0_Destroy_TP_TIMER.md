# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180081d00`
- end: `0x180081d34`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18004d3f8`
- `0x18004d448`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180081d2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180081d11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180081d11`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180081d1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180081d1f`

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
0x180081d00  push    rbx
0x180081d02  sub     rsp, 20h
0x180081d06  xor     r9d, r9d; msWindowLength
0x180081d09  xor     r8d, r8d; msPeriod
0x180081d0c  xor     edx, edx; pftDueTime
0x180081d0e  mov     rbx, rcx
0x180081d11  call    cs:__imp_SetThreadpoolTimer
0x180081d17  mov     edx, 1; fCancelPendingCallbacks
0x180081d1c  mov     rcx, rbx; pti
0x180081d1f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180081d25  mov     rcx, rbx
0x180081d28  add     rsp, 20h
0x180081d2c  pop     rbx
0x180081d2d  jmp     cs:__imp_CloseThreadpoolTimer
```
