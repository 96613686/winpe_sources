# CACSecurityContext::~CACSecurityContext(void)

- ea: `0x140003aa0`
- end: `0x140003aca`
- name: `??1CACSecurityContext@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(CACSecurityContext *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003af0`

## callees

- `0x1400010a4`

## pseudocode

```c
void __fastcall CACSecurityContext::~CACSecurityContext(void **this)
{
  operator delete(*this);
  operator delete(this[1]);
  operator delete(this[2]);
}

```

## disassembly

```asm
0x140003aa0  push    rbx
0x140003aa2  sub     rsp, 20h
0x140003aa6  mov     rbx, rcx
0x140003aa9  mov     rcx, [rcx]; void *
0x140003aac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003ab1  mov     rcx, [rbx+8]; void *
0x140003ab5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003aba  mov     rcx, [rbx+10h]; void *
0x140003abe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003ac3  add     rsp, 20h
0x140003ac7  pop     rbx
0x140003ac8  retn
```
