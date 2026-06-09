# CWMReadSample::`scalar deleting destructor'(uint)

- ea: `0x180008160`
- end: `0x180008194`
- name: `??_GCWMReadSample@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CWMReadSample *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800080a0`

## callees

- `0x180001008`
- `0x180008028`
- `0x180008160`

## pseudocode

```c
CWMReadSample *__fastcall CWMReadSample::`scalar deleting destructor'(CWMReadSample *this, char a2)
{
  CWMReadSample::~CWMReadSample(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008160  mov     [rsp+arg_0], rbx
0x180008165  push    rdi
0x180008166  sub     rsp, 20h
0x18000816a  mov     ebx, edx
0x18000816c  mov     rdi, rcx
0x18000816f  call    ??1CWMReadSample@@UEAA@XZ; CWMReadSample::~CWMReadSample(void)
0x180008174  test    bl, 1
0x180008177  jz      short loc_180008186
0x180008179  mov     edx, 50h ; 'P'; unsigned __int64
0x18000817e  mov     rcx, rdi; void *
0x180008181  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008186  mov     rbx, [rsp+28h+arg_0]
0x18000818b  mov     rax, rdi
0x18000818e  add     rsp, 20h
0x180008192  pop     rdi
0x180008193  retn
```
