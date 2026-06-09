# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180003d40`
- end: `0x180003d74`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800034c4`
- `0x180007fbc`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180003d51`
- `KERNEL32!SetThreadpoolTimer` at `0x180003d51`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003d6d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003d5f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003d5f`

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
0x180003d40  push    rbx
0x180003d42  sub     rsp, 20h
0x180003d46  xor     r9d, r9d; msWindowLength
0x180003d49  xor     r8d, r8d; msPeriod
0x180003d4c  xor     edx, edx; pftDueTime
0x180003d4e  mov     rbx, rcx
0x180003d51  call    cs:__imp_SetThreadpoolTimer
0x180003d57  mov     edx, 1; fCancelPendingCallbacks
0x180003d5c  mov     rcx, rbx; pti
0x180003d5f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003d65  mov     rcx, rbx
0x180003d68  add     rsp, 20h
0x180003d6c  pop     rbx
0x180003d6d  jmp     cs:__imp_CloseThreadpoolTimer
```
