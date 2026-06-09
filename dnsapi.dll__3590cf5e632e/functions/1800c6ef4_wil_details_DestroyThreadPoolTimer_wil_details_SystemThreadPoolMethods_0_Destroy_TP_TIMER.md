# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800c6ef4`
- end: `0x1800c6f39`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180080250`
- `0x1800803c0`
- `0x18008041c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c6f05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c6f05`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c6f2d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c6f19`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c6f19`

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
0x1800c6ef4  push    rbx
0x1800c6ef6  sub     rsp, 20h
0x1800c6efa  xor     r9d, r9d; msWindowLength
0x1800c6efd  xor     r8d, r8d; msPeriod
0x1800c6f00  xor     edx, edx; pftDueTime
0x1800c6f02  mov     rbx, rcx
0x1800c6f05  call    cs:__imp_SetThreadpoolTimer
0x1800c6f0c  nop     dword ptr [rax+rax+00h]
0x1800c6f11  mov     edx, 1; fCancelPendingCallbacks
0x1800c6f16  mov     rcx, rbx; pti
0x1800c6f19  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c6f20  nop     dword ptr [rax+rax+00h]
0x1800c6f25  mov     rcx, rbx
0x1800c6f28  add     rsp, 20h
0x1800c6f2c  pop     rbx
0x1800c6f2d  jmp     cs:__imp_CloseThreadpoolTimer
```
