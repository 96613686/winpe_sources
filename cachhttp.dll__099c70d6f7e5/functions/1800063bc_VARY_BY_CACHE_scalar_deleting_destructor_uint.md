# VARY_BY_CACHE::`scalar deleting destructor'(uint)

- ea: `0x1800063bc`
- end: `0x1800063dc`
- name: `??_GVARY_BY_CACHE@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(VARY_BY_CACHE *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800039d0`
- `0x1800072b0`

## callees

- `0x180005a4c`

## import_xrefs

- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x1800063c5`
- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x1800063c5`

## pseudocode

```c
VARY_BY_CACHE *__fastcall VARY_BY_CACHE::`scalar deleting destructor'(VARY_BY_CACHE *this)
{
  TREE_HASH_TABLE::~TREE_HASH_TABLE(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800063bc  push    rbx
0x1800063be  sub     rsp, 20h
0x1800063c2  mov     rbx, rcx
0x1800063c5  call    cs:__imp_??1TREE_HASH_TABLE@@QEAA@XZ; TREE_HASH_TABLE::~TREE_HASH_TABLE(void)
0x1800063cb  mov     rcx, rbx; Block
0x1800063ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800063d3  mov     rax, rbx
0x1800063d6  add     rsp, 20h
0x1800063da  pop     rbx
0x1800063db  retn
```
