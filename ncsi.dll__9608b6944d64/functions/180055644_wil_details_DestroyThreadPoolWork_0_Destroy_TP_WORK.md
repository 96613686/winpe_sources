# wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)

- ea: `0x180055644`
- end: `0x180055667`
- name: `?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `35`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180029228`
- `0x18002e188`
- `0x1800436bc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180055652`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180055652`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180055660`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolWork<0>::Destroy(struct _TP_WORK *a1)
{
  WaitForThreadpoolWorkCallbacks(a1, 1);
  CloseThreadpoolWork(a1);
}

```

## disassembly

```asm
0x180055644  push    rbx
0x180055646  sub     rsp, 20h
0x18005564a  mov     edx, 1; fCancelPendingCallbacks
0x18005564f  mov     rbx, rcx
0x180055652  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180055658  mov     rcx, rbx
0x18005565b  add     rsp, 20h
0x18005565f  pop     rbx
0x180055660  jmp     cs:__imp_CloseThreadpoolWork
```
