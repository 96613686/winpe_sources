# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180016c18`
- end: `0x180016c4c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d7a8`
- `0x180016904`
- `0x1800169d8`
- `0x180016b44`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016c45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016c29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016c29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016c37`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016c37`

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
0x180016c18  push    rbx
0x180016c1a  sub     rsp, 20h
0x180016c1e  xor     r9d, r9d; msWindowLength
0x180016c21  xor     r8d, r8d; msPeriod
0x180016c24  xor     edx, edx; pftDueTime
0x180016c26  mov     rbx, rcx
0x180016c29  call    cs:__imp_SetThreadpoolTimer
0x180016c2f  mov     edx, 1; fCancelPendingCallbacks
0x180016c34  mov     rcx, rbx; pti
0x180016c37  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016c3d  mov     rcx, rbx
0x180016c40  add     rsp, 20h
0x180016c44  pop     rbx
0x180016c45  jmp     cs:__imp_CloseThreadpoolTimer
```
