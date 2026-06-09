# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800eb934`
- end: `0x1800eb979`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800e5b74`
- `0x1800e5bcc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800eb945`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800eb945`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800eb96d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800eb959`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800eb959`

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
0x1800eb934  push    rbx
0x1800eb936  sub     rsp, 20h
0x1800eb93a  xor     r9d, r9d; msWindowLength
0x1800eb93d  xor     r8d, r8d; msPeriod
0x1800eb940  xor     edx, edx; pftDueTime
0x1800eb942  mov     rbx, rcx
0x1800eb945  call    cs:__imp_SetThreadpoolTimer
0x1800eb94c  nop     dword ptr [rax+rax+00h]
0x1800eb951  mov     edx, 1; fCancelPendingCallbacks
0x1800eb956  mov     rcx, rbx; pti
0x1800eb959  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800eb960  nop     dword ptr [rax+rax+00h]
0x1800eb965  mov     rcx, rbx
0x1800eb968  add     rsp, 20h
0x1800eb96c  pop     rbx
0x1800eb96d  jmp     cs:__imp_CloseThreadpoolTimer
```
