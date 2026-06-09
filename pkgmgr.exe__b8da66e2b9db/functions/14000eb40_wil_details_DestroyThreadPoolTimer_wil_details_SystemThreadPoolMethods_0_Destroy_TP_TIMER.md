# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x14000eb40`
- end: `0x14000eb74`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000e638`
- `0x140010918`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000eb6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000eb51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000eb51`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000eb5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000eb5f`

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
0x14000eb40  push    rbx
0x14000eb42  sub     rsp, 20h
0x14000eb46  xor     r9d, r9d; msWindowLength
0x14000eb49  xor     r8d, r8d; msPeriod
0x14000eb4c  xor     edx, edx; pftDueTime
0x14000eb4e  mov     rbx, rcx
0x14000eb51  call    cs:__imp_SetThreadpoolTimer
0x14000eb57  mov     edx, 1; fCancelPendingCallbacks
0x14000eb5c  mov     rcx, rbx; pti
0x14000eb5f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000eb65  mov     rcx, rbx
0x14000eb68  add     rsp, 20h
0x14000eb6c  pop     rbx
0x14000eb6d  jmp     cs:__imp_CloseThreadpoolTimer
```
