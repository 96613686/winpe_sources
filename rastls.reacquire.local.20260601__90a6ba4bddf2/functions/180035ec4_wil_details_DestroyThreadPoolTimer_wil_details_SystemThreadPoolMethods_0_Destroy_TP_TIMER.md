# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180035ec4`
- end: `0x180035f09`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18001fdf4`
- `0x18002ba08`
- `0x180032f78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180035efd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180035ee9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180035ee9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035ed5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035ed5`

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
0x180035ec4  push    rbx
0x180035ec6  sub     rsp, 20h
0x180035eca  xor     r9d, r9d; msWindowLength
0x180035ecd  xor     r8d, r8d; msPeriod
0x180035ed0  xor     edx, edx; pftDueTime
0x180035ed2  mov     rbx, rcx
0x180035ed5  call    cs:__imp_SetThreadpoolTimer
0x180035edc  nop     dword ptr [rax+rax+00h]
0x180035ee1  mov     edx, 1; fCancelPendingCallbacks
0x180035ee6  mov     rcx, rbx; pti
0x180035ee9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180035ef0  nop     dword ptr [rax+rax+00h]
0x180035ef5  mov     rcx, rbx
0x180035ef8  add     rsp, 20h
0x180035efc  pop     rbx
0x180035efd  jmp     cs:__imp_CloseThreadpoolTimer
```
