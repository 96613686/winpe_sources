# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180017ba8`
- end: `0x180017bdd`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180016aec`
- `0x18001d6c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017bc7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017bc7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017bb9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017bb9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017bd0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017bd0`

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
0x180017ba8  push    rbx
0x180017baa  sub     rsp, 20h
0x180017bae  mov     rbx, rcx
0x180017bb1  xor     r9d, r9d; msWindowLength
0x180017bb4  xor     r8d, r8d; msPeriod
0x180017bb7  xor     edx, edx; pftDueTime
0x180017bb9  call    cs:__imp_SetThreadpoolTimer
0x180017bbf  mov     edx, 1; fCancelPendingCallbacks
0x180017bc4  mov     rcx, rbx; pti
0x180017bc7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017bcd  mov     rcx, rbx; pti
0x180017bd0  call    cs:__imp_CloseThreadpoolTimer
0x180017bd6  nop
0x180017bd7  add     rsp, 20h
0x180017bdb  pop     rbx
0x180017bdc  retn
```
