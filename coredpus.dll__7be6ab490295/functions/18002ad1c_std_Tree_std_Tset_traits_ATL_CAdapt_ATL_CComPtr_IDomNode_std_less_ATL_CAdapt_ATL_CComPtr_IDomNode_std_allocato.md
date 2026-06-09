# std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::_Erase(std::pair<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *> *,std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *> *>)

- ea: `0x18002ad1c`
- end: `0x18002add3`
- name: `?_Erase@?$_Tree@V?$_Tset_traits@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@U?$less@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@V?$allocator@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@4@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@PEAU12@@2@@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002b260`

## callees

- `0x18002851c`
- `0x1800285c8`
- `0x180028978`
- `0x18002ad1c`
- `0x18002addc`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::_Erase(
        __int64 a1,
        __int64 *a2)
{
  __int64 v2; // r9
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 *v7; // rdi
  __int64 v9; // r9
  __int64 *v10; // r9
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v2 = *a2;
  v4 = a2[1];
  v5 = *a2;
  v13 = *a2;
  v6 = 0;
  while ( v5 != v4 )
  {
    ++v6;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>::operator++(&v13);
    v5 = v13;
  }
  v7 = *(__int64 **)a1;
  v13 = v2;
  if ( v2 == *v7 && *(_BYTE *)(v4 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Erase_tree<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>(
      a1,
      a1,
      v7[1]);
    v7[1] = (__int64)v7;
    *v7 = (__int64)v7;
    v7[2] = (__int64)v7;
    *(_QWORD *)(a1 + 8) = 0;
  }
  else
  {
    while ( v2 != v4 )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>::operator++(&v13);
      v14 = v9;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>::operator++(&v14);
      v11 = std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Extract((__int64 **)a1, v10);
      std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>::_Freenode<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>(
        v12,
        v11);
      v2 = v13;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002ad1c  mov     [rsp+arg_10], rbx
0x18002ad21  push    rbp
0x18002ad22  push    rsi
0x18002ad23  push    rdi
0x18002ad24  sub     rsp, 20h
0x18002ad28  mov     r9, [rdx]
0x18002ad2b  mov     rsi, rcx
0x18002ad2e  mov     rbx, [rdx+8]
0x18002ad32  mov     rax, r9
0x18002ad35  mov     [rsp+38h+arg_0], rax
0x18002ad3a  xor     ebp, ebp
0x18002ad3c  cmp     rax, rbx
0x18002ad3f  jz      short loc_18002AD55
0x18002ad41  inc     rbp
0x18002ad44  lea     rcx, [rsp+38h+arg_0]
0x18002ad49  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>::operator++(void)
0x18002ad4e  mov     rax, [rsp+38h+arg_0]
0x18002ad53  jmp     short loc_18002AD3C
0x18002ad55  mov     rdi, [rsi]
0x18002ad58  mov     [rsp+38h+arg_0], r9
0x18002ad5d  cmp     r9, [rdi]
0x18002ad60  jnz     short loc_18002AD9B
0x18002ad62  cmp     byte ptr [rbx+19h], 0
0x18002ad66  jz      short loc_18002AD9B
0x18002ad68  mov     r8, [rdi+8]
0x18002ad6c  mov     rdx, rsi
0x18002ad6f  mov     rcx, rsi
0x18002ad72  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@@1@PEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Erase_tree<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>(std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>> &,std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *> *)
0x18002ad77  mov     [rdi+8], rdi
0x18002ad7b  mov     [rdi], rdi
0x18002ad7e  mov     [rdi+10h], rdi
0x18002ad82  mov     qword ptr [rsi+8], 0
0x18002ad8a  mov     rbx, [rsp+38h+arg_10]
0x18002ad8f  mov     rax, rbp
0x18002ad92  add     rsp, 20h
0x18002ad96  pop     rdi
0x18002ad97  pop     rsi
0x18002ad98  pop     rbp
0x18002ad99  retn
0x18002ad9b  cmp     r9, rbx
0x18002ad9e  jz      short loc_18002AD8A
0x18002ada0  lea     rcx, [rsp+38h+arg_0]
0x18002ada5  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>::operator++(void)
0x18002adaa  lea     rcx, [rsp+38h+arg_8]
0x18002adaf  mov     [rsp+38h+arg_8], r9
0x18002adb4  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>::operator++(void)
0x18002adb9  mov     rdx, r9
0x18002adbc  mov     rcx, rsi
0x18002adbf  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IDomNode>>>>,std::_Iterator_base0>)
0x18002adc4  mov     rdx, rax
0x18002adc7  call    ??$_Freenode@V?$allocator@U?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@@std@@@?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>::_Freenode<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>(std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>> &,std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *> *)
0x18002adcc  mov     r9, [rsp+38h+arg_0]
0x18002add1  jmp     short loc_18002AD9B
```
