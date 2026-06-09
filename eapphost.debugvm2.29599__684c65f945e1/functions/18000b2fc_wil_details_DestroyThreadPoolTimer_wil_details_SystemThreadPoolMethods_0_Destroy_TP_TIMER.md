# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000b2fc`
- end: `0x18000b330`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a7e0`
- `0x18000d748`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b30d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b30d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b31b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b31b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b329`

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
0x18000b2fc  push    rbx
0x18000b2fe  sub     rsp, 20h
0x18000b302  xor     r9d, r9d; msWindowLength
0x18000b305  xor     r8d, r8d; msPeriod
0x18000b308  xor     edx, edx; pftDueTime
0x18000b30a  mov     rbx, rcx
0x18000b30d  call    cs:__imp_SetThreadpoolTimer
0x18000b313  mov     edx, 1; fCancelPendingCallbacks
0x18000b318  mov     rcx, rbx; pti
0x18000b31b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b321  mov     rcx, rbx
0x18000b324  add     rsp, 20h
0x18000b328  pop     rbx
0x18000b329  jmp     cs:__imp_CloseThreadpoolTimer
```
