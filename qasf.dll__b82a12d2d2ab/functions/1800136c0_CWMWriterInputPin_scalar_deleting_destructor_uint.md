# CWMWriterInputPin::`scalar deleting destructor'(uint)

- ea: `0x1800136c0`
- end: `0x1800136f4`
- name: `??_GCWMWriterInputPin@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CWMWriterInputPin *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180013568`
- `0x1800136c0`

## pseudocode

```c
CWMWriterInputPin *__fastcall CWMWriterInputPin::`scalar deleting destructor'(CWMWriterInputPin *this, char a2)
{
  CWMWriterInputPin::~CWMWriterInputPin(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800136c0  mov     [rsp+arg_0], rbx
0x1800136c5  push    rdi
0x1800136c6  sub     rsp, 20h
0x1800136ca  mov     ebx, edx
0x1800136cc  mov     rdi, rcx
0x1800136cf  call    ??1CWMWriterInputPin@@UEAA@XZ; CWMWriterInputPin::~CWMWriterInputPin(void)
0x1800136d4  test    bl, 1
0x1800136d7  jz      short loc_1800136E6
0x1800136d9  mov     edx, 210h; unsigned __int64
0x1800136de  mov     rcx, rdi; void *
0x1800136e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800136e6  mov     rbx, [rsp+28h+arg_0]
0x1800136eb  mov     rax, rdi
0x1800136ee  add     rsp, 20h
0x1800136f2  pop     rdi
0x1800136f3  retn
```
