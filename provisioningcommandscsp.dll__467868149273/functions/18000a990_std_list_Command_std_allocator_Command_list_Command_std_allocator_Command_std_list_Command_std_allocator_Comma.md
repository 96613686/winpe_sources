# std::list<Command,std::allocator<Command>>::list<Command,std::allocator<Command>>(std::list<Command,std::allocator<Command>> const &)

- ea: `0x18000a990`
- end: `0x18000a9e2`
- name: `??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@AEBV01@@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a874`

## callees

- `0x180007a08`
- `0x18000a8f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 **__fastcall std::list<Command>::list<Command>(__int64 **a1, __int64 ***a2)
{
  __int64 *v4; // rax
  __int64 **result; // rax

  *a1 = 0;
  a1[1] = 0;
  std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0((__int64)a1, 0, 0);
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
    std::list<Command>::clear((__int64)a1);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000a990  mov     [rsp+arg_8], rbx
0x18000a995  mov     [rsp+arg_0], rcx
0x18000a99a  push    rdi
0x18000a99b  sub     rsp, 30h
0x18000a99f  mov     rdi, rdx
0x18000a9a2  mov     rbx, rcx
0x18000a9a5  mov     qword ptr [rcx], 0
0x18000a9ac  mov     qword ptr [rcx+8], 0
0x18000a9b4  xor     r8d, r8d
0x18000a9b7  xor     edx, edx
0x18000a9b9  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x18000a9be  mov     [rbx], rax
0x18000a9c1  mov     r9, [rdi]
0x18000a9c4  mov     r8, [r9]
0x18000a9c7  mov     rdx, [rax]
0x18000a9ca  mov     rcx, rbx
0x18000a9cd  call    ??$_Insert_range@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@1@1Uforward_iterator_tag@1@@Z; std::list<Command>::_Insert_range<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::forward_iterator_tag)
0x18000a9d2  nop
0x18000a9d3  mov     rax, rbx
0x18000a9d6  mov     rbx, [rsp+38h+arg_8]
0x18000a9db  add     rsp, 30h
0x18000a9df  pop     rdi
0x18000a9e0  retn
```
