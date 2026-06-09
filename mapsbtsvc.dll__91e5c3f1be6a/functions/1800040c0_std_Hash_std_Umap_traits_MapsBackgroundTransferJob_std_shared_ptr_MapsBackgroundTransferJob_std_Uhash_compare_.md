# std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>(std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>> const &,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>> const &)

- ea: `0x1800040c0`
- end: `0x18000412e`
- name: `??0?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEAA@AEBV?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@1@AEBV?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@1@@Z`
- size: `110`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004168`

## callees

- `0x18000398c`
- `0x1800059f0`
- `0x180005a1c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>(
        __int64 a1,
        _DWORD *a2)
{
  _QWORD *v3; // rbx
  __int64 v4; // rcx

  *(_DWORD *)a1 = *a2;
  v3 = (_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Alloc_sentinel_and_proxy(a1 + 8);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>((_QWORD *)(a1 + 24));
  *(_QWORD *)(a1 + 48) = 7;
  *(_QWORD *)(a1 + 56) = 8;
  *(_DWORD *)a1 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>>>::_Assign_grow(
    v4,
    16,
    *v3);
  return a1;
}

```

## disassembly

```asm
0x1800040c0  mov     [rsp+arg_8], rbx
0x1800040c5  mov     [rsp+arg_0], rcx
0x1800040ca  push    rdi
0x1800040cb  sub     rsp, 20h
0x1800040cf  mov     rdi, rcx
0x1800040d2  mov     eax, [rdx]
0x1800040d4  mov     [rcx], eax
0x1800040d6  lea     rbx, [rcx+8]
0x1800040da  mov     qword ptr [rbx], 0
0x1800040e1  mov     qword ptr [rbx+8], 0
0x1800040e9  mov     rcx, rbx
0x1800040ec  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Alloc_sentinel_and_proxy(void)
0x1800040f1  nop
0x1800040f2  lea     rcx, [rdi+18h]
0x1800040f6  call    ??$?0AEBV?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>(std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>> const &)
0x1800040fb  nop
0x1800040fc  mov     qword ptr [rdi+30h], 7
0x180004104  mov     qword ptr [rdi+38h], 8
0x18000410c  mov     dword ptr [rdi], 3F800000h
0x180004112  mov     r8, [rbx]
0x180004115  mov     edx, 10h
0x18000411a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>)
0x18000411f  nop
0x180004120  mov     rax, rdi
0x180004123  mov     rbx, [rsp+28h+arg_8]
0x180004128  add     rsp, 20h
0x18000412c  pop     rdi
0x18000412d  retn
```
