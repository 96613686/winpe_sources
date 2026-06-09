# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800aee00`
- end: `0x1800aee34`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180084900`
- `0x180084974`
- `0x1800849f8`
- `0x180084ab4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aee11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aee11`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aee1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aee1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aee2d`

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
0x1800aee00  push    rbx
0x1800aee02  sub     rsp, 20h
0x1800aee06  xor     r9d, r9d; msWindowLength
0x1800aee09  xor     r8d, r8d; msPeriod
0x1800aee0c  xor     edx, edx; pftDueTime
0x1800aee0e  mov     rbx, rcx
0x1800aee11  call    cs:__imp_SetThreadpoolTimer
0x1800aee17  mov     edx, 1; fCancelPendingCallbacks
0x1800aee1c  mov     rcx, rbx; pti
0x1800aee1f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800aee25  mov     rcx, rbx
0x1800aee28  add     rsp, 20h
0x1800aee2c  pop     rbx
0x1800aee2d  jmp     cs:__imp_CloseThreadpoolTimer
```
