# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180057110`
- end: `0x180057144`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800363ec`
- `0x18003718c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005712f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005712f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005713d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180057121`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180057121`

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
0x180057110  push    rbx
0x180057112  sub     rsp, 20h
0x180057116  xor     r9d, r9d; msWindowLength
0x180057119  xor     r8d, r8d; msPeriod
0x18005711c  xor     edx, edx; pftDueTime
0x18005711e  mov     rbx, rcx
0x180057121  call    cs:__imp_SetThreadpoolTimer
0x180057127  mov     edx, 1; fCancelPendingCallbacks
0x18005712c  mov     rcx, rbx; pti
0x18005712f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180057135  mov     rcx, rbx
0x180057138  add     rsp, 20h
0x18005713c  pop     rbx
0x18005713d  jmp     cs:__imp_CloseThreadpoolTimer
```
