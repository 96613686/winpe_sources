# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180020224`
- end: `0x180020269`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001bf78`
- `0x18001c8f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002025d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020235`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020235`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020249`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020249`

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
0x180020224  push    rbx
0x180020226  sub     rsp, 20h
0x18002022a  xor     r9d, r9d; msWindowLength
0x18002022d  xor     r8d, r8d; msPeriod
0x180020230  xor     edx, edx; pftDueTime
0x180020232  mov     rbx, rcx
0x180020235  call    cs:__imp_SetThreadpoolTimer
0x18002023c  nop     dword ptr [rax+rax+00h]
0x180020241  mov     edx, 1; fCancelPendingCallbacks
0x180020246  mov     rcx, rbx; pti
0x180020249  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020250  nop     dword ptr [rax+rax+00h]
0x180020255  mov     rcx, rbx
0x180020258  add     rsp, 20h
0x18002025c  pop     rbx
0x18002025d  jmp     cs:__imp_CloseThreadpoolTimer
```
