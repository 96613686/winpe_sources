# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800e9160`
- end: `0x1800e9194`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800e7c88`
- `0x1800f126c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e917f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e917f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e918d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e9171`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e9171`

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
0x1800e9160  push    rbx
0x1800e9162  sub     rsp, 20h
0x1800e9166  xor     r9d, r9d; msWindowLength
0x1800e9169  xor     r8d, r8d; msPeriod
0x1800e916c  xor     edx, edx; pftDueTime
0x1800e916e  mov     rbx, rcx
0x1800e9171  call    cs:__imp_SetThreadpoolTimer
0x1800e9177  mov     edx, 1; fCancelPendingCallbacks
0x1800e917c  mov     rcx, rbx; pti
0x1800e917f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e9185  mov     rcx, rbx
0x1800e9188  add     rsp, 20h
0x1800e918c  pop     rbx
0x1800e918d  jmp     cs:__imp_CloseThreadpoolTimer
```
