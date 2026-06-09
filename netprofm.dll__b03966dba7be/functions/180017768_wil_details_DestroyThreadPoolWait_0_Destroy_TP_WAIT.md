# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180017768`
- end: `0x180017799`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `void __fastcall(PTP_WAIT pwa)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180009d98`
- `0x18000aa08`
- `0x18002ae7c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180017784`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180017784`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017776`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017776`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180017792`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details::DestroyThreadPoolWait<0>::Destroy(PTP_WAIT pwa)
{
  SetThreadpoolWait(pwa, 0, 0);
  WaitForThreadpoolWaitCallbacks(pwa, 1);
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x180017768  push    rbx
0x18001776a  sub     rsp, 20h
0x18001776e  xor     r8d, r8d; pftTimeout
0x180017771  xor     edx, edx; h
0x180017773  mov     rbx, rcx
0x180017776  call    cs:__imp_SetThreadpoolWait
0x18001777c  mov     edx, 1; fCancelPendingCallbacks
0x180017781  mov     rcx, rbx; pwa
0x180017784  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18001778a  mov     rcx, rbx
0x18001778d  add     rsp, 20h
0x180017791  pop     rbx
0x180017792  jmp     cs:__imp_CloseThreadpoolWait
```
