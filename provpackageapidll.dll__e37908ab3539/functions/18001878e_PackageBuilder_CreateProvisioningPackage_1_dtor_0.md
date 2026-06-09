# _PackageBuilder::CreateProvisioningPackage_::_1_::dtor$0

- ea: `0x18001878e`
- end: `0x1800187ab`
- name: `_PackageBuilder::CreateProvisioningPackage_::_1_::dtor$0`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800020a8`

## pseudocode

```c
void __fastcall PackageBuilder::CreateProvisioningPackage_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80), (const struct std::nothrow_t *)0x60);
}

```

## disassembly

```asm
0x18001878e  push    rbp
0x180018790  sub     rsp, 20h
0x180018794  mov     rbp, rdx
0x180018797  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x18001879c  mov     rcx, [rbp+50h]; void *
0x1800187a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800187a5  add     rsp, 20h
0x1800187a9  pop     rbp
0x1800187aa  retn
```
