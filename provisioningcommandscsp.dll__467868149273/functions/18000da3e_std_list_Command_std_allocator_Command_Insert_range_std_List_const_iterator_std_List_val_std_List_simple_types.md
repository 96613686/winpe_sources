# _std::list_Command_std::allocator_Command___::_Insert_range_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0

- ea: `0x18000da3e`
- end: `0x18000da9e`
- name: `_std::list_Command_std::allocator_Command___::_Insert_range_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180006dc4`
- `0x180006dd8`
- `0x18000ab98`
- `0x18000c1d8`
- `0x18000cb69`
- `0x18000da3e`

## pseudocode

```c
void __fastcall __noreturn std::list_Command_std::allocator_Command___::_Insert_range_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch_0(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rax

  if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(
                          a2 + 15,
                          a2 + 14) )
  {
    v3 = a2[13];
    do
    {
      a2[4] = v3;
      v4 = (_QWORD *)std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>::operator--(a2 + 4);
      std::list<Command>::_Unchecked_erase(a2[12], *v4);
      std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++(a2 + 15);
    }
    while ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(
                               a2 + 15,
                               a2 + 14) );
  }
  throw;
}

```

## disassembly

```asm
0x18000da3e  mov     [rsp+arg_8], rdx
0x18000da43  push    rbx
0x18000da44  push    rbp
0x18000da45  sub     rsp, 28h
0x18000da49  mov     rbp, rdx
0x18000da4c  lea     rdx, [rbp+70h]
0x18000da50  lea     rcx, [rbp+78h]
0x18000da54  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>> const &)
0x18000da59  test    al, al
0x18000da5b  jz      short loc_18000DA94
0x18000da5d  mov     rbx, [rbp+68h]
0x18000da61  mov     [rbp+20h], rbx
0x18000da65  lea     rcx, [rbp+20h]
0x18000da69  call    ??F?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>::operator--(void)
0x18000da6e  mov     rdx, [rax]
0x18000da71  mov     rcx, [rbp+60h]
0x18000da75  call    ?_Unchecked_erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::list<Command>::_Unchecked_erase(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>)
0x18000da7a  lea     rcx, [rbp+78h]
0x18000da7e  call    ??E?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++(void)
0x18000da83  lea     rdx, [rbp+70h]
0x18000da87  lea     rcx, [rbp+78h]
0x18000da8b  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>> const &)
0x18000da90  test    al, al
0x18000da92  jnz     short loc_18000DA61
0x18000da94  xor     edx, edx; pThrowInfo
0x18000da96  xor     ecx, ecx; pExceptionObject
0x18000da98  call    _CxxThrowException_0
```
