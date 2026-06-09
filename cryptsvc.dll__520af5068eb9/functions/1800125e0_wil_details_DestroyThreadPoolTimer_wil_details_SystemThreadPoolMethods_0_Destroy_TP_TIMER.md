# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800125e0`
- end: `0x180012614`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cf64`
- `0x18000cfb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800125ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800125ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800125f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800125f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001260d`

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
0x1800125e0  push    rbx
0x1800125e2  sub     rsp, 20h
0x1800125e6  xor     r9d, r9d; msWindowLength
0x1800125e9  xor     r8d, r8d; msPeriod
0x1800125ec  xor     edx, edx; pftDueTime
0x1800125ee  mov     rbx, rcx
0x1800125f1  call    cs:__imp_SetThreadpoolTimer
0x1800125f7  mov     edx, 1; fCancelPendingCallbacks
0x1800125fc  mov     rcx, rbx; pti
0x1800125ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012605  mov     rcx, rbx
0x180012608  add     rsp, 20h
0x18001260c  pop     rbx
0x18001260d  jmp     cs:__imp_CloseThreadpoolTimer
```
