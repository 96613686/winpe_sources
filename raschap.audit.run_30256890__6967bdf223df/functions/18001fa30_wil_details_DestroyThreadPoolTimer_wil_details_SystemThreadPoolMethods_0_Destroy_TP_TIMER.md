# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001fa30`
- end: `0x18001fa64`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fae4`
- `0x18000fc7c`
- `0x18000fd30`
- `0x180011c0c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fa5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fa41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fa41`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fa4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fa4f`

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
0x18001fa30  push    rbx
0x18001fa32  sub     rsp, 20h
0x18001fa36  xor     r9d, r9d; msWindowLength
0x18001fa39  xor     r8d, r8d; msPeriod
0x18001fa3c  xor     edx, edx; pftDueTime
0x18001fa3e  mov     rbx, rcx
0x18001fa41  call    cs:__imp_SetThreadpoolTimer
0x18001fa47  mov     edx, 1; fCancelPendingCallbacks
0x18001fa4c  mov     rcx, rbx; pti
0x18001fa4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001fa55  mov     rcx, rbx
0x18001fa58  add     rsp, 20h
0x18001fa5c  pop     rbx
0x18001fa5d  jmp     cs:__imp_CloseThreadpoolTimer
```
