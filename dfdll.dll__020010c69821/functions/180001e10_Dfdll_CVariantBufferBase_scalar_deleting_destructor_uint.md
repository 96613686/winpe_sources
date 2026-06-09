# Dfdll::CVariantBufferBase::`scalar deleting destructor'(uint)

- ea: `0x180001e10`
- end: `0x180001e82`
- name: `??_GCVariantBufferBase@Dfdll@@UEAAPEAXI@Z`
- size: `114`
- prototype: `void *__fastcall(Dfdll::CVariantBufferBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180001e10`
- `0x180002de0`
- `0x180012b30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Dfdll::CVariantBufferBase *__fastcall Dfdll::CVariantBufferBase::`scalar deleting destructor'(
        Dfdll::CVariantBufferBase *this,
        char a2)
{
  *(_QWORD *)this = &Dfdll::CVariantBufferBase::`vftable';
  Dfdll::CVariantBufferBase::Free(this, (VARIANTARG **)this + 1, (unsigned int *)this + 4);
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x18);
  return this;
}

```

## disassembly

```asm
0x180001e10  mov     [rsp+arg_0], rbx
0x180001e15  mov     [rsp+arg_8], rsi
0x180001e1a  mov     [rsp+arg_10], rdi
0x180001e1f  push    r14
0x180001e21  sub     rsp, 20h
0x180001e25  mov     esi, edx
0x180001e27  mov     r14, rcx
0x180001e2a  lea     rax, ??_7CVariantBufferBase@Dfdll@@6B@; const Dfdll::CVariantBufferBase::`vftable'
0x180001e31  mov     [rcx], rax
0x180001e34  lea     r8, [rcx+10h]; unsigned int *
0x180001e38  lea     rdx, [rcx+8]; void **
0x180001e3c  call    ?Free@CVariantBufferBase@Dfdll@@MEAAXAEAPEAXAEAI@Z; Dfdll::CVariantBufferBase::Free(void * &,uint &)
0x180001e41  nop
0x180001e42  and     qword ptr [r14+8], 0
0x180001e47  and     dword ptr [r14+10h], 0
0x180001e4c  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001e53  mov     [r14], rax
0x180001e56  test    sil, 1
0x180001e5a  jz      short loc_180001E69
0x180001e5c  mov     edx, 18h; struct std::nothrow_t *
0x180001e61  mov     rcx, r14; void *
0x180001e64  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001e69  mov     rax, r14
0x180001e6c  mov     rbx, [rsp+28h+arg_0]
0x180001e71  mov     rsi, [rsp+28h+arg_8]
0x180001e76  mov     rdi, [rsp+28h+arg_10]
0x180001e7b  add     rsp, 20h
0x180001e7f  pop     r14
0x180001e81  retn
```
