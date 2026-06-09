# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800be7b8`
- end: `0x1800be7fd`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `void __fastcall(_TP_TIMER *threadpoolTimer)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180094f9c`
- `0x1800be798`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800be7c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800be7c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800be7dd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800be7dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800be7f1`

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
0x1800be7b8  push    rbx
0x1800be7ba  sub     rsp, 20h
0x1800be7be  xor     r9d, r9d; msWindowLength
0x1800be7c1  xor     r8d, r8d; msPeriod
0x1800be7c4  xor     edx, edx; pftDueTime
0x1800be7c6  mov     rbx, threadpoolTimer
0x1800be7c9  call    cs:__imp_SetThreadpoolTimer
0x1800be7d0  nop     dword ptr [rax+rax+00h]
0x1800be7d5  mov     edx, 1; fCancelPendingCallbacks
0x1800be7da  mov     threadpoolTimer, rbx; pti
0x1800be7dd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800be7e4  nop     dword ptr [rax+rax+00h]
0x1800be7e9  mov     threadpoolTimer, rbx
0x1800be7ec  add     rsp, 20h
0x1800be7f0  pop     rbx
0x1800be7f1  jmp     cs:__imp_CloseThreadpoolTimer
```
