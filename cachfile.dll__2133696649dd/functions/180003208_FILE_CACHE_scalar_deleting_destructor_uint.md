# FILE_CACHE::`scalar deleting destructor'(uint)

- ea: `0x180003208`
- end: `0x180003228`
- name: `??_GFILE_CACHE@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(FILE_CACHE *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003720`
- `0x180003960`

## callees

- `0x180002920`

## import_xrefs

- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x180003211`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x180003211`

## pseudocode

```c
FILE_CACHE *__fastcall FILE_CACHE::`scalar deleting destructor'(FILE_CACHE *this)
{
  TREE_HASH_TABLE::~TREE_HASH_TABLE(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003208  push    rbx
0x18000320a  sub     rsp, 20h
0x18000320e  mov     rbx, rcx
0x180003211  call    cs:__imp_??1TREE_HASH_TABLE@@QEAA@XZ; TREE_HASH_TABLE::~TREE_HASH_TABLE(void)
0x180003217  mov     rcx, rbx; Block
0x18000321a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000321f  mov     rax, rbx
0x180003222  add     rsp, 20h
0x180003226  pop     rbx
0x180003227  retn
```
