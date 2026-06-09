# std::list<Command,std::allocator<Command>>::_Insert_range<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::forward_iterator_tag)

- ea: `0x1400081a0`
- end: `0x14000822c`
- name: `??$_Insert_range@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@1@1Uforward_iterator_tag@1@@Z`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008234`

## callees

- `0x1400080e0`
- `0x1400081a0`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140008208`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140008208`

## pseudocode

```c
_QWORD *__fastcall std::list<Command>::_Insert_range<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  _QWORD *result; // rax
  __int64 *v6; // rbx
  __int64 v8; // r14
  _QWORD *v9; // rdx
  __int64 v10; // rax
  _QWORD *v11; // rax
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF
  __int64 v14; // [rsp+60h] [rbp+8h]
  __int64 *v16; // [rsp+70h] [rbp+18h] BYREF
  __int64 *v17; // [rsp+78h] [rbp+20h] BYREF

  result = &retaddr;
  v16 = a3;
  v14 = a1;
  v6 = a3;
  v8 = a1;
  v17 = a3;
  while ( v6 != a4 )
  {
    try
    {
      v9 = std::_List_buy<Command>::_Buynode<Command>(
             a1,
             (_QWORD *)a2,
             *(_QWORD **)(a2 + 8),
             (const struct Command *)(v6 + 2));
      v10 = *(_QWORD *)(v8 + 8);
      a1 = 0x1FFFFFFFFFFFFFELL - v10;
      if ( v10 == 0x1FFFFFFFFFFFFFELL )
        std::_Xlength_error("list<T> too long");
      *(_QWORD *)(v8 + 8) = v10 + 1;
      *(_QWORD *)(a2 + 8) = v9;
      result = (_QWORD *)v9[1];
      *result = v9;
      v6 = (__int64 *)*v6;
      v16 = v6;
    }
    catch ( ... )
    {
      while ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(
                                 &v17,
                                 &v16) )
      {
        v12[0] = a2;
        v11 = (_QWORD *)std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>::operator--(v12);
        std::list<Command>::_Unchecked_erase(v14, *v11);
        std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++(&v17);
      }
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400081a0  mov     rax, rsp
0x1400081a3  mov     [rax+18h], r8
0x1400081a7  mov     [rax+10h], rdx
0x1400081ab  mov     [rax+8], rcx
0x1400081af  push    rbx
0x1400081b0  push    rsi
0x1400081b1  push    rdi
0x1400081b2  push    r14
0x1400081b4  sub     rsp, 38h
0x1400081b8  mov     rsi, r9
0x1400081bb  mov     rbx, r8
0x1400081be  mov     rdi, rdx
0x1400081c1  mov     r14, rcx
0x1400081c4  mov     [rax+20h], rbx
0x1400081c8  cmp     rbx, rsi
0x1400081cb  jnz     short loc_1400081D7
0x1400081cd  add     rsp, 38h
0x1400081d1  pop     r14
0x1400081d3  pop     rdi
0x1400081d4  pop     rsi
0x1400081d5  pop     rbx
0x1400081d6  retn
0x1400081d7  lea     r9, [rbx+10h]
0x1400081db  mov     r8, [rdi+8]
0x1400081df  mov     rdx, rdi
0x1400081e2  call    ??$_Buynode@UCommand@@@?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@1@PEAU21@0$$QEAUCommand@@@Z; std::_List_buy<Command>::_Buynode<Command>(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *,Command &&)
0x1400081e7  mov     rdx, rax
0x1400081ea  mov     rax, [r14+8]
0x1400081ee  mov     rcx, 1FFFFFFFFFFFFFEh
0x1400081f8  sub     rcx, rax
0x1400081fb  cmp     rcx, 1
0x1400081ff  jnb     short loc_14000820E
0x140008201  lea     rcx, aListTTooLong; "list<T> too long"
0x140008208  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000820e  inc     rax
0x140008211  mov     [r14+8], rax
0x140008215  mov     [rdi+8], rdx
0x140008219  mov     rax, [rdx+8]
0x14000821d  mov     [rax], rdx
0x140008220  mov     rbx, [rbx]
0x140008223  mov     [rsp+58h+arg_10], rbx
0x140008228  jmp     short loc_1400081C8
```
