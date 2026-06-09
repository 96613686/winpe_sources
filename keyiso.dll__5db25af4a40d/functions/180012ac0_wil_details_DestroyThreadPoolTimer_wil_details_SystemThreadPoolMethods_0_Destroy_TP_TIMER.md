# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180012ac0`
- end: `0x180012af4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000adc8`
- `0x18000ae18`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012aed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012adf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012adf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012ad1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012ad1`

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
0x180012ac0  push    rbx
0x180012ac2  sub     rsp, 20h
0x180012ac6  xor     r9d, r9d; msWindowLength
0x180012ac9  xor     r8d, r8d; msPeriod
0x180012acc  xor     edx, edx; pftDueTime
0x180012ace  mov     rbx, rcx
0x180012ad1  call    cs:__imp_SetThreadpoolTimer
0x180012ad7  mov     edx, 1; fCancelPendingCallbacks
0x180012adc  mov     rcx, rbx; pti
0x180012adf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012ae5  mov     rcx, rbx
0x180012ae8  add     rsp, 20h
0x180012aec  pop     rbx
0x180012aed  jmp     cs:__imp_CloseThreadpoolTimer
```
