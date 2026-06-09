# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006e88`
- end: `0x180006ebc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005f94`
- `0x18000bcc8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006eb5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006ea7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006ea7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006e99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006e99`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180006e88  push    rbx
0x180006e8a  sub     rsp, 20h
0x180006e8e  xor     r9d, r9d; msWindowLength
0x180006e91  xor     r8d, r8d; msPeriod
0x180006e94  xor     edx, edx; pftDueTime
0x180006e96  mov     rbx, rcx
0x180006e99  call    cs:__imp_SetThreadpoolTimer
0x180006e9f  mov     edx, 1; fCancelPendingCallbacks
0x180006ea4  mov     rcx, rbx; pti
0x180006ea7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006ead  mov     rcx, rbx
0x180006eb0  add     rsp, 20h
0x180006eb4  pop     rbx
0x180006eb5  jmp     cs:__imp_CloseThreadpoolTimer
```
