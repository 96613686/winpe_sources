# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003f830`
- end: `0x18003f864`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180031004`
- `0x180031084`
- `0x1800310a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003f85d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003f84f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003f84f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003f841`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003f841`

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
0x18003f830  push    rbx
0x18003f832  sub     rsp, 20h
0x18003f836  xor     r9d, r9d; msWindowLength
0x18003f839  xor     r8d, r8d; msPeriod
0x18003f83c  xor     edx, edx; pftDueTime
0x18003f83e  mov     rbx, rcx
0x18003f841  call    cs:__imp_SetThreadpoolTimer
0x18003f847  mov     edx, 1; fCancelPendingCallbacks
0x18003f84c  mov     rcx, rbx; pti
0x18003f84f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003f855  mov     rcx, rbx
0x18003f858  add     rsp, 20h
0x18003f85c  pop     rbx
0x18003f85d  jmp     cs:__imp_CloseThreadpoolTimer
```
