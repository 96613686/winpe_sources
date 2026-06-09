# NhmCloseThreadCleanupGroup(_TP_CLEANUP_GROUP *)

- ea: `0x18005ea80`
- end: `0x18005eaa5`
- name: `?NhmCloseThreadCleanupGroup@@YAXPEAU_TP_CLEANUP_GROUP@@@Z`
- size: `37`
- prototype: `void __fastcall(struct _TP_CLEANUP_GROUP *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180044ae4`
- `0x18007b3f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005ea90`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005ea90`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005ea9e`

## pseudocode

```c
void __fastcall NhmCloseThreadCleanupGroup(struct _TP_CLEANUP_GROUP *a1)
{
  CloseThreadpoolCleanupGroupMembers(a1, 1, 0);
  CloseThreadpoolCleanupGroup(a1);
}

```

## disassembly

```asm
0x18005ea80  push    rbx
0x18005ea82  sub     rsp, 20h
0x18005ea86  xor     r8d, r8d; pvCleanupContext
0x18005ea89  mov     rbx, rcx
0x18005ea8c  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18005ea90  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18005ea96  mov     rcx, rbx
0x18005ea99  add     rsp, 20h
0x18005ea9d  pop     rbx
0x18005ea9e  jmp     cs:__imp_CloseThreadpoolCleanupGroup
```
