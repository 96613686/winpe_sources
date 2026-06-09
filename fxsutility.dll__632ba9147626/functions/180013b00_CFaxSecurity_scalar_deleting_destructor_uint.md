# CFaxSecurity::`scalar deleting destructor'(uint)

- ea: `0x180013b00`
- end: `0x180013b26`
- name: `??_GCFaxSecurity@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(CFaxSecurity *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012d0`
- `0x180013b00`

## pseudocode

```c
CFaxSecurity *__fastcall CFaxSecurity::`scalar deleting destructor'(CFaxSecurity *this, char a2)
{
  *(_QWORD *)this = &CFaxSecurity::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180013b00  push    rbx
0x180013b02  sub     rsp, 20h
0x180013b06  lea     rax, ??_7CFaxSecurity@@6B@; const CFaxSecurity::`vftable'
0x180013b0d  mov     rbx, rcx
0x180013b10  mov     [rcx], rax
0x180013b13  test    dl, 1
0x180013b16  jz      short loc_180013B1D
0x180013b18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013b1d  mov     rax, rbx
0x180013b20  add     rsp, 20h
0x180013b24  pop     rbx
0x180013b25  retn
```
