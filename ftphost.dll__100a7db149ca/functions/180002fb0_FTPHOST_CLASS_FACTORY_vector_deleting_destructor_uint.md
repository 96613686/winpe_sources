# FTPHOST_CLASS_FACTORY::`vector deleting destructor'(uint)

- ea: `0x180002fb0`
- end: `0x180002fdd`
- name: `??_EFTPHOST_CLASS_FACTORY@@UEAAPEAXI@Z`
- size: `45`
- prototype: `void *__fastcall(FTPHOST_CLASS_FACTORY *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180002fb0`

## pseudocode

```c
FTPHOST_CLASS_FACTORY *__fastcall FTPHOST_CLASS_FACTORY::`vector deleting destructor'(
        FTPHOST_CLASS_FACTORY *this,
        char a2)
{
  *((_DWORD *)this + 2) = 1483958374;
  *(_QWORD *)this = &FTPHOST_CLASS_FACTORY::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002fb0  push    rbx
0x180002fb2  sub     rsp, 20h
0x180002fb6  mov     dword ptr [rcx+8], 58736866h
0x180002fbd  lea     rax, ??_7FTPHOST_CLASS_FACTORY@@6B@; const FTPHOST_CLASS_FACTORY::`vftable'
0x180002fc4  mov     [rcx], rax
0x180002fc7  mov     rbx, rcx
0x180002fca  test    dl, 1
0x180002fcd  jz      short loc_180002FD4
0x180002fcf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002fd4  mov     rax, rbx
0x180002fd7  add     rsp, 20h
0x180002fdb  pop     rbx
0x180002fdc  retn
```
