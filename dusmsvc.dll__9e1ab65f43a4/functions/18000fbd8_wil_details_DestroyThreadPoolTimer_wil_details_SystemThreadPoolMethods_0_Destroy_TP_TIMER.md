# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000fbd8`
- end: `0x18000fc0c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f0f4`
- `0x1800137a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fbe9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fbe9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fbf7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fbf7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fc05`

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
0x18000fbd8  push    rbx
0x18000fbda  sub     rsp, 20h
0x18000fbde  xor     r9d, r9d; msWindowLength
0x18000fbe1  xor     r8d, r8d; msPeriod
0x18000fbe4  xor     edx, edx; pftDueTime
0x18000fbe6  mov     rbx, rcx
0x18000fbe9  call    cs:__imp_SetThreadpoolTimer
0x18000fbef  mov     edx, 1; fCancelPendingCallbacks
0x18000fbf4  mov     rcx, rbx; pti
0x18000fbf7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000fbfd  mov     rcx, rbx
0x18000fc00  add     rsp, 20h
0x18000fc04  pop     rbx
0x18000fc05  jmp     cs:__imp_CloseThreadpoolTimer
```
