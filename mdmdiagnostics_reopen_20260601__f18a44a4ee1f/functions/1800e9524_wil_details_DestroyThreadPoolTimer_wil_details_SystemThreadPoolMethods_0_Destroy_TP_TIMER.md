# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800e9524`
- end: `0x1800e9569`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800e7e78`
- `0x1800f1bc4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e9549`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e9549`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e955d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e9535`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e9535`

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
0x1800e9524  push    rbx
0x1800e9526  sub     rsp, 20h
0x1800e952a  xor     r9d, r9d; msWindowLength
0x1800e952d  xor     r8d, r8d; msPeriod
0x1800e9530  xor     edx, edx; pftDueTime
0x1800e9532  mov     rbx, rcx
0x1800e9535  call    cs:__imp_SetThreadpoolTimer
0x1800e953c  nop     dword ptr [rax+rax+00h]
0x1800e9541  mov     edx, 1; fCancelPendingCallbacks
0x1800e9546  mov     rcx, rbx; pti
0x1800e9549  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e9550  nop     dword ptr [rax+rax+00h]
0x1800e9555  mov     rcx, rbx
0x1800e9558  add     rsp, 20h
0x1800e955c  pop     rbx
0x1800e955d  jmp     cs:__imp_CloseThreadpoolTimer
```
