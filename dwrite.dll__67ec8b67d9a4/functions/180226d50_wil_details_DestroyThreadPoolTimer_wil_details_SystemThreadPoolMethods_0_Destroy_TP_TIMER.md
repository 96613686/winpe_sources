# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180226d50`
- end: `0x180226d84`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1801e5850`
- `0x18020d02c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180226d7d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180226d6f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180226d6f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180226d61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180226d61`

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
0x180226d50  push    rbx
0x180226d52  sub     rsp, 20h
0x180226d56  xor     r9d, r9d; msWindowLength
0x180226d59  xor     r8d, r8d; msPeriod
0x180226d5c  xor     edx, edx; pftDueTime
0x180226d5e  mov     rbx, rcx
0x180226d61  call    cs:__imp_SetThreadpoolTimer
0x180226d67  mov     edx, 1; fCancelPendingCallbacks
0x180226d6c  mov     rcx, rbx; pti
0x180226d6f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180226d75  mov     rcx, rbx
0x180226d78  add     rsp, 20h
0x180226d7c  pop     rbx
0x180226d7d  jmp     cs:__imp_CloseThreadpoolTimer
```
