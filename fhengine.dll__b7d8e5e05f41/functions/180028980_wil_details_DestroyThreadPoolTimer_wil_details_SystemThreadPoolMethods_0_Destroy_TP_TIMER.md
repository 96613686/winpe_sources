# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180028980`
- end: `0x1800289b4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180027aac`
- `0x18002e69c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180028991`
- `KERNEL32!SetThreadpoolTimer` at `0x180028991`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002899f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002899f`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800289ad`

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
0x180028980  push    rbx
0x180028982  sub     rsp, 20h
0x180028986  xor     r9d, r9d; msWindowLength
0x180028989  xor     r8d, r8d; msPeriod
0x18002898c  xor     edx, edx; pftDueTime
0x18002898e  mov     rbx, rcx
0x180028991  call    cs:__imp_SetThreadpoolTimer
0x180028997  mov     edx, 1; fCancelPendingCallbacks
0x18002899c  mov     rcx, rbx; pti
0x18002899f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800289a5  mov     rcx, rbx
0x1800289a8  add     rsp, 20h
0x1800289ac  pop     rbx
0x1800289ad  jmp     cs:__imp_CloseThreadpoolTimer
```
