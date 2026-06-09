# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000ea30`
- end: `0x18000ea64`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008730`
- `0x1800087e4`
- `0x18000886c`
- `0x180008980`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ea41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ea41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ea5d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ea4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ea4f`

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
0x18000ea30  push    rbx
0x18000ea32  sub     rsp, 20h
0x18000ea36  xor     r9d, r9d; msWindowLength
0x18000ea39  xor     r8d, r8d; msPeriod
0x18000ea3c  xor     edx, edx; pftDueTime
0x18000ea3e  mov     rbx, rcx
0x18000ea41  call    cs:__imp_SetThreadpoolTimer
0x18000ea47  mov     edx, 1; fCancelPendingCallbacks
0x18000ea4c  mov     rcx, rbx; pti
0x18000ea4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ea55  mov     rcx, rbx
0x18000ea58  add     rsp, 20h
0x18000ea5c  pop     rbx
0x18000ea5d  jmp     cs:__imp_CloseThreadpoolTimer
```
