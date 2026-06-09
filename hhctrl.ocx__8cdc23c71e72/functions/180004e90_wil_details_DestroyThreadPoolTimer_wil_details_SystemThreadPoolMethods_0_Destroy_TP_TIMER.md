# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180004e90`
- end: `0x180004ec4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003e84`
- `0x18000a47c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180004ea1`
- `KERNEL32!SetThreadpoolTimer` at `0x180004ea1`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004eaf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004eaf`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004ebd`

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
0x180004e90  push    rbx
0x180004e92  sub     rsp, 20h
0x180004e96  xor     r9d, r9d; msWindowLength
0x180004e99  xor     r8d, r8d; msPeriod
0x180004e9c  xor     edx, edx; pftDueTime
0x180004e9e  mov     rbx, rcx
0x180004ea1  call    cs:__imp_SetThreadpoolTimer
0x180004ea7  mov     edx, 1; fCancelPendingCallbacks
0x180004eac  mov     rcx, rbx; pti
0x180004eaf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004eb5  mov     rcx, rbx
0x180004eb8  add     rsp, 20h
0x180004ebc  pop     rbx
0x180004ebd  jmp     cs:__imp_CloseThreadpoolTimer
```
