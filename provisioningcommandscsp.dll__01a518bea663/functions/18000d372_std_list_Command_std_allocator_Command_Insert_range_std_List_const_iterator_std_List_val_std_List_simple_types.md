# _std::list_Command_std::allocator_Command___::_Insert_range_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0

- ea: `0x18000d372`
- end: `0x18000d3d2`
- name: `_std::list_Command_std::allocator_Command___::_Insert_range_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0`
- size: `96`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180006a98`
- `0x180006aa8`
- `0x18000a62c`
- `0x18000bb0c`
- `0x18000c4b0`
- `0x18000d372`

## pseudocode

```c
void __fastcall __noreturn std::list_Command_std::allocator_Command___::_Insert_range_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  void **v4; // rax

  if ( std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(
         (_QWORD *)(a2 + 120),
         (_QWORD *)(a2 + 112)) )
  {
    v3 = *(_QWORD *)(a2 + 104);
    do
    {
      *(_QWORD *)(a2 + 32) = v3;
      v4 = (void **)std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>::operator--(a2 + 32);
      std::list<Command>::_Unchecked_erase(*(void ***)(a2 + 96), *v4);
      std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++((_QWORD **)(a2 + 120));
    }
    while ( std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(
              (_QWORD *)(a2 + 120),
              (_QWORD *)(a2 + 112)) );
  }
  throw;
}

```

## disassembly

```asm
0x18000d372  mov     [rsp+arg_8], rdx
0x18000d377  push    rbx
0x18000d378  push    rbp
0x18000d379  sub     rsp, 28h
0x18000d37d  mov     rbp, rdx
0x18000d380  lea     rdx, [rbp+70h]
0x18000d384  lea     rcx, [rbp+78h]
0x18000d388  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>> const &)
0x18000d38d  test    al, al
0x18000d38f  jz      short loc_18000D3C8
0x18000d391  mov     rbx, [rbp+68h]
0x18000d395  mov     [rbp+20h], rbx
0x18000d399  lea     rcx, [rbp+20h]
0x18000d39d  call    ??F?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>::operator--(void)
0x18000d3a2  mov     rdx, [rax]
0x18000d3a5  mov     rcx, [rbp+60h]
0x18000d3a9  call    ?_Unchecked_erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::list<Command>::_Unchecked_erase(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>)
0x18000d3ae  lea     rcx, [rbp+78h]
0x18000d3b2  call    ??E?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++(void)
0x18000d3b7  lea     rdx, [rbp+70h]
0x18000d3bb  lea     rcx, [rbp+78h]
0x18000d3bf  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>> const &)
0x18000d3c4  test    al, al
0x18000d3c6  jnz     short loc_18000D395
0x18000d3c8  xor     edx, edx; pThrowInfo
0x18000d3ca  xor     ecx, ecx; pExceptionObject
0x18000d3cc  call    _CxxThrowException_0
```
