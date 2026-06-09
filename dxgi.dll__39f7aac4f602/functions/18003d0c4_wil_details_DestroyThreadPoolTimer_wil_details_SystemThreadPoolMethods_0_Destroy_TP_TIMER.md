# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003d0c4`
- end: `0x18003d0f8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18003cfcc`
- `0x18003d080`
- `0x18003d9c0`
- `0x18003ddf0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003d0f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d0d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d0d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003d0e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003d0e3`

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
0x18003d0c4  push    rbx
0x18003d0c6  sub     rsp, 20h
0x18003d0ca  xor     r9d, r9d; msWindowLength
0x18003d0cd  xor     r8d, r8d; msPeriod
0x18003d0d0  xor     edx, edx; pftDueTime
0x18003d0d2  mov     rbx, rcx
0x18003d0d5  call    cs:__imp_SetThreadpoolTimer
0x18003d0db  mov     edx, 1; fCancelPendingCallbacks
0x18003d0e0  mov     rcx, rbx; pti
0x18003d0e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003d0e9  mov     rcx, rbx
0x18003d0ec  add     rsp, 20h
0x18003d0f0  pop     rbx
0x18003d0f1  jmp     cs:__imp_CloseThreadpoolTimer
```
