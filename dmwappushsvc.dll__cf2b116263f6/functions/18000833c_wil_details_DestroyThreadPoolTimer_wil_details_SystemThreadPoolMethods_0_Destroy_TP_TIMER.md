# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000833c`
- end: `0x180008370`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800079c4`
- `0x18000cbf8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008369`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000834d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000834d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000835b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000835b`

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
0x18000833c  push    rbx
0x18000833e  sub     rsp, 20h
0x180008342  xor     r9d, r9d; msWindowLength
0x180008345  xor     r8d, r8d; msPeriod
0x180008348  xor     edx, edx; pftDueTime
0x18000834a  mov     rbx, rcx
0x18000834d  call    cs:__imp_SetThreadpoolTimer
0x180008353  mov     edx, 1; fCancelPendingCallbacks
0x180008358  mov     rcx, rbx; pti
0x18000835b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008361  mov     rcx, rbx
0x180008364  add     rsp, 20h
0x180008368  pop     rbx
0x180008369  jmp     cs:__imp_CloseThreadpoolTimer
```
