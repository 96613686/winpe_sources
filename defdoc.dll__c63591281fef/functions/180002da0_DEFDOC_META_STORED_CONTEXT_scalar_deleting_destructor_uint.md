# DEFDOC_META_STORED_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x180002da0`
- end: `0x180002dde`
- name: `??_GDEFDOC_META_STORED_CONTEXT@@EEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(DEFDOC_META_STORED_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180002da0`

## import_xrefs

- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002dbd`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002dbd`

## pseudocode

```c
DEFDOC_META_STORED_CONTEXT *__fastcall DEFDOC_META_STORED_CONTEXT::`scalar deleting destructor'(
        DEFDOC_META_STORED_CONTEXT *this,
        char a2)
{
  *(_QWORD *)this = &DEFDOC_META_STORED_CONTEXT::`vftable';
  MULTISZ::~MULTISZ((DEFDOC_META_STORED_CONTEXT *)((char *)this + 16));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002da0  mov     [rsp+arg_0], rbx
0x180002da5  push    rdi
0x180002da6  sub     rsp, 20h
0x180002daa  lea     rax, ??_7DEFDOC_META_STORED_CONTEXT@@6B@; const DEFDOC_META_STORED_CONTEXT::`vftable'
0x180002db1  mov     rdi, rcx
0x180002db4  mov     [rcx], rax
0x180002db7  mov     ebx, edx
0x180002db9  add     rcx, 10h
0x180002dbd  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180002dc3  test    bl, 1
0x180002dc6  jz      short loc_180002DD0
0x180002dc8  mov     rcx, rdi; Block
0x180002dcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002dd0  mov     rbx, [rsp+28h+arg_0]
0x180002dd5  mov     rax, rdi
0x180002dd8  add     rsp, 20h
0x180002ddc  pop     rdi
0x180002ddd  retn
```
