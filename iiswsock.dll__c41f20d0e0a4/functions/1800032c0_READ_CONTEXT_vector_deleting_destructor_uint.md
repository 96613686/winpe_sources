# READ_CONTEXT::`vector deleting destructor'(uint)

- ea: `0x1800032c0`
- end: `0x1800032f7`
- name: `??_EREAD_CONTEXT@@UEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(READ_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800032c0`

## pseudocode

```c
READ_CONTEXT *__fastcall READ_CONTEXT::`vector deleting destructor'(READ_CONTEXT *this, char a2)
{
  *(_QWORD *)this = &READ_CONTEXT::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800032c0  push    rbx
0x1800032c2  sub     rsp, 20h
0x1800032c6  lea     rax, ??_7READ_CONTEXT@@6B@; const READ_CONTEXT::`vftable'
0x1800032cd  mov     rbx, rcx
0x1800032d0  mov     [rcx], rax
0x1800032d3  xor     eax, eax
0x1800032d5  mov     [rcx+8], rax
0x1800032d9  mov     [rcx+10h], rax
0x1800032dd  mov     [rcx+18h], rax
0x1800032e1  mov     [rcx+20h], eax
0x1800032e4  test    dl, 1
0x1800032e7  jz      short loc_1800032EE
0x1800032e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800032ee  mov     rax, rbx
0x1800032f1  add     rsp, 20h
0x1800032f5  pop     rbx
0x1800032f6  retn
```
