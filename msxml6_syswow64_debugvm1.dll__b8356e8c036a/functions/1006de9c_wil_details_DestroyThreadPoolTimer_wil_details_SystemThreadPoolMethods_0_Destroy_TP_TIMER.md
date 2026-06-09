# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1006de9c`
- end: `0x1006dec1`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SGXPAU_TP_TIMER@@@Z`
- size: `37`
- prototype: `void __stdcall(_TP_TIMER *threadpoolTimer)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x100642e7`
- `0x1006431f`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1006deb4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1006deb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1006debb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1006dea9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1006dea9`

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
0x1006de9c  mov     edi, edi
0x1006de9e  push    ebp
0x1006de9f  mov     ebp, esp
0x1006dea1  xor     eax, eax
0x1006dea3  push    eax; msWindowLength
0x1006dea4  push    eax; msPeriod
0x1006dea5  push    eax; pftDueTime
0x1006dea6  push    [ebp+threadpoolTimer]; pti
0x1006dea9  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x1006deaf  push    1; fCancelPendingCallbacks
0x1006deb1  push    [ebp+threadpoolTimer]; pti
0x1006deb4  call    ds:__imp__WaitForThreadpoolTimerCallbacks@8; WaitForThreadpoolTimerCallbacks(x,x)
0x1006deba  pop     ebp
0x1006debb  jmp     ds:__imp__CloseThreadpoolTimer@4; CloseThreadpoolTimer(x)
```
