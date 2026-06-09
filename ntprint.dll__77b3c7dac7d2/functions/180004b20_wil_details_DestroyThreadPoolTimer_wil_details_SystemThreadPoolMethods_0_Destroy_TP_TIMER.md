# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180004b20`
- end: `0x180004b54`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004284`
- `0x1800088a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b3f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b31`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b31`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b4d`

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
0x180004b20  push    rbx
0x180004b22  sub     rsp, 20h
0x180004b26  xor     r9d, r9d; msWindowLength
0x180004b29  xor     r8d, r8d; msPeriod
0x180004b2c  xor     edx, edx; pftDueTime
0x180004b2e  mov     rbx, rcx
0x180004b31  call    cs:__imp_SetThreadpoolTimer
0x180004b37  mov     edx, 1; fCancelPendingCallbacks
0x180004b3c  mov     rcx, rbx; pti
0x180004b3f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004b45  mov     rcx, rbx
0x180004b48  add     rsp, 20h
0x180004b4c  pop     rbx
0x180004b4d  jmp     cs:__imp_CloseThreadpoolTimer
```
