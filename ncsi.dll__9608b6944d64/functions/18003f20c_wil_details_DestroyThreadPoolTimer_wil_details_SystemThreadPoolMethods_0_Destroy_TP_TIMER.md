# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003f20c`
- end: `0x18003f240`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002e960`
- `0x18003f13c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003f21d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003f21d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003f239`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003f22b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003f22b`

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
0x18003f20c  push    rbx
0x18003f20e  sub     rsp, 20h
0x18003f212  xor     r9d, r9d; msWindowLength
0x18003f215  xor     r8d, r8d; msPeriod
0x18003f218  xor     edx, edx; pftDueTime
0x18003f21a  mov     rbx, rcx
0x18003f21d  call    cs:__imp_SetThreadpoolTimer
0x18003f223  mov     edx, 1; fCancelPendingCallbacks
0x18003f228  mov     rcx, rbx; pti
0x18003f22b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003f231  mov     rcx, rbx
0x18003f234  add     rsp, 20h
0x18003f238  pop     rbx
0x18003f239  jmp     cs:__imp_CloseThreadpoolTimer
```
