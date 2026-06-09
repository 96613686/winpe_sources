# IoctlIpcCleanupSilo

- ea: `0x180027e58`
- end: `0x180027eb3`
- name: `IoctlIpcCleanupSilo`
- size: `91`
- prototype: `PLIST_ENTRY __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800280a0`

## callees

- `0x1800075c4`
- `0x180027e58`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180027e91`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180027e91`

## pseudocode

```c
PLIST_ENTRY __fastcall IoctlIpcCleanupSilo(__int64 a1)
{
  KSPIN_LOCK *v2; // rdi
  struct _LIST_ENTRY *v3; // rsi
  PLIST_ENTRY result; // rax

  v2 = (KSPIN_LOCK *)(a1 + 160);
  v3 = (struct _LIST_ENTRY *)(a1 + 168);
  while ( 1 )
  {
    result = ExInterlockedRemoveHeadList(v3, v2);
    if ( !result )
      break;
    PendingCallFailure(a1, result, 0xC0000120);
  }
  return result;
}

```

## disassembly

```asm
0x180027e58  mov     [rsp+arg_0], rbx
0x180027e5d  mov     [rsp+arg_8], rsi
0x180027e62  push    rdi
0x180027e63  sub     rsp, 20h
0x180027e67  mov     rbx, rcx
0x180027e6a  lea     rdi, [rcx+0A0h]
0x180027e71  lea     rsi, [rcx+0A8h]
0x180027e78  jmp     short loc_180027E8B
0x180027e7a  mov     r8d, 0C0000120h
0x180027e80  mov     rdx, rax
0x180027e83  mov     rcx, rbx
0x180027e86  call    PendingCallFailure
0x180027e8b  mov     rdx, rdi; Lock
0x180027e8e  mov     rcx, rsi; ListHead
0x180027e91  call    cs:__imp_ExInterlockedRemoveHeadList
0x180027e98  nop     dword ptr [rax+rax+00h]
0x180027e9d  test    rax, rax
0x180027ea0  jnz     short loc_180027E7A
0x180027ea2  mov     rbx, [rsp+28h+arg_0]
0x180027ea7  mov     rsi, [rsp+28h+arg_8]
0x180027eac  add     rsp, 20h
0x180027eb0  pop     rdi
0x180027eb1  retn
```
