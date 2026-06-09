# std::list<Command,std::allocator<Command>>::_Insert_range<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::forward_iterator_tag)

- ea: `0x18000a8f4`
- end: `0x18000a987`
- name: `??$_Insert_range@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@1@1Uforward_iterator_tag@1@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a990`

## callees

- `0x180006a70`
- `0x18000a8f4`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a95d`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a95d`

## pseudocode

```c
__int64 *__fastcall std::list<Command>::_Insert_range<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *result; // rax
  __int64 *v6; // rbx
  __int64 v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rax
  _QWORD *v11; // rax
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF
  __int64 v14; // [rsp+60h] [rbp+8h]
  __int64 *v16; // [rsp+70h] [rbp+18h] BYREF
  __int64 *v17; // [rsp+78h] [rbp+20h] BYREF

  result = (__int64 *)&retaddr;
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
      result = *(__int64 **)(v9 + 8);
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
0x18000a8f4  mov     rax, rsp
0x18000a8f7  mov     [rax+18h], r8
0x18000a8fb  mov     [rax+10h], rdx
0x18000a8ff  mov     [rax+8], rcx
0x18000a903  push    rbx
0x18000a904  push    rsi
0x18000a905  push    rdi
0x18000a906  push    r14
0x18000a908  sub     rsp, 38h
0x18000a90c  mov     rsi, r9
0x18000a90f  mov     rbx, r8
0x18000a912  mov     rdi, rdx
0x18000a915  mov     r14, rcx
0x18000a918  mov     [rax+20h], rbx
0x18000a91c  cmp     rbx, rsi
0x18000a91f  jnz     short loc_18000A92C
0x18000a921  add     rsp, 38h
0x18000a925  pop     r14
0x18000a927  pop     rdi
0x18000a928  pop     rsi
0x18000a929  pop     rbx
0x18000a92a  retn
0x18000a92c  lea     r9, [rbx+10h]
0x18000a930  mov     r8, [rdi+8]
0x18000a934  mov     rdx, rdi
0x18000a937  call    ??$_Buynode@UCommand@@@?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@1@PEAU21@0$$QEAUCommand@@@Z; std::_List_buy<Command>::_Buynode<Command>(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *,Command &&)
0x18000a93c  mov     rdx, rax
0x18000a93f  mov     rax, [r14+8]
0x18000a943  mov     rcx, 1FFFFFFFFFFFFFEh
0x18000a94d  sub     rcx, rax
0x18000a950  cmp     rcx, 1
0x18000a954  jnb     short loc_18000A969
0x18000a956  lea     rcx, aListTTooLong; "list<T> too long"
0x18000a95d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a969  inc     rax
0x18000a96c  mov     [r14+8], rax
0x18000a970  mov     [rdi+8], rdx
0x18000a974  mov     rax, [rdx+8]
0x18000a978  mov     [rax], rdx
0x18000a97b  mov     rbx, [rbx]
0x18000a97e  mov     [rsp+58h+arg_10], rbx
0x18000a983  jmp     short loc_18000A91C
```
