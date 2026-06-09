# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800746a0`
- end: `0x1800746d4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18003c3b0`
- `0x18003c400`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800746bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800746bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800746b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800746b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800746cd`

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
0x1800746a0  push    rbx
0x1800746a2  sub     rsp, 20h
0x1800746a6  xor     r9d, r9d; msWindowLength
0x1800746a9  xor     r8d, r8d; msPeriod
0x1800746ac  xor     edx, edx; pftDueTime
0x1800746ae  mov     rbx, rcx
0x1800746b1  call    cs:__imp_SetThreadpoolTimer
0x1800746b7  mov     edx, 1; fCancelPendingCallbacks
0x1800746bc  mov     rcx, rbx; pti
0x1800746bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800746c5  mov     rcx, rbx
0x1800746c8  add     rsp, 20h
0x1800746cc  pop     rbx
0x1800746cd  jmp     cs:__imp_CloseThreadpoolTimer
```
