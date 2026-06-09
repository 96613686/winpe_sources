# Dfdll::CVariant::`scalar deleting destructor'(uint)

- ea: `0x180001d80`
- end: `0x180001dc4`
- name: `??_GCVariant@Dfdll@@UEAAPEAXI@Z`
- size: `68`
- prototype: `void *__fastcall(Dfdll::CVariant *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001d80`
- `0x180012b30`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180001d9d`
- `OLEAUT32!__imp_VariantClear` at `0x180001d9d`

## pseudocode

```c
Dfdll::CVariant *__fastcall Dfdll::CVariant::`scalar deleting destructor'(Dfdll::CVariant *this, char a2)
{
  *(_QWORD *)this = &Dfdll::CVariant::`vftable';
  VariantClear((VARIANTARG *)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x20);
  return this;
}

```

## disassembly

```asm
0x180001d80  mov     [rsp+arg_0], rbx
0x180001d85  push    rdi
0x180001d86  sub     rsp, 20h
0x180001d8a  mov     ebx, edx
0x180001d8c  mov     rdi, rcx
0x180001d8f  lea     rax, ??_7CVariant@Dfdll@@6B@; const Dfdll::CVariant::`vftable'
0x180001d96  mov     [rcx], rax
0x180001d99  add     rcx, 8; pvarg
0x180001d9d  call    cs:__imp_VariantClear
0x180001da3  nop
0x180001da4  test    bl, 1
0x180001da7  jz      short loc_180001DB6
0x180001da9  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180001dae  mov     rcx, rdi; void *
0x180001db1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001db6  mov     rax, rdi
0x180001db9  mov     rbx, [rsp+28h+arg_0]
0x180001dbe  add     rsp, 20h
0x180001dc2  pop     rdi
0x180001dc3  retn
```
