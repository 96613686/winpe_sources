# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002321c`
- end: `0x180023251`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `53`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800228b4`
- `0x180026fc4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023244`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023244`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002322d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002322d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002323b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002323b`

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
0x18002321c  push    rbx
0x18002321e  sub     rsp, 20h
0x180023222  mov     rbx, rcx
0x180023225  xor     r9d, r9d; msWindowLength
0x180023228  xor     r8d, r8d; msPeriod
0x18002322b  xor     edx, edx; pftDueTime
0x18002322d  call    cs:__imp_SetThreadpoolTimer
0x180023233  mov     edx, 1; fCancelPendingCallbacks
0x180023238  mov     rcx, rbx; pti
0x18002323b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023241  mov     rcx, rbx; pti
0x180023244  call    cs:__imp_CloseThreadpoolTimer
0x18002324a  nop
0x18002324b  add     rsp, 20h
0x18002324f  pop     rbx
0x180023250  retn
```
