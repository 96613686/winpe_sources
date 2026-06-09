# _std::_Uninit_copy_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_ATL::CComVariant______ATL::CComVariant___std::allocator_ATL::CComVariant____::_1_::catch$0

- ea: `0x18001b7da`
- end: `0x18001b81d`
- name: `_std::_Uninit_copy_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_ATL::CComVariant______ATL::CComVariant___std::allocator_ATL::CComVariant____::_1_::catch$0`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a4ec`
- `0x18001b7da`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001b803`
- `OLEAUT32!__imp_VariantClear` at `0x18001b803`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_copy_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_ATL::CComVariant______ATL::CComVariant___std::allocator_ATL::CComVariant____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  VARIANTARG *i; // rbx

  for ( i = *(VARIANTARG **)(a2 + 72); i != *(VARIANTARG **)(a2 + 64); ++i )
  {
    if ( i->vt == 4095 )
      i->vt = 8;
    VariantClear(i);
  }
  throw;
}

```

## disassembly

```asm
0x18001b7da  mov     [rsp+arg_8], rdx
0x18001b7df  push    rbx
0x18001b7e0  push    rbp
0x18001b7e1  sub     rsp, 28h
0x18001b7e5  mov     rbp, rdx
0x18001b7e8  mov     rbx, [rbp+48h]
0x18001b7ec  jmp     short loc_18001B80D
0x18001b7ee  mov     eax, 0FFFh
0x18001b7f3  cmp     [rbx], ax
0x18001b7f6  jnz     short loc_18001B800
0x18001b7f8  mov     eax, 8
0x18001b7fd  mov     [rbx], ax
0x18001b800  mov     rcx, rbx; pvarg
0x18001b803  call    cs:__imp_VariantClear
0x18001b809  add     rbx, 18h
0x18001b80d  cmp     rbx, [rbp+40h]
0x18001b811  jnz     short loc_18001B7EE
0x18001b813  xor     edx, edx; pThrowInfo
0x18001b815  xor     ecx, ecx; pExceptionObject
0x18001b817  call    _CxxThrowException_0
```
