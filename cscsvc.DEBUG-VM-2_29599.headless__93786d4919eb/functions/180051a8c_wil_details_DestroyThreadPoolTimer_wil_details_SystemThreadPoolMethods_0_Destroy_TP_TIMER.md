# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180051a8c`
- end: `0x180051ac0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180050328`
- `0x180053758`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051a9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051a9d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051aab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051aab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180051ab9`

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
0x180051a8c  push    rbx
0x180051a8e  sub     rsp, 20h
0x180051a92  xor     r9d, r9d; msWindowLength
0x180051a95  xor     r8d, r8d; msPeriod
0x180051a98  xor     edx, edx; pftDueTime
0x180051a9a  mov     rbx, rcx
0x180051a9d  call    cs:__imp_SetThreadpoolTimer
0x180051aa3  mov     edx, 1; fCancelPendingCallbacks
0x180051aa8  mov     rcx, rbx; pti
0x180051aab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180051ab1  mov     rcx, rbx
0x180051ab4  add     rsp, 20h
0x180051ab8  pop     rbx
0x180051ab9  jmp     cs:__imp_CloseThreadpoolTimer
```
