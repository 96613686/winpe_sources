# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800068c0`
- end: `0x1800068f4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005f94`
- `0x18000ad64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800068df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800068d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800068ed`

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
0x1800068c0  push    rbx
0x1800068c2  sub     rsp, 20h
0x1800068c6  xor     r9d, r9d; msWindowLength
0x1800068c9  xor     r8d, r8d; msPeriod
0x1800068cc  xor     edx, edx; pftDueTime
0x1800068ce  mov     rbx, rcx
0x1800068d1  call    cs:__imp_SetThreadpoolTimer
0x1800068d7  mov     edx, 1; fCancelPendingCallbacks
0x1800068dc  mov     rcx, rbx; pti
0x1800068df  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800068e5  mov     rcx, rbx
0x1800068e8  add     rsp, 20h
0x1800068ec  pop     rbx
0x1800068ed  jmp     cs:__imp_CloseThreadpoolTimer
```
