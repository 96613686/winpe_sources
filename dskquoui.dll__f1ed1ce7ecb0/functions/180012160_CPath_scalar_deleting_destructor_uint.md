# CPath::`scalar deleting destructor'(uint)

- ea: `0x180012160`
- end: `0x18001219e`
- name: `??_GCPath@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(CPath *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001534`
- `0x180012160`
- `0x180019ee0`

## pseudocode

```c
CPath *__fastcall CPath::`scalar deleting destructor'(CPath *this, char a2)
{
  *(_QWORD *)this = &CPath::`vftable';
  CString::~CString(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180012160  mov     [rsp+arg_0], rbx
0x180012165  push    rdi
0x180012166  sub     rsp, 20h
0x18001216a  lea     rax, ??_7CPath@@6B@; const CPath::`vftable'
0x180012171  mov     ebx, edx
0x180012173  mov     [rcx], rax
0x180012176  mov     rdi, rcx
0x180012179  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001217e  test    bl, 1
0x180012181  jz      short loc_180012190
0x180012183  mov     edx, 10h; unsigned __int64
0x180012188  mov     rcx, rdi; void *
0x18001218b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012190  mov     rbx, [rsp+28h+arg_0]
0x180012195  mov     rax, rdi
0x180012198  add     rsp, 20h
0x18001219c  pop     rdi
0x18001219d  retn
```
