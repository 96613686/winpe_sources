# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180044288`
- end: `0x1800442b9`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `void __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180042be8`
- `0x18005d154`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800442b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800442a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800442a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180044296`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180044296`

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
0x180044288  push    rbx
0x18004428a  sub     rsp, 20h
0x18004428e  xor     r8d, r8d; pftTimeout
0x180044291  xor     edx, edx; h
0x180044293  mov     rbx, rcx
0x180044296  call    cs:__imp_SetThreadpoolWait
0x18004429c  mov     edx, 1; fCancelPendingCallbacks
0x1800442a1  mov     rcx, rbx; pwa
0x1800442a4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800442aa  mov     rcx, rbx
0x1800442ad  add     rsp, 20h
0x1800442b1  pop     rbx
0x1800442b2  jmp     cs:__imp_CloseThreadpoolWait
```
