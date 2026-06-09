# LuafvLogDeleteFilePCAEvent

- ea: `0x1400181a4`
- end: `0x14001821a`
- name: `LuafvLogDeleteFilePCAEvent`
- size: `118`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140025300`

## callees

- `0x140005bb0`
- `0x140006000`
- `0x14001892c`

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
0x1400181a4  push    rbx
0x1400181a6  sub     rsp, 0C0h
0x1400181ad  mov     rax, cs:__security_cookie
0x1400181b4  xor     rax, rsp
0x1400181b7  mov     [rsp+0C8h+var_18], rax
0x1400181bf  xor     edx, edx; Val
0x1400181c1  mov     rbx, rcx
0x1400181c4  lea     rcx, [rsp+0C8h+var_88]; void *
0x1400181c9  lea     r8d, [rdx+70h]; Size
0x1400181cd  call    memset
0x1400181d2  lea     rax, [rsp+0C8h+var_88]
0x1400181d7  mov     [rsp+0C8h+UserDataCount], 7; UserDataCount
0x1400181df  mov     [rsp+0C8h+var_A0], rax; PEVENT_DATA_DESCRIPTOR
0x1400181e4  xor     r9d, r9d; int
0x1400181e7  lea     rax, LuafvDeleteFileAccessDeniedEvent
0x1400181ee  xor     r8d, r8d; int
0x1400181f1  xor     edx, edx; int
0x1400181f3  mov     [rsp+0C8h+EventDescriptor], rax; EventDescriptor
0x1400181f8  mov     rcx, rbx; int
0x1400181fb  call    LuafvLogFileEvent
0x140018200  mov     rcx, [rsp+0C8h+var_18]
0x140018208  xor     rcx, rsp; StackCookie
0x14001820b  call    __security_check_cookie
0x140018210  add     rsp, 0C0h
0x140018217  pop     rbx
0x140018218  retn
```
