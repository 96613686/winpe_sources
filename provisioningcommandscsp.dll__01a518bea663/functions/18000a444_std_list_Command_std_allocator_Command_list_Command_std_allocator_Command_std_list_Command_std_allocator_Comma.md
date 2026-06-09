# std::list<Command,std::allocator<Command>>::list<Command,std::allocator<Command>>(std::list<Command,std::allocator<Command>> const &)

- ea: `0x18000a444`
- end: `0x18000a495`
- name: `??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@AEBV01@@Z`
- size: `81`
- prototype: `__int64 **__fastcall(__int64 **, __int64 ***)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a330`

## callees

- `0x180007698`
- `0x18000a3b0`

## pseudocode

```c
__int64 **__fastcall std::list<Command>::list<Command>(__int64 **a1, __int64 ***a2)
{
  __int64 *v4; // rax
  __int64 **result; // rax

  *a1 = 0;
  a1[1] = 0;
  v4 = (__int64 *)std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(a1, 0, 0);
  *a1 = v4;
  try
  {
    std::list<Command>::_Insert_range<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(
      (__int64)a1,
      *v4,
      **a2,
      (__int64 *)*a2);
    result = a1;
  }
  catch ( ... )
  {
    std::list<Command>::clear(a1);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000a444  mov     [rsp+arg_8], rbx
0x18000a449  mov     [rsp+arg_0], rcx
0x18000a44e  push    rdi
0x18000a44f  sub     rsp, 30h
0x18000a453  mov     rdi, rdx
0x18000a456  mov     rbx, rcx
0x18000a459  mov     qword ptr [rcx], 0
0x18000a460  mov     qword ptr [rcx+8], 0
0x18000a468  xor     r8d, r8d
0x18000a46b  xor     edx, edx
0x18000a46d  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x18000a472  mov     [rbx], rax
0x18000a475  mov     r9, [rdi]
0x18000a478  mov     r8, [r9]
0x18000a47b  mov     rdx, [rax]
0x18000a47e  mov     rcx, rbx
0x18000a481  call    ??$_Insert_range@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@1@1Uforward_iterator_tag@1@@Z; std::list<Command>::_Insert_range<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::forward_iterator_tag)
0x18000a486  nop
0x18000a487  mov     rax, rbx
0x18000a48a  mov     rbx, [rsp+38h+arg_8]
0x18000a48f  add     rsp, 30h
0x18000a493  pop     rdi
0x18000a494  retn
```
