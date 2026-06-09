# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18007dcb0`
- end: `0x18007dce4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18003b2c0`
- `0x18003b310`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007dcc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007dcc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007dcdd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007dccf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007dccf`

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
0x18007dcb0  push    rbx
0x18007dcb2  sub     rsp, 20h
0x18007dcb6  xor     r9d, r9d; msWindowLength
0x18007dcb9  xor     r8d, r8d; msPeriod
0x18007dcbc  xor     edx, edx; pftDueTime
0x18007dcbe  mov     rbx, rcx
0x18007dcc1  call    cs:__imp_SetThreadpoolTimer
0x18007dcc7  mov     edx, 1; fCancelPendingCallbacks
0x18007dccc  mov     rcx, rbx; pti
0x18007dccf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007dcd5  mov     rcx, rbx
0x18007dcd8  add     rsp, 20h
0x18007dcdc  pop     rbx
0x18007dcdd  jmp     cs:__imp_CloseThreadpoolTimer
```
