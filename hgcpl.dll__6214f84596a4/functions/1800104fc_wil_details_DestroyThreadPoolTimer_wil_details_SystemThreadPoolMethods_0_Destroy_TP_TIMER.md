# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800104fc`
- end: `0x180010530`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180010048`
- `0x18001267c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010529`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001051b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001051b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001050d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001050d`

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
0x1800104fc  push    rbx
0x1800104fe  sub     rsp, 20h
0x180010502  xor     r9d, r9d; msWindowLength
0x180010505  xor     r8d, r8d; msPeriod
0x180010508  xor     edx, edx; pftDueTime
0x18001050a  mov     rbx, rcx
0x18001050d  call    cs:__imp_SetThreadpoolTimer
0x180010513  mov     edx, 1; fCancelPendingCallbacks
0x180010518  mov     rcx, rbx; pti
0x18001051b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010521  mov     rcx, rbx
0x180010524  add     rsp, 20h
0x180010528  pop     rbx
0x180010529  jmp     cs:__imp_CloseThreadpoolTimer
```
