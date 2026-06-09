# CDLinkList::`vector deleting destructor'(uint)

- ea: `0x180012e60`
- end: `0x180012ec0`
- name: `??_ECDLinkList@@UEAAPEAXI@Z`
- size: `96`
- prototype: `void *__fastcall(CDLinkList *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180009f38`
- `0x180012e60`
- `0x18001b010`

## pseudocode

```c
CDLinkList *__fastcall CDLinkList::`vector deleting destructor'(CDLinkList *this, char a2)
{
  __int64 i; // rcx

  *(_QWORD *)this = &CDLinkList::`vftable';
  for ( i = *((_QWORD *)this + 1); i; i = *((_QWORD *)this + 1) )
  {
    *((_QWORD *)this + 1) = *(_QWORD *)(i + 8);
    (**(void (__fastcall ***)(__int64, __int64))i)(i, 1);
  }
  *((_QWORD *)this + 2) = 0;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180012e60  mov     [rsp+arg_0], rbx
0x180012e65  push    rdi
0x180012e66  sub     rsp, 20h
0x180012e6a  lea     rax, ??_7CDLinkList@@6B@; const CDLinkList::`vftable'
0x180012e71  mov     rbx, rcx
0x180012e74  mov     [rcx], rax
0x180012e77  mov     edi, edx
0x180012e79  mov     rcx, [rcx+8]
0x180012e7d  jmp     short loc_180012E9B
0x180012e7f  mov     rax, [rcx+8]
0x180012e83  mov     edx, 1
0x180012e88  mov     [rbx+8], rax
0x180012e8c  mov     rax, [rcx]
0x180012e8f  mov     rax, [rax]
0x180012e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e97  mov     rcx, [rbx+8]
0x180012e9b  test    rcx, rcx
0x180012e9e  jnz     short loc_180012E7F
0x180012ea0  mov     [rbx+10h], rcx
0x180012ea4  test    dil, 1
0x180012ea8  jz      short loc_180012EB2
0x180012eaa  mov     rcx, rbx; Block
0x180012ead  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012eb2  mov     rax, rbx
0x180012eb5  mov     rbx, [rsp+28h+arg_0]
0x180012eba  add     rsp, 20h
0x180012ebe  pop     rdi
0x180012ebf  retn
```
