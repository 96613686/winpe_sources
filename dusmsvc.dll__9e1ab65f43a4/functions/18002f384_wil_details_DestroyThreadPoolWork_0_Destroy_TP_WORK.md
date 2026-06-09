# wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)

- ea: `0x18002f384`
- end: `0x18002f3a7`
- name: `?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002effc`
- `0x180030330`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002f392`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002f392`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002f3a0`

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
0x18002f384  push    rbx
0x18002f386  sub     rsp, 20h
0x18002f38a  mov     edx, 1; fCancelPendingCallbacks
0x18002f38f  mov     rbx, rcx
0x18002f392  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002f398  mov     rcx, rbx
0x18002f39b  add     rsp, 20h
0x18002f39f  pop     rbx
0x18002f3a0  jmp     cs:__imp_CloseThreadpoolWork
```
