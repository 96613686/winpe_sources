# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180040fd8`
- end: `0x18004101d`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800329cc`
- `0x180032a58`
- `0x180032a78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180041011`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180040ffd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180040ffd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180040fe9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180040fe9`

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
0x180040fd8  push    rbx
0x180040fda  sub     rsp, 20h
0x180040fde  xor     r9d, r9d; msWindowLength
0x180040fe1  xor     r8d, r8d; msPeriod
0x180040fe4  xor     edx, edx; pftDueTime
0x180040fe6  mov     rbx, rcx
0x180040fe9  call    cs:__imp_SetThreadpoolTimer
0x180040ff0  nop     dword ptr [rax+rax+00h]
0x180040ff5  mov     edx, 1; fCancelPendingCallbacks
0x180040ffa  mov     rcx, rbx; pti
0x180040ffd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180041004  nop     dword ptr [rax+rax+00h]
0x180041009  mov     rcx, rbx
0x18004100c  add     rsp, 20h
0x180041010  pop     rbx
0x180041011  jmp     cs:__imp_CloseThreadpoolTimer
```
