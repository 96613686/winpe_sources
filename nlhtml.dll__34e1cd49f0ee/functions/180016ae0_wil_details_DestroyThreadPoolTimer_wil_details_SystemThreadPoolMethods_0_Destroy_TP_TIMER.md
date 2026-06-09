# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180016ae0`
- end: `0x180016b14`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180016160`
- `0x18001a96c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016b0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016af1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016af1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016aff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016aff`

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
0x180016ae0  push    rbx
0x180016ae2  sub     rsp, 20h
0x180016ae6  xor     r9d, r9d; msWindowLength
0x180016ae9  xor     r8d, r8d; msPeriod
0x180016aec  xor     edx, edx; pftDueTime
0x180016aee  mov     rbx, rcx
0x180016af1  call    cs:__imp_SetThreadpoolTimer
0x180016af7  mov     edx, 1; fCancelPendingCallbacks
0x180016afc  mov     rcx, rbx; pti
0x180016aff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016b05  mov     rcx, rbx
0x180016b08  add     rsp, 20h
0x180016b0c  pop     rbx
0x180016b0d  jmp     cs:__imp_CloseThreadpoolTimer
```
