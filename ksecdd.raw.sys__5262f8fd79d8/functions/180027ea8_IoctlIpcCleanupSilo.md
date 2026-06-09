# IoctlIpcCleanupSilo

- ea: `0x180027ea8`
- end: `0x180027f03`
- name: `IoctlIpcCleanupSilo`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800280f0`

## callees

- `0x1800075c4`
- `0x180027ea8`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180027ee1`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180027ee1`

## pseudocode

```c
struct _LIST_ENTRY *__fastcall IoctlIpcCleanupSilo(__int64 a1)
{
  KSPIN_LOCK *v2; // rdi
  struct _LIST_ENTRY *v3; // rsi
  struct _LIST_ENTRY *result; // rax

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
0x180027ea8  mov     [rsp+arg_0], rbx
0x180027ead  mov     [rsp+arg_8], rsi
0x180027eb2  push    rdi
0x180027eb3  sub     rsp, 20h
0x180027eb7  mov     rbx, rcx
0x180027eba  lea     rdi, [rcx+0A0h]
0x180027ec1  lea     rsi, [rcx+0A8h]
0x180027ec8  jmp     short loc_180027EDB
0x180027eca  mov     r8d, 0C0000120h
0x180027ed0  mov     rdx, rax
0x180027ed3  mov     rcx, rbx
0x180027ed6  call    PendingCallFailure
0x180027edb  mov     rdx, rdi; Lock
0x180027ede  mov     rcx, rsi; ListHead
0x180027ee1  call    cs:__imp_ExInterlockedRemoveHeadList
0x180027ee8  nop     dword ptr [rax+rax+00h]
0x180027eed  test    rax, rax
0x180027ef0  jnz     short loc_180027ECA
0x180027ef2  mov     rbx, [rsp+28h+arg_0]
0x180027ef7  mov     rsi, [rsp+28h+arg_8]
0x180027efc  add     rsp, 20h
0x180027f00  pop     rdi
0x180027f01  retn
```
