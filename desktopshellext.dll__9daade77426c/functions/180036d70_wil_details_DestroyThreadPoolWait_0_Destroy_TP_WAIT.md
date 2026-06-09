# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180036d70`
- end: `0x180036da1`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011da0`
- `0x180017ed8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180036d7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180036d7e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180036d8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180036d8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180036d9a`

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
0x180036d70  push    rbx
0x180036d72  sub     rsp, 20h
0x180036d76  xor     r8d, r8d; pftTimeout
0x180036d79  xor     edx, edx; h
0x180036d7b  mov     rbx, rcx
0x180036d7e  call    cs:__imp_SetThreadpoolWait
0x180036d84  mov     edx, 1; fCancelPendingCallbacks
0x180036d89  mov     rcx, rbx; pwa
0x180036d8c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180036d92  mov     rcx, rbx
0x180036d95  add     rsp, 20h
0x180036d99  pop     rbx
0x180036d9a  jmp     cs:__imp_CloseThreadpoolWait
```
