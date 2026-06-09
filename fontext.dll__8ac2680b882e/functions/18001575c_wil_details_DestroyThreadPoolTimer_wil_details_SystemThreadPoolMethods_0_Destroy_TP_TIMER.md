# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001575c`
- end: `0x180015790`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800146d8`
- `0x18001a860`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001577b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001577b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001576d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001576d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015789`

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
0x18001575c  push    rbx
0x18001575e  sub     rsp, 20h
0x180015762  xor     r9d, r9d; msWindowLength
0x180015765  xor     r8d, r8d; msPeriod
0x180015768  xor     edx, edx; pftDueTime
0x18001576a  mov     rbx, rcx
0x18001576d  call    cs:__imp_SetThreadpoolTimer
0x180015773  mov     edx, 1; fCancelPendingCallbacks
0x180015778  mov     rcx, rbx; pti
0x18001577b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180015781  mov     rcx, rbx
0x180015784  add     rsp, 20h
0x180015788  pop     rbx
0x180015789  jmp     cs:__imp_CloseThreadpoolTimer
```
