# Dfdll::CObject::`vector deleting destructor'(uint)

- ea: `0x180001ca0`
- end: `0x180001ccb`
- name: `??_ECObject@Dfdll@@UEAAPEAXI@Z`
- size: `43`
- prototype: `void *__fastcall(Dfdll::CObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001ca0`
- `0x180012b30`

## pseudocode

```c
Dfdll::CObject *__fastcall Dfdll::CObject::`vector deleting destructor'(Dfdll::CObject *this, char a2)
{
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)8);
  return this;
}

```

## disassembly

```asm
0x180001ca0  push    rbx
0x180001ca2  sub     rsp, 20h
0x180001ca6  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001cad  mov     rbx, rcx
0x180001cb0  mov     [rcx], rax
0x180001cb3  test    dl, 1
0x180001cb6  jz      short loc_180001CC2
0x180001cb8  mov     edx, 8; struct std::nothrow_t *
0x180001cbd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001cc2  mov     rax, rbx
0x180001cc5  add     rsp, 20h
0x180001cc9  pop     rbx
0x180001cca  retn
```
