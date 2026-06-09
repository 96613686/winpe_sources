# _TDataGetter_unsigned_short___std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::vector_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________TNDFDeallocator_unsigned_short_____&FreeDependencies__&CopyAndAllocateDependency__::_1_::dtor$0

- ea: `0x180013f4d`
- end: `0x180013f59`
- name: `_TDataGetter_unsigned_short___std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::vector_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________TNDFDeallocator_unsigned_short_____&FreeDependencies__&CopyAndAllocateDependency__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c914`

## pseudocode

```c
void __fastcall TDataGetter_unsigned_short___std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::vector_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________TNDFDeallocator_unsigned_short______FreeDependencies___CopyAndAllocateDependency__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  TNDFDeallocator<unsigned short * *,&void FreeDependencies(unsigned short * *,unsigned long,int)>::~TNDFDeallocator<unsigned short * *,&void FreeDependencies(unsigned short * *,unsigned long,int)>(a2 + 32);
}

```

## disassembly

```asm
0x180013f4d  lea     rcx, [rdx+20h]
0x180013f54  jmp     ??1?$TNDFDeallocator@PEAPEAG$1?FreeDependencies@@YAXPEAPEAGKH@Z@@QEAA@XZ; TNDFDeallocator<ushort * *,&FreeDependencies(ushort * *,ulong,int)>::~TNDFDeallocator<ushort * *,&FreeDependencies(ushort * *,ulong,int)>(void)
```
