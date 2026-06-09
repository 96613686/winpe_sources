# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003b1c4`
- end: `0x18003b209`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180024de0`
- `0x180035f68`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003b1fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b1e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b1e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b1d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b1d5`

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
0x18003b1c4  push    rbx
0x18003b1c6  sub     rsp, 20h
0x18003b1ca  xor     r9d, r9d; msWindowLength
0x18003b1cd  xor     r8d, r8d; msPeriod
0x18003b1d0  xor     edx, edx; pftDueTime
0x18003b1d2  mov     rbx, rcx
0x18003b1d5  call    cs:__imp_SetThreadpoolTimer
0x18003b1dc  nop     dword ptr [rax+rax+00h]
0x18003b1e1  mov     edx, 1; fCancelPendingCallbacks
0x18003b1e6  mov     rcx, rbx; pti
0x18003b1e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003b1f0  nop     dword ptr [rax+rax+00h]
0x18003b1f5  mov     rcx, rbx
0x18003b1f8  add     rsp, 20h
0x18003b1fc  pop     rbx
0x18003b1fd  jmp     cs:__imp_CloseThreadpoolTimer
```
