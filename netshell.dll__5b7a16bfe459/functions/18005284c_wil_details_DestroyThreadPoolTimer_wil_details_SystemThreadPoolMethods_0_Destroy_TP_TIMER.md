# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18005284c`
- end: `0x180052880`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180016808`
- `0x18001a148`
- `0x18001a8ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005285d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005285d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180052879`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005286b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005286b`

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
0x18005284c  push    rbx
0x18005284e  sub     rsp, 20h
0x180052852  xor     r9d, r9d; msWindowLength
0x180052855  xor     r8d, r8d; msPeriod
0x180052858  xor     edx, edx; pftDueTime
0x18005285a  mov     rbx, rcx
0x18005285d  call    cs:__imp_SetThreadpoolTimer
0x180052863  mov     edx, 1; fCancelPendingCallbacks
0x180052868  mov     rcx, rbx; pti
0x18005286b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180052871  mov     rcx, rbx
0x180052874  add     rsp, 20h
0x180052878  pop     rbx
0x180052879  jmp     cs:__imp_CloseThreadpoolTimer
```
