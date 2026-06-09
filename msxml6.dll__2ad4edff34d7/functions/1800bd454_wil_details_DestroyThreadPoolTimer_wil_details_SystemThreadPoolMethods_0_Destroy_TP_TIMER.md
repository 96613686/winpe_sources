# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800bd454`
- end: `0x1800bd488`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(_TP_TIMER *threadpoolTimer)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180094be8`
- `0x1800bd438`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800bd465`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800bd465`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800bd473`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800bd473`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800bd481`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(
        _TP_TIMER *threadpoolTimer)
{
  SetThreadpoolTimer(threadpoolTimer, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(threadpoolTimer, 1);
  CloseThreadpoolTimer(threadpoolTimer);
}

```

## disassembly

```asm
0x1800bd454  push    rbx
0x1800bd456  sub     rsp, 20h
0x1800bd45a  xor     r9d, r9d; msWindowLength
0x1800bd45d  xor     r8d, r8d; msPeriod
0x1800bd460  xor     edx, edx; pftDueTime
0x1800bd462  mov     rbx, threadpoolTimer
0x1800bd465  call    cs:__imp_SetThreadpoolTimer
0x1800bd46b  mov     edx, 1; fCancelPendingCallbacks
0x1800bd470  mov     threadpoolTimer, rbx; pti
0x1800bd473  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800bd479  mov     threadpoolTimer, rbx
0x1800bd47c  add     rsp, 20h
0x1800bd480  pop     rbx
0x1800bd481  jmp     cs:__imp_CloseThreadpoolTimer
```
