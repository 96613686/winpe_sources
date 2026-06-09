# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180016b44`
- end: `0x180016b89`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180013798`
- `0x18001c170`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016b55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016b55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016b7d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016b69`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016b69`

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
0x180016b44  push    rbx
0x180016b46  sub     rsp, 20h
0x180016b4a  xor     r9d, r9d; msWindowLength
0x180016b4d  xor     r8d, r8d; msPeriod
0x180016b50  xor     edx, edx; pftDueTime
0x180016b52  mov     rbx, rcx
0x180016b55  call    cs:__imp_SetThreadpoolTimer
0x180016b5c  nop     dword ptr [rax+rax+00h]
0x180016b61  mov     edx, 1; fCancelPendingCallbacks
0x180016b66  mov     rcx, rbx; pti
0x180016b69  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016b70  nop     dword ptr [rax+rax+00h]
0x180016b75  mov     rcx, rbx
0x180016b78  add     rsp, 20h
0x180016b7c  pop     rbx
0x180016b7d  jmp     cs:__imp_CloseThreadpoolTimer
```
