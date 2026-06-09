# LuafvLogDeleteFilePCAEvent

- ea: `0x1400181f4`
- end: `0x14001826a`
- name: `LuafvLogDeleteFilePCAEvent`
- size: `118`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140025350`

## callees

- `0x140005f30`
- `0x140006380`
- `0x14001897c`

## pseudocode

```c
__int64 __fastcall LuafvLogDeleteFilePCAEvent(int a1)
{
  struct _EVENT_DATA_DESCRIPTOR v3[7]; // [rsp+40h] [rbp-88h] BYREF

  memset(v3, 0, sizeof(v3));
  return LuafvLogFileEvent(a1, 0, 0, 0, &LuafvDeleteFileAccessDeniedEvent, v3, 7u);
}

```

## disassembly

```asm
0x1400181f4  push    rbx
0x1400181f6  sub     rsp, 0C0h
0x1400181fd  mov     rax, cs:__security_cookie
0x140018204  xor     rax, rsp
0x140018207  mov     [rsp+0C8h+var_18], rax
0x14001820f  xor     edx, edx; Val
0x140018211  mov     rbx, rcx
0x140018214  lea     rcx, [rsp+0C8h+var_88]; void *
0x140018219  lea     r8d, [rdx+70h]; Size
0x14001821d  call    memset
0x140018222  lea     rax, [rsp+0C8h+var_88]
0x140018227  mov     [rsp+0C8h+UserDataCount], 7; UserDataCount
0x14001822f  mov     [rsp+0C8h+var_A0], rax; PEVENT_DATA_DESCRIPTOR
0x140018234  xor     r9d, r9d; int
0x140018237  lea     rax, LuafvDeleteFileAccessDeniedEvent
0x14001823e  xor     r8d, r8d; int
0x140018241  xor     edx, edx; int
0x140018243  mov     [rsp+0C8h+EventDescriptor], rax; EventDescriptor
0x140018248  mov     rcx, rbx; int
0x14001824b  call    LuafvLogFileEvent
0x140018250  mov     rcx, [rsp+0C8h+var_18]
0x140018258  xor     rcx, rsp; StackCookie
0x14001825b  call    __security_check_cookie
0x140018260  add     rsp, 0C0h
0x140018267  pop     rbx
0x140018268  retn
```
