# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180005c00`
- end: `0x180005c34`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005304`
- `0x180009dcc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c11`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c1f`

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
0x180005c00  push    rbx
0x180005c02  sub     rsp, 20h
0x180005c06  xor     r9d, r9d; msWindowLength
0x180005c09  xor     r8d, r8d; msPeriod
0x180005c0c  xor     edx, edx; pftDueTime
0x180005c0e  mov     rbx, rcx
0x180005c11  call    cs:__imp_SetThreadpoolTimer
0x180005c17  mov     edx, 1; fCancelPendingCallbacks
0x180005c1c  mov     rcx, rbx; pti
0x180005c1f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005c25  mov     rcx, rbx
0x180005c28  add     rsp, 20h
0x180005c2c  pop     rbx
0x180005c2d  jmp     cs:__imp_CloseThreadpoolTimer
```
