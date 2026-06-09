# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001aaf4`
- end: `0x18001ab28`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a630`
- `0x18001d0e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ab13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ab13`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001ab21`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ab05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ab05`

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
0x18001aaf4  push    rbx
0x18001aaf6  sub     rsp, 20h
0x18001aafa  xor     r9d, r9d; msWindowLength
0x18001aafd  xor     r8d, r8d; msPeriod
0x18001ab00  xor     edx, edx; pftDueTime
0x18001ab02  mov     rbx, rcx
0x18001ab05  call    cs:__imp_SetThreadpoolTimer
0x18001ab0b  mov     edx, 1; fCancelPendingCallbacks
0x18001ab10  mov     rcx, rbx; pti
0x18001ab13  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ab19  mov     rcx, rbx
0x18001ab1c  add     rsp, 20h
0x18001ab20  pop     rbx
0x18001ab21  jmp     cs:__imp_CloseThreadpoolTimer
```
