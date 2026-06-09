# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180051604`
- end: `0x180051649`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180031098`
- `0x18004b2b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051629`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051629`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051615`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051615`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005163d`

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
0x180051604  push    rbx
0x180051606  sub     rsp, 20h
0x18005160a  xor     r9d, r9d; msWindowLength
0x18005160d  xor     r8d, r8d; msPeriod
0x180051610  xor     edx, edx; pftDueTime
0x180051612  mov     rbx, rcx
0x180051615  call    cs:__imp_SetThreadpoolTimer
0x18005161c  nop     dword ptr [rax+rax+00h]
0x180051621  mov     edx, 1; fCancelPendingCallbacks
0x180051626  mov     rcx, rbx; pti
0x180051629  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180051630  nop     dword ptr [rax+rax+00h]
0x180051635  mov     rcx, rbx
0x180051638  add     rsp, 20h
0x18005163c  pop     rbx
0x18005163d  jmp     cs:__imp_CloseThreadpoolTimer
```
