# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180074dd4`
- end: `0x180074e08`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180018cf4`
- `0x180021318`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180074df3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180074df3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180074de5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180074de5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180074e01`

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
0x180074dd4  push    rbx
0x180074dd6  sub     rsp, 20h
0x180074dda  xor     r9d, r9d; msWindowLength
0x180074ddd  xor     r8d, r8d; msPeriod
0x180074de0  xor     edx, edx; pftDueTime
0x180074de2  mov     rbx, rcx
0x180074de5  call    cs:__imp_SetThreadpoolTimer
0x180074deb  mov     edx, 1; fCancelPendingCallbacks
0x180074df0  mov     rcx, rbx; pti
0x180074df3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180074df9  mov     rcx, rbx
0x180074dfc  add     rsp, 20h
0x180074e00  pop     rbx
0x180074e01  jmp     cs:__imp_CloseThreadpoolTimer
```
