# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180117280`
- end: `0x1801172b1`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180081130`
- `0x18011719c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18011728e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18011728e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801172aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18011729c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18011729c`

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
0x180117280  push    rbx
0x180117282  sub     rsp, 20h
0x180117286  xor     r8d, r8d; pftTimeout
0x180117289  xor     edx, edx; h
0x18011728b  mov     rbx, rcx
0x18011728e  call    cs:__imp_SetThreadpoolWait
0x180117294  mov     edx, 1; fCancelPendingCallbacks
0x180117299  mov     rcx, rbx; pwa
0x18011729c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1801172a2  mov     rcx, rbx
0x1801172a5  add     rsp, 20h
0x1801172a9  pop     rbx
0x1801172aa  jmp     cs:__imp_CloseThreadpoolWait
```
