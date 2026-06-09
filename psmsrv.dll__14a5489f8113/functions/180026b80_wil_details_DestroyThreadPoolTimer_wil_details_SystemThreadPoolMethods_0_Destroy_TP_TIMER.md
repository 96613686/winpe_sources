# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180026b80`
- end: `0x180026bb4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180017c50`
- `0x180019ee4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026b91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026b91`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026b9f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026b9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180026bad`

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
0x180026b80  push    rbx
0x180026b82  sub     rsp, 20h
0x180026b86  xor     r9d, r9d; msWindowLength
0x180026b89  xor     r8d, r8d; msPeriod
0x180026b8c  xor     edx, edx; pftDueTime
0x180026b8e  mov     rbx, rcx
0x180026b91  call    cs:__imp_SetThreadpoolTimer
0x180026b97  mov     edx, 1; fCancelPendingCallbacks
0x180026b9c  mov     rcx, rbx; pti
0x180026b9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180026ba5  mov     rcx, rbx
0x180026ba8  add     rsp, 20h
0x180026bac  pop     rbx
0x180026bad  jmp     cs:__imp_CloseThreadpoolTimer
```
