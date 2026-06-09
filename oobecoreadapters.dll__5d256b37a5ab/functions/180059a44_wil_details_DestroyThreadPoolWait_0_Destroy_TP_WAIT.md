# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180059a44`
- end: `0x180059a75`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180058da8`
- `0x18005a8b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180059a52`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180059a52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180059a60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180059a60`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180059a6e`

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
0x180059a44  push    rbx
0x180059a46  sub     rsp, 20h
0x180059a4a  xor     r8d, r8d; pftTimeout
0x180059a4d  xor     edx, edx; h
0x180059a4f  mov     rbx, rcx
0x180059a52  call    cs:__imp_SetThreadpoolWait
0x180059a58  mov     edx, 1; fCancelPendingCallbacks
0x180059a5d  mov     rcx, rbx; pwa
0x180059a60  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180059a66  mov     rcx, rbx
0x180059a69  add     rsp, 20h
0x180059a6d  pop     rbx
0x180059a6e  jmp     cs:__imp_CloseThreadpoolWait
```
