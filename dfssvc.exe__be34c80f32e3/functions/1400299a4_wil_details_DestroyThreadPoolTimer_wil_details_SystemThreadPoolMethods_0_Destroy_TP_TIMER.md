# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400299a4`
- end: `0x1400299e9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400279cc`
- `0x140031eac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400299b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400299b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400299c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400299c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400299dd`

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
0x1400299a4  push    rbx
0x1400299a6  sub     rsp, 20h
0x1400299aa  xor     r9d, r9d; msWindowLength
0x1400299ad  xor     r8d, r8d; msPeriod
0x1400299b0  xor     edx, edx; pftDueTime
0x1400299b2  mov     rbx, rcx
0x1400299b5  call    cs:__imp_SetThreadpoolTimer
0x1400299bc  nop     dword ptr [rax+rax+00h]
0x1400299c1  mov     edx, 1; fCancelPendingCallbacks
0x1400299c6  mov     rcx, rbx; pti
0x1400299c9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400299d0  nop     dword ptr [rax+rax+00h]
0x1400299d5  mov     rcx, rbx
0x1400299d8  add     rsp, 20h
0x1400299dc  pop     rbx
0x1400299dd  jmp     cs:__imp_CloseThreadpoolTimer
```
