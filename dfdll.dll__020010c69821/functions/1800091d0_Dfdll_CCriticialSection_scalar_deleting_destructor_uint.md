# Dfdll::CCriticialSection::`scalar deleting destructor'(uint)

- ea: `0x1800091d0`
- end: `0x180009204`
- name: `??_GCCriticialSection@Dfdll@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(Dfdll::CCriticialSection *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180008b8c`
- `0x1800091d0`
- `0x180012b30`

## pseudocode

```c
Dfdll::CCriticialSection *__fastcall Dfdll::CCriticialSection::`scalar deleting destructor'(
        Dfdll::CCriticialSection *this,
        char a2)
{
  Dfdll::CCriticialSection::~CCriticialSection(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x40);
  return this;
}

```

## disassembly

```asm
0x1800091d0  mov     [rsp+arg_0], rbx
0x1800091d5  push    rdi
0x1800091d6  sub     rsp, 20h
0x1800091da  mov     ebx, edx
0x1800091dc  mov     rdi, rcx
0x1800091df  call    ??1CCriticialSection@Dfdll@@UEAA@XZ
0x1800091e4  test    bl, 1
0x1800091e7  jz      short loc_1800091F6
0x1800091e9  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x1800091ee  mov     rcx, rdi; void *
0x1800091f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800091f6  mov     rbx, [rsp+28h+arg_0]
0x1800091fb  mov     rax, rdi
0x1800091fe  add     rsp, 20h
0x180009202  pop     rdi
0x180009203  retn
```
