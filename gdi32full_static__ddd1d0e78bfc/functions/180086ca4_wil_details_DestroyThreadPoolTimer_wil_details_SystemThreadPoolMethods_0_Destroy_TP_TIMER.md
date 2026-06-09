# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180086ca4`
- end: `0x180086ce9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180053280`
- `0x1800532dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180086cdd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180086cb5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180086cb5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180086cc9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180086cc9`

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
0x180086ca4  push    rbx
0x180086ca6  sub     rsp, 20h
0x180086caa  xor     r9d, r9d; msWindowLength
0x180086cad  xor     r8d, r8d; msPeriod
0x180086cb0  xor     edx, edx; pftDueTime
0x180086cb2  mov     rbx, rcx
0x180086cb5  call    cs:__imp_SetThreadpoolTimer
0x180086cbc  nop     dword ptr [rax+rax+00h]
0x180086cc1  mov     edx, 1; fCancelPendingCallbacks
0x180086cc6  mov     rcx, rbx; pti
0x180086cc9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180086cd0  nop     dword ptr [rax+rax+00h]
0x180086cd5  mov     rcx, rbx
0x180086cd8  add     rsp, 20h
0x180086cdc  pop     rbx
0x180086cdd  jmp     cs:__imp_CloseThreadpoolTimer
```
