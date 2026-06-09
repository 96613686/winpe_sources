# _std::_Hash_std::tr1::_Umap_traits_HardwareAddress_VisibleDock_std::_Hash_compare_HardwareAddress_std::hash_HardwareAddress__std::equal_to_HardwareAddress____std::allocator_std::pair_HardwareAddress_const__VisibleDock____0___::_Insert_::_1_::catch$3

- ea: `0x18001e041`
- end: `0x18001e075`
- name: `_std::_Hash_std::tr1::_Umap_traits_HardwareAddress_VisibleDock_std::_Hash_compare_HardwareAddress_std::hash_HardwareAddress__std::equal_to_HardwareAddress____std::allocator_std::pair_HardwareAddress_const__VisibleDock____0___::_Insert_::_1_::catch$3`
- size: `52`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020bd`
- `0x18001a09c`
- `0x18001a0ac`

## pseudocode

```c
void __fastcall __noreturn std::_Hash_std::tr1::_Umap_traits_HardwareAddress_VisibleDock_std::_Hash_compare_HardwareAddress_std::hash_HardwareAddress__std::equal_to_HardwareAddress____std::allocator_std::pair_HardwareAddress_const__VisibleDock____0___::_Insert_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  int **iter; // rax

  iter = (int **)std::list<std::pair<HardwareAddress const,VisibleDock>>::_Make_iter(
                   a1,
                   (_QWORD *)(a2 + 112),
                   *(_QWORD *)(a2 + 120));
  std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::erase(
    *(_QWORD **)(a2 + 96),
    (_QWORD *)(a2 + 32),
    *iter);
  throw;
}

```

## disassembly

```asm
0x18001e041  mov     [rsp+arg_8], rdx
0x18001e046  push    rbp
0x18001e047  sub     rsp, 20h
0x18001e04b  mov     rbp, rdx
0x18001e04e  mov     r8, [rbp+78h]
0x18001e052  lea     rdx, [rbp+70h]
0x18001e056  call    ?_Make_iter@?$list@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@QEBA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@@Z; std::list<std::pair<HardwareAddress const,VisibleDock>>::_Make_iter(std::_List_const_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>)
0x18001e05b  mov     r8, [rax]
0x18001e05e  lea     rdx, [rbp+20h]
0x18001e062  mov     rcx, [rbp+60h]
0x18001e066  call    ?erase@?$_Hash@V?$_Umap_traits@VHardwareAddress@@VVisibleDock@@V?$_Hash_compare@VHardwareAddress@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@3@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>)
0x18001e06b  xor     edx, edx; pThrowInfo
0x18001e06d  xor     ecx, ecx; pExceptionObject
0x18001e06f  call    _CxxThrowException_0
```
