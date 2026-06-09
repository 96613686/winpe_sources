# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180012b54`
- end: `0x180012b88`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bdc4`
- `0x18000ca08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012b65`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012b65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012b81`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012b73`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012b73`

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
0x180012b54  push    rbx
0x180012b56  sub     rsp, 20h
0x180012b5a  xor     r9d, r9d; msWindowLength
0x180012b5d  xor     r8d, r8d; msPeriod
0x180012b60  xor     edx, edx; pftDueTime
0x180012b62  mov     rbx, rcx
0x180012b65  call    cs:__imp_SetThreadpoolTimer
0x180012b6b  mov     edx, 1; fCancelPendingCallbacks
0x180012b70  mov     rcx, rbx; pti
0x180012b73  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012b79  mov     rcx, rbx
0x180012b7c  add     rsp, 20h
0x180012b80  pop     rbx
0x180012b81  jmp     cs:__imp_CloseThreadpoolTimer
```
