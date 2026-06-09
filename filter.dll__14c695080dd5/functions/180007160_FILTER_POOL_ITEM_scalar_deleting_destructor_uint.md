# FILTER_POOL_ITEM::`scalar deleting destructor'(uint)

- ea: `0x180007160`
- end: `0x18000717f`
- name: `??_GFILTER_POOL_ITEM@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(FILTER_POOL_ITEM *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a3e0`
- `0x18000a9d8`

## callees

- `0x180007190`
- `0x1800088fc`

## pseudocode

```c
FILTER_POOL_ITEM *__fastcall FILTER_POOL_ITEM::`scalar deleting destructor'(FILTER_POOL_ITEM *this)
{
  FILTER_POOL_ITEM::~FILTER_POOL_ITEM(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007160  push    rbx
0x180007162  sub     rsp, 20h
0x180007166  mov     rbx, rcx
0x180007169  call    ??1FILTER_POOL_ITEM@@QEAA@XZ; FILTER_POOL_ITEM::~FILTER_POOL_ITEM(void)
0x18000716e  mov     rcx, rbx; Block
0x180007171  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007176  mov     rax, rbx
0x180007179  add     rsp, 20h
0x18000717d  pop     rbx
0x18000717e  retn
```
