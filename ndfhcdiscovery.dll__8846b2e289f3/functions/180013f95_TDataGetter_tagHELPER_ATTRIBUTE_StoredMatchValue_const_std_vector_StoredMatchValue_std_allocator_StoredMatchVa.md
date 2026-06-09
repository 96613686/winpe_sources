# _TDataGetter_tagHELPER_ATTRIBUTE_StoredMatchValue_const__std::vector_StoredMatchValue_std::allocator_StoredMatchValue____std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_StoredMatchValue______TNDFDeallocator_tagHELPER_ATTRIBUTE___&FreeHelperAttributes__&CopyAndAllocateMatchValue__::_1_::dtor$0

- ea: `0x180013f95`
- end: `0x180013fa1`
- name: `_TDataGetter_tagHELPER_ATTRIBUTE_StoredMatchValue_const__std::vector_StoredMatchValue_std::allocator_StoredMatchValue____std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_StoredMatchValue______TNDFDeallocator_tagHELPER_ATTRIBUTE___&FreeHelperAttributes__&CopyAndAllocateMatchValue__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c9f8`

## pseudocode

```c
__int64 __fastcall TDataGetter_tagHELPER_ATTRIBUTE_StoredMatchValue_const__std::vector_StoredMatchValue_std::allocator_StoredMatchValue____std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_StoredMatchValue______TNDFDeallocator_tagHELPER_ATTRIBUTE____FreeHelperAttributes___CopyAndAllocateMatchValue__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>(a2 + 32);
}

```

## disassembly

```asm
0x180013f95  lea     rcx, [rdx+20h]
0x180013f9c  jmp     ??1?$TNDFDeallocator@PEAUtagHELPER_ATTRIBUTE@@$1?FreeHelperAttributes@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>(void)
```
