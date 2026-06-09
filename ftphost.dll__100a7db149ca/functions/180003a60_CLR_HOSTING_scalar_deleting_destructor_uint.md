# CLR_HOSTING::`scalar deleting destructor'(uint)

- ea: `0x180003a60`
- end: `0x180003aa4`
- name: `??_GCLR_HOSTING@@EEAAPEAXI@Z`
- size: `68`
- prototype: `void *__fastcall(CLR_HOSTING *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180003a18`
- `0x180003a60`

## pseudocode

```c
CLR_HOSTING *__fastcall CLR_HOSTING::`scalar deleting destructor'(CLR_HOSTING *this, char a2)
{
  *(_QWORD *)this = &CLR_HOSTING_LEGACY::`vftable'{for `CLR_HOSTING_BASE'};
  *((_QWORD *)this + 4) = &CLR_HOSTING_LEGACY::`vftable'{for `IClrHostingHelper'};
  CLR_HOSTING_BASE::~CLR_HOSTING_BASE(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003a60  mov     [rsp+arg_0], rbx
0x180003a65  push    rdi
0x180003a66  sub     rsp, 20h
0x180003a6a  lea     rax, ??_7CLR_HOSTING_LEGACY@@6BCLR_HOSTING_BASE@@@; const CLR_HOSTING_LEGACY::`vftable'{for `CLR_HOSTING_BASE'}
0x180003a71  mov     ebx, edx
0x180003a73  mov     [rcx], rax
0x180003a76  mov     rdi, rcx
0x180003a79  lea     rax, ??_7CLR_HOSTING_LEGACY@@6BIClrHostingHelper@@@; const CLR_HOSTING_LEGACY::`vftable'{for `IClrHostingHelper'}
0x180003a80  mov     [rcx+20h], rax
0x180003a84  call    ??1CLR_HOSTING_BASE@@MEAA@XZ; CLR_HOSTING_BASE::~CLR_HOSTING_BASE(void)
0x180003a89  test    bl, 1
0x180003a8c  jz      short loc_180003A96
0x180003a8e  mov     rcx, rdi; Block
0x180003a91  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a96  mov     rbx, [rsp+28h+arg_0]
0x180003a9b  mov     rax, rdi
0x180003a9e  add     rsp, 20h
0x180003aa2  pop     rdi
0x180003aa3  retn
```
