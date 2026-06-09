# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180019444`
- end: `0x180019489`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800104b8`
- `0x1800122b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019455`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019455`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019469`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019469`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001947d`

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
0x180019444  push    rbx
0x180019446  sub     rsp, 20h
0x18001944a  xor     r9d, r9d; msWindowLength
0x18001944d  xor     r8d, r8d; msPeriod
0x180019450  xor     edx, edx; pftDueTime
0x180019452  mov     rbx, rcx
0x180019455  call    cs:__imp_SetThreadpoolTimer
0x18001945c  nop     dword ptr [rax+rax+00h]
0x180019461  mov     edx, 1; fCancelPendingCallbacks
0x180019466  mov     rcx, rbx; pti
0x180019469  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019470  nop     dword ptr [rax+rax+00h]
0x180019475  mov     rcx, rbx
0x180019478  add     rsp, 20h
0x18001947c  pop     rbx
0x18001947d  jmp     cs:__imp_CloseThreadpoolTimer
```
