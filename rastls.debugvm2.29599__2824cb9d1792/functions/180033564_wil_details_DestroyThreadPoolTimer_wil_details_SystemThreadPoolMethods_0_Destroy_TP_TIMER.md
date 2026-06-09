# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180033564`
- end: `0x180033598`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18001f0d4`
- `0x18002958c`
- `0x18003102c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180033591`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033583`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033583`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033575`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033575`

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
0x180033564  push    rbx
0x180033566  sub     rsp, 20h
0x18003356a  xor     r9d, r9d; msWindowLength
0x18003356d  xor     r8d, r8d; msPeriod
0x180033570  xor     edx, edx; pftDueTime
0x180033572  mov     rbx, rcx
0x180033575  call    cs:__imp_SetThreadpoolTimer
0x18003357b  mov     edx, 1; fCancelPendingCallbacks
0x180033580  mov     rcx, rbx; pti
0x180033583  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180033589  mov     rcx, rbx
0x18003358c  add     rsp, 20h
0x180033590  pop     rbx
0x180033591  jmp     cs:__imp_CloseThreadpoolTimer
```
