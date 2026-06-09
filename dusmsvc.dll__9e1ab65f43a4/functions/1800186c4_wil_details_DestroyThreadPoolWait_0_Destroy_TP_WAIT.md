# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x1800186c4`
- end: `0x1800186f5`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180018358`
- `0x18003de20`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800186d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800186d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800186ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800186e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800186e0`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolWait<0>::Destroy(PTP_WAIT pwa)
{
  SetThreadpoolWait(pwa, 0, 0);
  WaitForThreadpoolWaitCallbacks(pwa, 1);
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x1800186c4  push    rbx
0x1800186c6  sub     rsp, 20h
0x1800186ca  xor     r8d, r8d; pftTimeout
0x1800186cd  xor     edx, edx; h
0x1800186cf  mov     rbx, rcx
0x1800186d2  call    cs:__imp_SetThreadpoolWait
0x1800186d8  mov     edx, 1; fCancelPendingCallbacks
0x1800186dd  mov     rcx, rbx; pwa
0x1800186e0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800186e6  mov     rcx, rbx
0x1800186e9  add     rsp, 20h
0x1800186ed  pop     rbx
0x1800186ee  jmp     cs:__imp_CloseThreadpoolWait
```
