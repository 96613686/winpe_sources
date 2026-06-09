# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003e380`
- end: `0x18003e3b4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002e1f8`
- `0x18002e248`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e3ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e391`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e391`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e39f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e39f`

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
0x18003e380  push    rbx
0x18003e382  sub     rsp, 20h
0x18003e386  xor     r9d, r9d; msWindowLength
0x18003e389  xor     r8d, r8d; msPeriod
0x18003e38c  xor     edx, edx; pftDueTime
0x18003e38e  mov     rbx, rcx
0x18003e391  call    cs:__imp_SetThreadpoolTimer
0x18003e397  mov     edx, 1; fCancelPendingCallbacks
0x18003e39c  mov     rcx, rbx; pti
0x18003e39f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003e3a5  mov     rcx, rbx
0x18003e3a8  add     rsp, 20h
0x18003e3ac  pop     rbx
0x18003e3ad  jmp     cs:__imp_CloseThreadpoolTimer
```
