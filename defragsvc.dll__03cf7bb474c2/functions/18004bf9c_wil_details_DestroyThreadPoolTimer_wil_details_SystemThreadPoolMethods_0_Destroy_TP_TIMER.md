# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18004bf9c`
- end: `0x18004bfd0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180035bf0`
- `0x180035c40`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004bfad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004bfad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004bfc9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004bfbb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004bfbb`

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
0x18004bf9c  push    rbx
0x18004bf9e  sub     rsp, 20h
0x18004bfa2  xor     r9d, r9d; msWindowLength
0x18004bfa5  xor     r8d, r8d; msPeriod
0x18004bfa8  xor     edx, edx; pftDueTime
0x18004bfaa  mov     rbx, rcx
0x18004bfad  call    cs:__imp_SetThreadpoolTimer
0x18004bfb3  mov     edx, 1; fCancelPendingCallbacks
0x18004bfb8  mov     rcx, rbx; pti
0x18004bfbb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004bfc1  mov     rcx, rbx
0x18004bfc4  add     rsp, 20h
0x18004bfc8  pop     rbx
0x18004bfc9  jmp     cs:__imp_CloseThreadpoolTimer
```
