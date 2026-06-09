# QueryDirCache::`scalar deleting destructor'(uint)

- ea: `0x1400037c0`
- end: `0x1400037f0`
- name: `??_GQueryDirCache@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(QueryDirCache *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140001e30`
- `0x1400037c0`
- `0x14001665c`

## pseudocode

```c
QueryDirCache *__fastcall QueryDirCache::`scalar deleting destructor'(QueryDirCache *this, __int64 a2, __int64 a3)
{
  char v3; // bl

  v3 = a2;
  QueryDirCache::~QueryDirCache(this, a2, a3);
  if ( (v3 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400037c0  mov     [rsp+arg_0], rbx
0x1400037c5  push    rdi
0x1400037c6  sub     rsp, 20h
0x1400037ca  mov     ebx, edx
0x1400037cc  mov     rdi, rcx
0x1400037cf  call    ??1QueryDirCache@@UEAA@XZ; QueryDirCache::~QueryDirCache(void)
0x1400037d4  test    bl, 1
0x1400037d7  jz      short loc_1400037E1
0x1400037d9  mov     rcx, rdi; void *
0x1400037dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400037e1  mov     rbx, [rsp+28h+arg_0]
0x1400037e6  mov     rax, rdi
0x1400037e9  add     rsp, 20h
0x1400037ed  pop     rdi
0x1400037ee  retn
```
