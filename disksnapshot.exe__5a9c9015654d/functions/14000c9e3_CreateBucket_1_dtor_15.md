# _CreateBucket_::_1_::dtor$15

- ea: `0x14000c9e3`
- end: `0x14000c9ef`
- name: `_CreateBucket_::_1_::dtor$15`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400055f4`

## pseudocode

```c
void __fastcall CreateBucket_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  std::_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>(a2 + 80);
}

```

## disassembly

```asm
0x14000c9e3  lea     rcx, [rdx+50h]
0x14000c9ea  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAU_RULE_BUCKET@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>(void)
```
