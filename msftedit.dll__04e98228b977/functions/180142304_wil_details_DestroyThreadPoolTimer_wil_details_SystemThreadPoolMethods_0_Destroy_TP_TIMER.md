# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180142304`
- end: `0x180142349`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1801419c8`
- `0x180145fd4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180142315`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180142315`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18014233d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180142329`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180142329`

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
0x180142304  push    rbx
0x180142306  sub     rsp, 20h
0x18014230a  xor     r9d, r9d; msWindowLength
0x18014230d  xor     r8d, r8d; msPeriod
0x180142310  xor     edx, edx; pftDueTime
0x180142312  mov     rbx, rcx
0x180142315  call    cs:__imp_SetThreadpoolTimer
0x18014231c  nop     dword ptr [rax+rax+00h]
0x180142321  mov     edx, 1; fCancelPendingCallbacks
0x180142326  mov     rcx, rbx; pti
0x180142329  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180142330  nop     dword ptr [rax+rax+00h]
0x180142335  mov     rcx, rbx
0x180142338  add     rsp, 20h
0x18014233c  pop     rbx
0x18014233d  jmp     cs:__imp_CloseThreadpoolTimer
```
