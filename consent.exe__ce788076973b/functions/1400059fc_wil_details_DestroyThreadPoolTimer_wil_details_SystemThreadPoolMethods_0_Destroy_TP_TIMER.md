# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400059fc`
- end: `0x140005a30`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400057c0`
- `0x140005990`
- `0x14000f310`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005a29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005a1b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005a1b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005a0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005a0d`

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
0x1400059fc  push    rbx
0x1400059fe  sub     rsp, 20h
0x140005a02  xor     r9d, r9d; msWindowLength
0x140005a05  xor     r8d, r8d; msPeriod
0x140005a08  xor     edx, edx; pftDueTime
0x140005a0a  mov     rbx, rcx
0x140005a0d  call    cs:__imp_SetThreadpoolTimer
0x140005a13  mov     edx, 1; fCancelPendingCallbacks
0x140005a18  mov     rcx, rbx; pti
0x140005a1b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005a21  mov     rcx, rbx
0x140005a24  add     rsp, 20h
0x140005a28  pop     rbx
0x140005a29  jmp     cs:__imp_CloseThreadpoolTimer
```
