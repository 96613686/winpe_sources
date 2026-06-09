# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18004cd90`
- end: `0x18004cdd5`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18003b47c`
- `0x180042824`
- `0x18004cc78`
- `0x18004cd04`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004cdc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004cda1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004cda1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004cdb5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004cdb5`

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
0x18004cd90  push    rbx
0x18004cd92  sub     rsp, 20h
0x18004cd96  xor     r9d, r9d; msWindowLength
0x18004cd99  xor     r8d, r8d; msPeriod
0x18004cd9c  xor     edx, edx; pftDueTime
0x18004cd9e  mov     rbx, rcx
0x18004cda1  call    cs:__imp_SetThreadpoolTimer
0x18004cda8  nop     dword ptr [rax+rax+00h]
0x18004cdad  mov     edx, 1; fCancelPendingCallbacks
0x18004cdb2  mov     rcx, rbx; pti
0x18004cdb5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004cdbc  nop     dword ptr [rax+rax+00h]
0x18004cdc1  mov     rcx, rbx
0x18004cdc4  add     rsp, 20h
0x18004cdc8  pop     rbx
0x18004cdc9  jmp     cs:__imp_CloseThreadpoolTimer
```
