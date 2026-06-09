# Dfdll::CVariantArray::`scalar deleting destructor'(uint)

- ea: `0x180001dd0`
- end: `0x180001e04`
- name: `??_GCVariantArray@Dfdll@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(Dfdll::CVariantArray *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180001ad0`
- `0x180001dd0`
- `0x180012b30`

## pseudocode

```c
Dfdll::CVariantArray *__fastcall Dfdll::CVariantArray::`scalar deleting destructor'(
        Dfdll::CVariantArray *this,
        char a2)
{
  Dfdll::CVariantArray::~CVariantArray(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x28);
  return this;
}

```

## disassembly

```asm
0x180001dd0  mov     [rsp+arg_0], rbx
0x180001dd5  push    rdi
0x180001dd6  sub     rsp, 20h
0x180001dda  mov     ebx, edx
0x180001ddc  mov     rdi, rcx
0x180001ddf  call    ??1CVariantArray@Dfdll@@UEAA@XZ; Dfdll::CVariantArray::~CVariantArray(void)
0x180001de4  test    bl, 1
0x180001de7  jz      short loc_180001DF6
0x180001de9  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180001dee  mov     rcx, rdi; void *
0x180001df1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001df6  mov     rbx, [rsp+28h+arg_0]
0x180001dfb  mov     rax, rdi
0x180001dfe  add     rsp, 20h
0x180001e02  pop     rdi
0x180001e03  retn
```
