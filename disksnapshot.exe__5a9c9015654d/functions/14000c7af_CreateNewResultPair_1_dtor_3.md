# _CreateNewResultPair_::_1_::dtor$3

- ea: `0x14000c7af`
- end: `0x14000c7bb`
- name: `_CreateNewResultPair_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400055f4`

## pseudocode

```c
void __fastcall CreateNewResultPair_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  std::_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x14000c7af  lea     rcx, [rdx+20h]
0x14000c7b6  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAU_RULE_BUCKET@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>(void)
```
