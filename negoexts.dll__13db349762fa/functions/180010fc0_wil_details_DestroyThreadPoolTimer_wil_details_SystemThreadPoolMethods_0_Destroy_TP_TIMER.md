# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180010fc0`
- end: `0x180010ff4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e02c`
- `0x18000e07c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010fdf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010fdf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010fed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010fd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010fd1`

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
0x180010fc0  push    rbx
0x180010fc2  sub     rsp, 20h
0x180010fc6  xor     r9d, r9d; msWindowLength
0x180010fc9  xor     r8d, r8d; msPeriod
0x180010fcc  xor     edx, edx; pftDueTime
0x180010fce  mov     rbx, rcx
0x180010fd1  call    cs:__imp_SetThreadpoolTimer
0x180010fd7  mov     edx, 1; fCancelPendingCallbacks
0x180010fdc  mov     rcx, rbx; pti
0x180010fdf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010fe5  mov     rcx, rbx
0x180010fe8  add     rsp, 20h
0x180010fec  pop     rbx
0x180010fed  jmp     cs:__imp_CloseThreadpoolTimer
```
