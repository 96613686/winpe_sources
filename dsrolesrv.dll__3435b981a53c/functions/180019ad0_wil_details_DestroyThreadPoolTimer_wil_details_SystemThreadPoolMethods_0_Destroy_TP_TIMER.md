# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180019ad0`
- end: `0x180019b04`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800192f8`
- `0x18001de88`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019ae1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019ae1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019afd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019aef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019aef`

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
0x180019ad0  push    rbx
0x180019ad2  sub     rsp, 20h
0x180019ad6  xor     r9d, r9d; msWindowLength
0x180019ad9  xor     r8d, r8d; msPeriod
0x180019adc  xor     edx, edx; pftDueTime
0x180019ade  mov     rbx, rcx
0x180019ae1  call    cs:__imp_SetThreadpoolTimer
0x180019ae7  mov     edx, 1; fCancelPendingCallbacks
0x180019aec  mov     rcx, rbx; pti
0x180019aef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019af5  mov     rcx, rbx
0x180019af8  add     rsp, 20h
0x180019afc  pop     rbx
0x180019afd  jmp     cs:__imp_CloseThreadpoolTimer
```
