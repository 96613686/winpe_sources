# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000b7bc`
- end: `0x18000b801`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ac50`
- `0x18000dcb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b7cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b7cd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b7e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b7e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b7f5`

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
0x18000b7bc  push    rbx
0x18000b7be  sub     rsp, 20h
0x18000b7c2  xor     r9d, r9d; msWindowLength
0x18000b7c5  xor     r8d, r8d; msPeriod
0x18000b7c8  xor     edx, edx; pftDueTime
0x18000b7ca  mov     rbx, rcx
0x18000b7cd  call    cs:__imp_SetThreadpoolTimer
0x18000b7d4  nop     dword ptr [rax+rax+00h]
0x18000b7d9  mov     edx, 1; fCancelPendingCallbacks
0x18000b7de  mov     rcx, rbx; pti
0x18000b7e1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b7e8  nop     dword ptr [rax+rax+00h]
0x18000b7ed  mov     rcx, rbx
0x18000b7f0  add     rsp, 20h
0x18000b7f4  pop     rbx
0x18000b7f5  jmp     cs:__imp_CloseThreadpoolTimer
```
