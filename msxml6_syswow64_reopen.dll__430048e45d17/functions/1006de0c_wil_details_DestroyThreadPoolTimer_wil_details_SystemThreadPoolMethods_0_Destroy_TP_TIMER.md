# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1006de0c`
- end: `0x1006de31`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SGXPAU_TP_TIMER@@@Z`
- size: `37`
- prototype: `void __stdcall(_TP_TIMER *threadpoolTimer)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x10064254`
- `0x1006428c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1006de24`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1006de24`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1006de2b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1006de19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1006de19`

## pseudocode

```c
void __stdcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(
        _TP_TIMER *threadpoolTimer)
{
  SetThreadpoolTimer(threadpoolTimer, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(threadpoolTimer, 1);
  CloseThreadpoolTimer(threadpoolTimer);
}

```

## disassembly

```asm
0x1006de0c  mov     edi, edi
0x1006de0e  push    ebp
0x1006de0f  mov     ebp, esp
0x1006de11  xor     eax, eax
0x1006de13  push    eax; msWindowLength
0x1006de14  push    eax; msPeriod
0x1006de15  push    eax; pftDueTime
0x1006de16  push    [ebp+threadpoolTimer]; pti
0x1006de19  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x1006de1f  push    1; fCancelPendingCallbacks
0x1006de21  push    [ebp+threadpoolTimer]; pti
0x1006de24  call    ds:__imp__WaitForThreadpoolTimerCallbacks@8; WaitForThreadpoolTimerCallbacks(x,x)
0x1006de2a  pop     ebp
0x1006de2b  jmp     ds:__imp__CloseThreadpoolTimer@4; CloseThreadpoolTimer(x)
```
